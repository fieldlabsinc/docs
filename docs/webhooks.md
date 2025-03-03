# Webhooks

## Introduction

Currently, we only support webhook for transcription events.

## How to use

1. Go to Compass app
2. Click on the "Profile" button (also called Settings)
3. Scroll down to the "Developer Settings" section, open it
4. Enter the webhook URL.

> Webhook URL should be a public URL.

>

## Webhook payload

Every time a transcription is completed and appended to your memory, the webhook will be triggered.

The payload will be a JSON object with the following fields:

- `date`: The date and time of the transcription.
- `transcription`: The whole transcription text.
- `transcriptions`: An array of transcriptions of different speakers.
  - `text`: The transcription text.
  - `speaker`: The speaker of the transcription.
  - `start`: The start time of the transcription.
  - `end`: The end time of the transcription.
  - `duration`: The duration of the transcription.

```json
{
  "date": "2025-03-01T16:35:00.100907+00:00",
  "transcription": "Hi, my name is Adam.",
  "transcriptions": [
    {
      "text": "Hi, my name is Adam.",
      "speaker": "A",
      "start": 0.04,
      "end": 4.4,
      "duration": 4.36
    }
  ]
}
```

> You can use [requestcatcher.com](https://requestcatcher.com/) to test the webhook.
