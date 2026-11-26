# DroneLedger — source-traced drone incident dossiers

Snapshot 2026-11-26: 669 published dossiers (176 editor-reviewed, 493 automatic).
Archive: https://droneincidents.com · methodology: https://droneincidents.com/methodology/
Release: 20261126T053747487418-3eeab9; generated: 2026-11-26T05:37:36+00:00. Package SHA-256 hashes: MANIFEST.json.

## Unit, coverage and language
One row is a dossier, not one drone, sortie, attack, casualty or independently verified event.
The retained dossier dates range from 2015-06-28 to 2026-11-26. This is observed snapshot coverage,
not the start of comprehensive monitoring. Backfilled and source-date records may be included.
A weekly archive can lag the website; later versions may correct, merge or withdraw dossiers.
The archive is selective, worldwide in scope, with uneven media/source/language coverage.
English is the base dataset text. The website has English, Ukrainian, Russian, Arabic and Persian
interfaces; that does not imply complete translation or equal source coverage in those languages.
Sources can be official statements, news agencies, publishers and other public reporting.
Publication repetition is not independent corroboration: follow claims.originId/relay and sources.family.
Source publication dates are not incident dates or verified local incident times.

## Fields in this package
- JSON envelope: `generated`, `release`, `coverage`, `license`, `incidents`.
- JSON dossier fields: `archiveEntity`, `archivePattern`, `assessment`, `assessment_droneType_level`, `assessment_droneType_range_high`, `assessment_droneType_range_low`, `assessment_droneType_subject`, `assessment_operator_level`, `assessment_operator_range_high`, `assessment_operator_range_low`, `assessment_operator_subject`, `assessment_scale_version`, `assessment_target_level`, `assessment_target_range_high`, `assessment_target_range_low`, `assessment_target_subject`, `attribution`, `attributionSources`, `attributionStatus`, `autoCheckedAt`, `autoEnrichments`, `category`, `checkedAt`, `claims`, `corroboration`, `country`, `countryCode`, `date`, `dateKind`, `droneStatus`, `droneStatusSources`, `droneTypes`, `eventFacts`, `evidence`, `followUp`, `history`, `id`, `impact`, `impactReports`, `impactStatus`, `impactStatusSources`, `lat`, `locationPrecision`, `lon`, `media`, `namedLocation`, `operationalEffects`, `outcome`, `place`, `plainSummary`, `publisherMedia`, `referencePoint`, `reportTiming`, `review`, `revision`, `scope`, `series`, `sources`, `summary`, `timeline`, `title`, `unknown`, `updatedAt`, `windowBasis`, `windowEnd`, `windowStart`.
- CSV columns in order: `id`, `title`, `place`, `country`, `countryCode`, `scope`, `review`, `corroboration`, `dateKind`, `date`, `category`, `droneStatus`, `impactStatus`, `attributionStatus`, `lat`, `lon`, `locationPrecision`, `checkedAt`, `autoCheckedAt`, `updatedAt`, `summary`, `impact`, `evidence`, `unknown`, `attribution`, `windowStart`, `windowEnd`, `windowBasis`, `source_urls`, `source_families`, `sources_json`, `ref_lat`, `ref_lon`, `ref_level`, `impact_reports_json`, `media_json`, `operationalEffects_json`, `followUp_json`, `archiveEntity_json`, `namedLocation_json`, `publisherMedia_json`, `archivePattern_json`, `assessment_scale_version`, `assessment_operator_subject`, `assessment_operator_level`, `assessment_operator_range_low`, `assessment_operator_range_high`, `assessment_target_subject`, `assessment_target_level`, `assessment_target_range_low`, `assessment_target_range_high`, `assessment_droneType_subject`, `assessment_droneType_level`, `assessment_droneType_range_low`, `assessment_droneType_range_high`, `assessment_json`, `outcome_json`, `reportTiming_json`, `revision`, `droneStatusSources_json`, `impactStatusSources_json`, `attributionSources_json`, `claims_json`, `timeline_json`.

Every dossier includes original source URLs in JSON `sources` and CSV `source_urls`.
The package uses the validated public release. Unpublished dossiers and withdrawn revision entries
are excluded. Evidence states still apply to the individual claims and fields.

## Evidence and analysis
Presence, impact and attribution have separate states. Confirmed presence does not confirm damage,
a specific type or a perpetrator. `review=auto` means no editorial review. `corroboration=multiple`
is a registered-source tier, not a guarantee that every assertion has two independent originals;
`curated` denotes editorial selection, not a universal confirmed status. Missing/null is not zero.

Use counts to describe this snapshot's dossiers, stratified by dateKind, review, source families,
country and separate evidence states. Report selection and missingness. Read sources and claims
before using individual findings. Do not infer attack frequency, geographic risk, fleet losses,
interception rates, casualty totals or country rankings from row counts. Do not sum overlapping
national/regional/local reports, successive interim counts, types or launched/intercepted/impacted
metrics. Claims by conflict parties remain attributed claims, not independently measured outcomes.
`lat/lon` are approximate only; `referencePoint` and CSV ref_* are display anchors, never incident
positions. Country codes on sea dossiers must not be treated as proof of territorial location or flag.

## Files and reproducibility
- incidents.csv: UTF-8, quoted cells, one row per dossier. Formula-like text has a leading apostrophe;
  preserve the original value using JSON where exact transcription is needed.
- incidents.json: release envelope and dossiers with sources, claims, timeline and available history.
- DATA_DICTIONARY.md: all current CSV/JSON fields, nested evidence and reference indices.
- CITATION.cff: project author and snapshot version; no unreserved future DOI is invented.
- MANIFEST.json: source release/generated timestamp and hashes of the four data/document files above
  plus CITATION.cff. CSV/JSON are read from one resolved immutable release directory.

For reproducibility cite the exact version DOI shown on Zenodo, snapshot date, release and file hash;
use the concept DOI only to refer to the series. Never substitute the previous version's DOI for
this snapshot. The supplied concept DOI is 10.5281/zenodo.23345422; check it on Zenodo before citing.

## Licence
Dossier data: CC BY 4.0; attribution: DroneLedger (droneincidents.com).
Source quotations and linked articles retain publisher rights; the dataset licence does not grant
rights to reproduce those articles. GeoNames place references require CC BY 4.0 attribution.
