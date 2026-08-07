# SpeakForge AI - API Design

## Purpose

This document defines the REST API endpoints for Version 1.

---

# Base URL

```
/api/v1
```

---

# Authentication

## Google Login

### POST

```
/auth/google
```

### Purpose

Authenticate user using Google OAuth.

### Request

```json
{
  "token": "google_jwt_token"
}
```

### Response

```json
{
  "success": true,
  "user": {},
  "accessToken": ""
}
```

---

# Challenges

## Get Today's Challenge

### GET

```
/challenges/today
```

### Response

```json
{
  "success": true,
  "challenge": {}
}
```

---

# Speaking Sessions

## Upload Recording

### POST

```
/sessions
```

### Content Type

```
multipart/form-data
```

### Body

```
audio
challengeId
```

### Response

```json
{
  "success": true,
  "sessionId": ""
}
```

---

## Get Session Status

### GET

```
/sessions/:id/status
```

### Response

```json
{
  "status": "evaluating"
}
```

Possible values

- uploaded
- transcribing
- evaluating
- completed
- failed

---

## Get AI Feedback

### GET

```
/sessions/:id
```

### Response

```json
{
  "success": true,
  "session": {}
}
```

---

## Get User History

### GET

```
/sessions/history
```

### Response

```json
{
  "success": true,
  "history": []
}
```

---

# Dashboard

## Dashboard Summary

### GET

```
/dashboard
```

### Returns

- Current Streak
- Total Sessions
- Average Score
- Latest Challenge
- Latest Feedback

---

# Error Response

Every endpoint follows this format.

```json
{
  "success": false,
  "message": "Error message"
}
```

---

# Success Response

```json
{
  "success": true,
  "data": {}
}
```

---

# Version 1 Endpoints

| Method | Endpoint | Purpose |
|----------|----------|----------|
| POST | /auth/google | Login |
| GET | /challenges/today | Today's Challenge |
| POST | /sessions | Upload Audio |
| GET | /sessions/:id/status | Processing Status |
| GET | /sessions/:id | AI Feedback |
| GET | /sessions/history | User History |
| GET | /dashboard | Dashboard Summary |