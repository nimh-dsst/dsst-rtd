# `participants.json`

```json
{
  "participant_id": {
    "Description": "A participant identifier of the form sub-<label>."
  },
  "age": {
    "Description": "Age of the participant at the time of first MRI data collection.",
    "Units": "months"
  },
  "sex": {
    "Description": "Biological sex of the participant.",
    "Levels": {
      "M": "male",
      "F": "female"
    }
  },
  "group": {
    "Description": "Experimental group the participant belonged to.",
    "Levels": {
      "AUT": "Participants diagnosed with autism disorder (AUT) using DSM-IV-TR criteria by a team of doctoral-level experienced clinicians, using the Autism Diagnostic Interview-Revised (ADI-R), Autism Diagnostic Observation Schedule (ADOS), and clinical judgement.",
      "DD": "Participants with significantly impaired cognitive ability but without autism disorder were enrolled in developmental delay (DD) group.",
      "TYP": "Participants categorized as typically developing (TYP) were recruited for lack of concern in any domain of development and were screened using the Social Communication Questionnaire and cognitive testing."
    }
  }
}
```
