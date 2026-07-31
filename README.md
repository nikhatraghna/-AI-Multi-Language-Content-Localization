# AI Multi-Language Content Localization Workflow

n8n automation that translates new Google Sheets rows from English into Urdu, Arabic, and French using Hugging Face, writes results back to the sheet, and emails a confirmation.

## What it does
- Triggers on new Google Sheet rows
- Skips empty/already-translated rows
- Translates via Hugging Face Inference API
- Writes translations back to the row
- Sends Gmail confirmation on completion

## Sheet columns
`Content ID | English Content | Urdu Translation | Arabic Translation | French Translation | Status`

## Models
| Language | Model |
|---|---|
| EN → Urdu | `Helsinki-NLP/opus-mt-en-ur` |
| EN → Arabic | `Helsinki-NLP/opus-mt-en-ar` |
| EN → French | `Helsinki-NLP/opus-mt-en-fr` |

## Setup
1. Create the sheet with the columns above
2. Add credentials in n8n: Google Sheets OAuth2, Gmail OAuth2, Hugging Face API token (`Authorization: Bearer <token>`)
3. Import the workflow, connect credentials, activate
4. Test with a new row of English content
