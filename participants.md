---
layout: default
title: participants_*
rank: 3
---

## Participants overview file (`participants_overview*`)

Template:

```Text
participants_overview.tsv
participants_overview.json
```
The purpose of this RECOMMENDED file is to describe properties of participants which are session independent such as age, sex, handedness and so forth. If this file exists, it MUST contain the column participant_id, which MUST consist of sub-<label> values identifying one row for each participant, followed by a list of optional columns describing participants. Each participant MUST be described by one and only one row.

`participants_overview.tsv` example:

```Text
participant_id  sex   handedness  group
sub-KKqxkP          M     right       patient
sub-Znknpt          F     right       control
sub-EtD2sa          F     n/a         patient
```

Each `participants_overview.tsv` file with a sidecar `participants_overview.json` file to describe the TSV column names and properties of their values (see also the section on tabular files). Such sidecar files are needed to interpret the data, especially so when optional columns are defined beyond age, sex, handedness, such as group in this example, or when a different age unit is needed (for example, gestational weeks).

`participants_overview.json` example:
```Text
{
    "sex": {
        "Description": "sex of the participant as reported by the participant",
        "Levels": {
            "M": "male",
            "F": "female"
        }
    },
    "handedness": {
        "Description": "handedness of the participant as reported by the participant",
        "Levels": {
            "left": "left",
            "right": "right"
        }
    },
    "group": {
        "Description": "group the participant belonged to",
        "Levels": {
            "ET": "participants who have been diagnosed with ET",
            "PD": "participants who have been diagnosed with PD"
        }
    }
}
```
## Participants session file (`participants_session*`)

Template:

```Text
participants_session.tsv
participants_session.json
```
The purpose of this RECOMMENDED file is to describe properties of participants which are session dependent such as age, weight, clinical score (e.g. MDS-UPDRS-III) and so forth. If this file exists, it MUST contain the column participant_id, which MUST consist of sub-<label> values session_id and identifying one row for each participant per visit, followed by a list of optional columns describing participants.

`participants_overview.tsv` example:

```Text
participant_id  session_id  age weight  MDS-UPDRS-III
sub-KKqxkP          v1n1	55  72      65
sub-KKqxkP          v2n1	56  75      42
sub-Znknpt          v1n1	74  64      78
```
For the same reasons as mentioned above, it is RECOMMENDED to have a accompanied `participants_overview.json` file.

`participants_overview.json` example:
```Text
{
    "session_id": {
        "Description": "Label of sessions conducted",
        "Levels": {
            "v1n1": "Pre-oprativ visit before first operation, within 3 month prior to intervention",
            "v2n1": "Post-oprativ visit after first operation, within 1 week past intervention",
            "v3n1": "Post-oprativ visit after first operation, within 1-3 month past intervention",
            "v4n1": "Post-oprativ visit after first operation, within 4-6 month past intervention",
            "v5n1": "Post-oprativ visit after first operation, within 7-12 month past intervention",
            "v6n1": "Post-oprativ visit after first operation, within 13-24 month past intervention",
            "v7n1": "Post-oprativ visit after first operation, within 25-36 month past intervention",
            "v8n1": "Post-oprativ visit after first operation, within 37-48 month past intervention",
            "v1n2": "Pre-oprativ visit before second operation, within 3 month prior to intervention",
            "v2n2": "Post-oprativ visit after second operation, within 1 week past intervention",
            "v3n2": "Post-oprativ visit after second operation, within 1-3 month past intervention",
            "v4n2": "Post-oprativ visit after second operation, within 4-6 month past intervention",
            "v5n2": "Post-oprativ visit after second operation, within 7-12 month past intervention",
            "v6n2": "Post-oprativ visit after second operation, within 13-24 month past intervention",
            "v7n2": "Post-oprativ visit after second operation, within 25-36 month past intervention",
            "v8n2": "Post-oprativ visit after second operation, within 37-48 month past intervention",
            "v1n3": "Pre-oprativ visit before third operation, within 3 month prior to intervention",
            "v2n3": "Post-oprativ visit after third operation, within 1 week past intervention",
            "v3n3": "Post-oprativ visit after third operation, within 1-3 month past intervention",
            "v4n3": "Post-oprativ visit after third operation, within 4-6 month past intervention",
            "v5n3": "Post-oprativ visit after third operation, within 7-12 month past intervention",
            "v6n3": "Post-oprativ visit after third operation, within 13-24 month past intervention",
            "v7n3": "Post-oprativ visit after third operation, within 25-36 month past intervention",
            "v8n3": "Post-oprativ visit after third operation, within 37-48 month past intervention",
        },
    "age": {
            "Description": "age of the participant",
            "Units": "years"
        },
    "MDS-UPDRS-III": {
        "Description": "MDS-UPDRS-III total score of the participant",
        "Units": "Total points, range 0-144"
    }
}
```
