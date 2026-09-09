# Copilot Instructions

## Project overview

- This repository contains a small FastAPI application for Mergington High School extracurricular activities.
- The API entry point is `src/app.py`; it serves the browser client from `src/static/`.
- Activity data is stored in the module-level `activities` dictionary and is intentionally reset when the process restarts.

## Development

- Install dependencies with `pip install -r requirements.txt`.
- Run the app from `src/` with `python app.py`, or launch it through the checked-in VS Code debug configuration.
- The application listens on port 8000. The browser UI is at `/static/index.html`; API documentation is at `/docs`.

## API behavior

- `GET /activities` returns all activities and their participant lists.
- `POST /activities/{activity_name}/signup?email=...` registers a participant.
- `DELETE /activities/{activity_name}/unregister?email=...` removes a participant.
- Preserve the existing HTTP errors for missing activities, duplicate signups, and invalid unregister requests.
- URL-encode activity names and email addresses in client requests because activity names contain spaces.

## Change guidance

- Keep changes focused and consistent with the existing simple FastAPI and vanilla JavaScript structure.
- Do not introduce a database or persistence layer unless the task explicitly requires it.
- When changing API behavior, update the matching client code and documentation, then verify with a local request or a focused test.