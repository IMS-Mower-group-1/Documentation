# API Endpoints

## Mow-session

### 1. Get all mow sessions for a mower

- **URL:** `https://tgin13-1-q1387758.deta.app/mow-session/mower/:id`
- **Method:** `GET`
- **URL Params:** `id=[string]` (Mower ID)
- **Success Response:**
  - **Code:** `200`
  - **Content:** Array of mow session objects
- **Error Response:**
  - **Code:** `500`
  - **Content:** `{ error: 'Internal server error' }`

### 2. Get active mow session for a mower

- **URL:** `https://tgin13-1-q1387758.deta.app/mow-session/mower/:id/active`
- **Method:** `GET`
- **URL Params:** `id=[string]` (Mower ID)
- **Success Response:**
  - **Code:** `200`
  - **Content:** Active mow session object
- **Error Response:**
  - **Code:** `500`
  - **Content:** `{ error: 'Internal server error' }`

### 3. Start mow session for a mower

- **URL:** `https://tgin13-1-q1387758.deta.app/mow-session/start-session/:id`
- **Method:** `POST`
- **URL Params:** `id=[string]` (Mower ID)
- **Success Response:**
  - **Code:** `201`
  - **Content:** `{ message: 'Mowing session started successfully', sessionId: [string] }`
- **Error Response:**
  - **Code:** `500`
  - **Content:** `{ error: 'Internal server error' }`

### 4. End mow session for a mower

- **URL:** `https://tgin13-1-q1387758.deta.app/mow-session/end-session/:id`
- **Method:** `POST`
- **URL Params:** `id=[string]` (Mower ID)
- **Success Response:**
  - **Code:** `200`
  - **Content:** `{ message: 'Mowing session ended successfully' }`
- **Error Response:**
  - **Code:** `500`
  - **Content:** `{ error: 'Internal server error' }`

## Position

### 1. Update position

- **URL:** `https://tgin13-1-q1387758.deta.app/position/update/:id`
- **Method:** `POST`
- **URL Params:** `id=[string]` (Mower ID)
- **Data Params (Body):** `{ "position": "(x, y)" }` (Current position as a string)
- **Success Response:**
  - **Code:** `200`
  - **Content:** `{ message: "Position updated & added to the mowing session path" }`
- **Error Response:**
  - **Code:** `500`
  - **Content:** `{ error: "Internal server error" }`

## Image

### 2. Upload image

- **URL:** `/upload/:mowerID/:mowSessionID`
- **Method:** `POST`
- **URL Params:**
  - `mowerID=[string]` (Mower ID)
  - `mowSessionID=[string]` (Mowing session ID)
- **Content-Type:** `application/octet-stream`
- **Data Params:** Binary image data (application/octet-stream)
- **Success Response:**
  - **Code:** `200`
- **Error Response:**
  - **Code:** `400`
