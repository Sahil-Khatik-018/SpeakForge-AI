# SpeakForge AI - Request Flows

---

# Flow 1 - User Login

## Trigger

User clicks **Continue with Google**

## Flow

1. User opens the application.
2. Frontend starts Google Authentication.
3. Google verifies user identity.
4. Frontend receives Google Token.
5. Frontend sends token to Backend.
6. Backend verifies token.
7. Backend checks whether user exists.
8. If user does not exist, create a new user.
9. Backend generates session.
10. Backend returns authenticated user.
11. Frontend redirects to Dashboard.

---

# Flow 2 - Get Daily Challenge

## Trigger

Dashboard loads.

## Flow

1. Frontend requests today's challenge.
2. Backend checks challenge collection.
3. Backend returns today's challenge.
4. Frontend displays challenge.

---

# Flow 3 - Upload Speaking Recording

## Trigger

User clicks Submit Recording.

## Flow

1. Frontend validates recording.
2. Audio uploaded to backend.
3. Backend validates audio.
4. Backend stores temporary audio.
5. Backend returns upload success.

---

# Flow 4 - AI Evaluation

## Trigger

Audio upload completed.

## Flow

1. Backend sends audio to Whisper.
2. Whisper converts speech into text.
3. Backend receives transcript.
4. Backend sends transcript to GPT.
5. GPT evaluates:
   - Grammar
   - Pronunciation
   - Fluency
   - Vocabulary
   - Confidence
6. GPT returns structured feedback.
7. Backend stores feedback.
8. Backend responds to frontend.

---

# Flow 5 - View Feedback

## Trigger

Evaluation completed.

## Flow

1. Frontend requests latest evaluation.
2. Backend fetches feedback.
3. Backend returns result.
4. Frontend displays:
   - Overall Score
   - Grammar
   - Fluency
   - Vocabulary
   - Pronunciation
   - Confidence Tips

---

# Flow 6 - View History

## Trigger

User opens History page.

## Flow

1. Frontend requests previous sessions.
2. Backend queries database.
3. Backend returns speaking history.
4. Frontend displays chronological history.