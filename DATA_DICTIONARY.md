# Data dictionary

JSON envelope: generated (build timestamp, not event time), release (build identity), coverage
(selection disclaimer), license (licence metadata), incidents (array). CSV values are quoted strings;
JSON retains null, number, arrays and objects. Empty string/null/empty array mean absent or unavailable,
not false or zero. Source references are zero-based indices in that dossier's sources array.

| Dossier field (CSV and JSON) | Meaning |
|---|---|
| id | Stable dossier identifier; not an individual aircraft ID. |
| title | Public dossier title. |
| place | Public city, region, sea or other coarse place label. |
| country | Country label; sea association does not prove territorial location or flag. |
| countryCode | Two-letter country association. |
| scope | single or wave: report extent; not an actor or weapon inference. |
| review | editor or auto; automatic is not editorial approval. |
| corroboration | curated, multiple, single; source tier distinct from claim confidence. |
| dateKind | event or statement; statement uses a report/statement date rather than a known event date. |
| date | YYYY-MM-DD, interpreted with dateKind, no time/zone precision implied. |
| category | Archive's incident category; classification can change. |
| droneStatus | confirmed, reported, inconclusive, debunked: presence only. |
| impactStatus | confirmed, reported, inconclusive, debunked, unknown: consequences only. |
| attributionStatus | none, suspected, claimed, charged, convicted, officially-attributed: responsibility state. |
| lat | Approximate latitude or null; read locationPrecision. |
| lon | Approximate longitude or null; read locationPrecision. |
| locationPrecision | Stated precision of dossier coordinates; never precision of a display anchor. |
| checkedAt | Editorial check date or absent; not incident occurrence time. |
| autoCheckedAt | Automatic check date or absent; not editorial review. |
| updatedAt | Dossier update timestamp/date; not incident time. |
| summary | Summary prose. |
| impact | Consequences prose, interpreted with impactStatus. |
| evidence | Evidence assessment prose. |
| unknown | Known gaps and unresolved questions. |
| attribution | Responsibility prose, interpreted with attributionStatus. |

## Reporting windows (CSV and JSON)
windowStart/windowEnd: optional inclusive calendar-day bounds, YYYY-MM-DD; both null for legacy dossiers.
windowBasis: explicit, source-relative-evening-night or source-relative-24h. A reporting window is not
a set of separately located events or exact timestamps. Source-relative requires a demonstrated source
offset. Legacy date/dateKind are retained; do not use the date as an exact event day when a window exists.
Never backfill a window from an old date or count it once in each covered day.

## CSV-only flattened columns
source_urls: source URLs joined by ` | `; source_families: unique publisher-family slugs in
encounter order joined by ` | `; sources_json: JSON-encoded sources array (use this rather than
splitting URLs). ref_lat/ref_lon/ref_level: flattened referencePoint coordinates/level or empty.
No nested claims, timeline or history are flattened into CSV. Use JSON for those.

## JSON-only nested dossier fields
- sources[]: label (publisher/document label), url (HTTPS original), published (source publication
  date, YYYY-MM-DD), family (organisation slug). A family does not establish original independence.
- droneStatusSources[], impactStatusSources[], attributionSources[]: supporting source indices
  for the respective axis; empty does not prove a negative observation.
- droneTypes[]: asReported (literal reported type label), type (catalog slug or null), count
  (positive integer or null), countMetric (launched, intercepted, impacted or null), sourceIndex.
  Do not add overlapping counts, different time windows or different metrics.
- claims[]: id (claim slug), axis (claim axis), statement (assertion), quote (source passage),
  claimant (original speaker/organisation), note (assessment explanation), originId (shared original
  statement identity), relay (direct/relayed), assessment (evidence assessment), sourceIndex,
  quoteCheckedAt (quote check date or null). Read those together; repeated relay is not corroboration.
- timeline[]: date (YYYY-MM-DD), text (event/check narrative), source (supporting source index).
  Entries are dossier chronology, not trajectories or precise observation times.
- referencePoint: null or lat/lon (display anchor), name (named place), level (city/region/sea/country)
  and any provenance/precision members present. It is not measured incident geolocation.
- history[]: available dossier change entries; revision (version number), date (change date), at (change timestamp), note
  (change explanation). This export is not a guarantee of complete historical evidence snapshots;
  bind analysis to envelope.release and MANIFEST hashes, not a guessed current revision.

No internal state, credentials, queue/hold flags or unpublished dossiers belong in this export.
Enums and optional nested members can evolve; preserve unknown fields and report schema changes.
