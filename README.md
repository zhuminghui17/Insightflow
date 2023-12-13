# Insightflow API List

Flask server and AWS services like DynamoDB, S3, Lambda, etc.

## Table of Contents
- [1. User Management](#1-user-management)
- [2. Video Management](#2-video-management)
- [3. Transcription Services](#3-transcription-services)
- [4. AI Analysis](#4-ai-analysis)
- [5. Project Management](#5-project-management)
- [6. Dashboard](#6-dashboard)

## 1. User Management
Endpoints related to user registration, authentication, and profile management.

### `POST /api/users/register`
- **Description:** Register a new user.
- **Body:** `username`, `email`, `password`

### `POST /api/users/login`
- **Description:** Authenticate a user.
- **Body:** `email`, `password`
- **Returns:** Authentication token

### `GET /api/users/profile`
- **Description:** Retrieve user profile details.
- **Headers:** `Authorization: Bearer <token>`

### `PUT /api/users/profile`
- **Description:** Update user profile details.
- **Headers:** `Authorization: Bearer <token>`
- **Body:** Profile update fields

## 2. Video Management
Endpoints for handling video uploads to AWS S3 and retrievals.

### `POST /api/videos/upload`
- **Description:** Upload a new interview video to AWS S3.
- **Body:** Video file data

### `GET /api/videos/{videoId}`
- **Description:** Retrieve specific video details from AWS S3.
- **Parameters:** `videoId`

### `GET /api/videos/list`
- **Description:** List all videos for a project from AWS S3.
- **Query:** `projectId`

## 3. Transcription Services
Endpoints for video transcriptions using AWS Transcribe.

### `POST /api/transcriptions/generate/{videoId}`
- **Description:** Generate transcription for a video using AWS Transcribe.
- **Parameters:** `videoId`

### `GET /api/transcriptions/{videoId}`
- **Description:** Retrieve transcription of a video from DynamoDB.
- **Parameters:** `videoId`

## 4. AI Analysis
Endpoints for AI-driven analysis using AWS Comprehend or Lambda functions.

### `POST /api/analysis/categorize/{videoId}`
- **Description:** Analyze and categorize video content using AWS services.
- **Parameters:** `videoId`

### `GET /api/analysis/tags/{videoId}`
- **Description:** Retrieve tags and categories for a video from DynamoDB.
- **Parameters:** `videoId`

## 5. Project Management
Endpoints for creating and managing projects stored in DynamoDB.

### `POST /api/projects/create`
- **Description:** Create a new project in DynamoDB.
- **Body:** Project details

### `GET /api/projects/{projectId}`
- **Description:** Retrieve project details from DynamoDB.
- **Parameters:** `projectId`

### `PUT /api/projects/update/{projectId}`
- **Description:** Update a project in DynamoDB.
- **Parameters:** `projectId`
- **Body:** Updated project details

### `DELETE /api/projects/delete/{projectId}`
- **Description:** Delete a project from DynamoDB.
- **Parameters:** `projectId`

## 6. Dashboard
Endpoints for dashboard data retrieval, aggregating data from various AWS services.

### `GET /api/dashboard/overview`
- **Description:** Retrieve overall dashboard data, aggregating information from AWS services.

### `GET /api/dashboard/project/{projectId}`
- **Description:** Retrieve dashboard data for a single project, using data from AWS services.
- **Parameters:** `projectId`


