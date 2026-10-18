# CLAUDE.md — Adaptive Exam Portal (CI6600 Individual Project)

This file gives Claude Code the context for this repository. Read it at the start of every session.

## About the project

- **Student:** Abdul Rafay Pervaiz, BSc Computer Science, Kingston University London
- **Module:** CI6600 Individual Project (final year project), 2026/27
- **Working title:** An Adaptive Examination App Using Item Response Theory to Personalise Assessment Difficulty
- **Aim:** Design, build and evaluate a mobile-first adaptive exam app. It uses Item Response Theory (IRT) to choose questions that match each student's estimated ability. The project tests whether it can measure ability as accurately as a fixed-length test while using fewer questions.

### Users
- **Students** take adaptive practice tests and see an explained result: estimated ability, strong topics and weak topics.
- **Teachers** create a question bank, set up tests, and view results and question analytics (for example, items flagged as too easy, too hard or poorly discriminating).

### The core technical feature
The adaptive engine:
1. Estimates the student's ability (theta) after each answer.
2. Picks the next question that gives the most information at that ability.
3. Stops when the estimate is precise enough or a maximum length is reached.
4. Controls item exposure so the same questions aren't overused.
5. Calibrates item parameters from real response data over time.

The engine must be pure, well-tested code that runs outside the UI, so a simulation script can evaluate it.

## Tech stack (provisional — the student makes the final decisions)

- **App:** React Native with Expo, TypeScript, also built for the web (Expo for Web) so markers can use a public URL
- **Backend:** Supabase (PostgreSQL, Auth, Row Level Security)
- **Adaptive engine:** a TypeScript module in `packages/engine` (or `src/engine`) with unit tests
- **Simulation and evaluation:** scripts in `scripts/simulation` that generate simulated students and compare adaptive and fixed tests
- **Hosting:** web build on Vercel or Netlify; mobile build through Expo (EAS)

Don't add a new major library or service without asking first and explaining the trade-offs.

## Assessment rules this repo must support

- **AI use is allowed and must be declared** (Category 3). The student must be able to explain every part of the code in a compulsory viva.
- So, for every non-trivial change:
  - Explain **what** you changed and **why**, in plain English.
  - Point out any choices or alternatives the student should decide on, rather than deciding silently.
  - Keep changes small enough to review.
- Marks reward the student's own understanding, decisions and evaluation, not just the amount of code.

## Working conventions

- **Commits:** small and focused, with clear messages in the imperative ("Add 2PL probability function", not "update"). One logical change per commit.
- **Branches:** work on `main` for now unless the student asks for feature branches.
- **Secrets:** never commit `.env` files, API keys or Supabase service keys. Use `.env.example` with placeholder values.
- **Tests:** the adaptive engine must have unit tests. Add or update tests with every engine change.
- **Accessibility:** support screen readers (accessibility labels), sufficient colour contrast, scalable text, and an "extra time" setting.
- **Privacy (GDPR):** collect the minimum personal data. Use test or anonymised data only. Never use the app for real graded assessments.

## Documentation to keep up to date

- `docs/project-log.md` holds dated entries of what was done, decisions made and problems hit. Remind the student to add an entry at the end of each session.
- `docs/ai-log.md` holds notes for Appendix A of the report. After a significant session, suggest a short entry covering:
  - the key instructions given
  - what the AI contributed
  - what the student contributed or changed
  - how it was verified
- `README.md` holds setup steps, how to run the app, the live URL and test login details for markers.

## Key milestones

| Milestone | Due |
|---|---|
| 1. Introduction and State of the Art Review | 23–27 Nov 2026 |
| 2. Analysis and Design | 11–15 Jan 2027 |
| 3. Realisation (the build) | 15–19 Mar 2027 |
| 4. Testing, Validation and Critical Review | 12 Apr 2027 (final submission; viva within two weeks) |
