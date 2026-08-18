---
name: "Merge feature/collab-bible-security into main"
---

This pull request merges the feature branch that contains the Collaborative Bible Study prototype and security groundwork into the repository main branch.

What this PR includes:
- collaborative-bible-study.html: a demo KJV reader with note-taking, group notes, a 12-day demo reading plan, and a client-side simulated AI summary. Requires a display name (stored in localStorage) before saving notes.
- firestore.rules: draft Firestore security rules enforcing PRIVATE / GROUP / PUBLIC visibility for studyNotes, and group member checks.
- functions/index.js: Cloud Functions skeleton providing generateGroupSummary endpoint that filters notes server-side (only GROUP/PUBLIC are included) and stores summary metadata. Uses a simulated summary unless OPENAI_API_KEY is set.

Notes & recommendations before merging to main:
- The demo currently uses a localStorage name-only auth shim. For production, replace this with Firebase Authentication (Email + Google) and use auth.uid for authorId before making the site public.
- Firestore rules are a draft; test them locally with the Firestore emulator before deploying.
- Cloud Functions are included as a skeleton. To enable real AI summarization, set OPENAI_API_KEY in the functions environment.

Steps after merge:
1. Run local emulator and tests (I can provide commands in the PR description).
2. Deploy Firestore rules and Cloud Functions to your Firebase project (requires deployment access).
3. Replace demo auth shim with Firebase Auth and migrate stored local names if desired.

If you want me to proceed and create the PR on GitHub, confirm and I will open it and post the PR link here for review.
