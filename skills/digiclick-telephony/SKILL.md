---
name: digiclick-telephony
description: Use the DigiClick telephony MCP tools to answer and place phone calls, send and receive texts, take voicemail and manage numbers. Trigger when the user wants to call, text, answer the phone, check voicemail, or get a phone number.
---

# DigiClick Telephony

You have a real phone line. The tools are on the MCP server named `telephony`.
Set `DIGICLICK_API_KEY` to a key from https://app.digiclick.com/mcp/console
before use.

## Calling someone
1. `place_call` with `to`, `brain: "mcp"`, and an `opener` (what to say when
   they answer). It returns a `callId`.
2. Loop: `wait_for_turn` (up to 25 s) → read what they said → `speak` your
   reply. Keep replies to one or two sentences; it is read aloud.
3. Say goodbye with `speak`, then `hangup_call`. Hanging up ends the call —
   there is no "I'll call you back" unless you place a new call first.

## Answering the phone
`wait_for_call` long-polls for an inbound call. The line has already answered
and greeted; call `answer_call` to take it, then the same `wait_for_turn` /
`speak` loop. If you do not claim it, the line apologises or takes a voicemail
per the owner's settings.

## Texts, voicemail, numbers
`send_sms` / `wait_for_message` / `fetch_media`; `list_voicemails` and
`get_voicemail` (transcript + audio); `search_numbers`, `buy_number`,
`configure_number`, `release_number`.

## Rules
- Say you are an AI assistant if asked. Never claim to be human.
- No robocalls or unsolicited texts; honour STOP and do-not-call requests.
- Phone style: short sentences, no markdown, numbers read one digit at a time.
