# `task-AffectivePosner_events.json`

```json
{
  "onset": {
    "Description": "Onset of the event.",
    "Units": "seconds"
  },

  "duration": {
    "Description": "Duration of the event, starting from the onset.",
    "Units": "seconds"
  },

  "trial": {
    "Description": "Number of the current trial, starting from 1."
  },

  "event": {
    "Description": "Name of the event within a trial.",
    "Levels": {
      "cue": "Cue appears on screen.",
      "feedback": "Feedback appears on screen."
    }
  },

  "event_condition": {
    "Description": "Condition of the event, corresponding to the cue or feedback.",
    "Levels": {
      "valid": "Cue and target presented on the same side.",
      "invalid": "Cue and target presented on opposite sides.",
      "reward": "Participant receives monetary reward after an accurate response.",
      "rigged": "Participant loses money after an accurate response.",
      "wrong": "Participant receives feedback after no response or an inaccurate response."
    }
  },

  "cue_location": {
    "Description": "Location of the cue.",
    "Levels": {
      "left": "Cue is presented on the left side of the screen.",
      "right": "Cue is presented on the right side of the screen."
    }
  },

  "target_location": {
    "Description": "Location of the target.",
    "Levels": {
      "left": "Target is presented on the left side of the screen.",
      "right": "Target is presented on the right side of the screen."
    }
  },

  "response_location": {
    "Description": "Location of participant response based on button press.",
    "Levels": {
      "left": "Participant pressed the left button.",
      "right": "Participant pressed the right button."
    }
  },

  "response_time": {
    "Description": "Response time to the target.",
    "Units": "seconds"
  },

  "accuracy": {
    "Description": "Whether there was an accurate button press.",
    "Levels": {
      "0": "No accurate response.",
      "1": "Accurate response."
    }
  },

  "feedback_text": {
    "Description": "Text on the feedback screen seen by participants.",
    "Levels": {
      "YOU WIN!": "Reward feedback.",
      "TOO SLOW!": "Rigged feedback.",
      "WRONG!": "Error feedback."
    }
  }
}
```
