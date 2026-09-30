# Skygauge Dispatch · UX demo

An independent, interactive redesign of [Skygauge Dispatch POC](https://github.com/Nikita-skygauge/skygauge-dispatch-poc), based on source commit `5cb8a4a5bffa61add8f5b9eac16b33b14de1cd0d`.

This is a separate repository copy because GitHub does not support forking a personal repository back into the same account. The original repository and deployed application are unchanged.

## Try it

Open the [demo](https://nikita-skygauge.github.io/skygauge-dispatch-ux-demo/). Start with **New job**, then add an owner, due date, asset, scope, and notes. Switch between List and Board, or explore a sample email thread in Inbox.

To run locally, serve this folder with any static web server, for example `python3 -m http.server 8767`, and open `http://localhost:8767`.

## What changed

- Jobs is the starting point, with List and Board views and a quieter sidebar.
- Creating a job requires only a name. Asset and map location are optional.
- Jobs open as full pages. Owner, due date, asset, work type, and scope are easy to find.
- Text notes stay inside the job page. Spatial notes still use the original map tools.
- Advanced properties, photos, files, activity, and email threads remain available.
- Phone layouts use compact job rows and full-page job details.
- Main job controls support keyboard access; dialogs use native focus management.
- Four sample jobs have illustrative map locations (an area, a line, and two pins). The map names the selected job, explains missing locations, and provides a re-centre button.
- A one-time migration fills empty locations on the four original sample jobs. Existing geometry, job edits, notes, and map credentials are preserved. Sample locations are not verified positions of real assets.

## Demo boundaries

The application always uses an isolated browser-local database. The original Firebase configuration has been removed, and no URL parameter can enable a live connection. Sample people use `example.com` addresses. Outgoing email is simulated and never sent.

Changes persist only in the same browser and origin. This is not a shared workspace or production data store. Browser storage has a size limit; demo file uploads are limited to 2 MB, and save errors are displayed. Clearing site data resets the sample workspace. Avoid uploading real confidential job documents.

The original Google 3D map and spatial editing code is preserved. It requires a Maps JavaScript API key, billing, and an allowed website restriction for this demo origin. Add that key through Site map; it is saved only in the current browser. Camera/location capture still requires device permission. Sample shapes illustrate the workflow; they are not surveyed asset locations.

Original authentication and Firestore adapters remain as inactive source reference. Reconnecting a real backend needs a separate implementation and validation pass, including access control, storage, email delivery, data migration, and concurrency.

## Validation

Checked JavaScript syntax and browser flows for name-only job creation, owner/status/due-date changes, scope and note editing, reload persistence, List and Board navigation, search, sample replies, and phone layouts. Also checked real 3D sample-area rendering, map framing, missing-location messaging and placement entry, and the one-time map migration (including preservation of existing geometry, renamed/deleted jobs, notes, and configuration). The original production repository was not modified.

`index.html` contains the original application with the demo data and workflow changes. `ux.css` contains the interface styling layer. No build step is required.
