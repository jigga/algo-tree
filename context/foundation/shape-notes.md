---
project: "AlgoTree"
context_type: greenfield
created: 2026-09-02
updated: 2026-09-07
product_type: web-app
timeline_budget:
  mvp_weeks: 3
  hard_deadline: null
  after_hours_only: true
checkpoint:
  current_phase: 8
  phases_completed: [1, 2, 3, 4, 5, 6]
  gray_areas_resolved: []
  frs_drafted: 4
  quality_check_status: accepted
---

## Vision & Problem Statement
Software engineers suffer from the "Illusion of Competence" during technical interview prep—they rote-solve LeetCode problems without cementing the underlying concepts, leading to rapid knowledge decay. When they revisit a topic weeks later, they fail to recall the core patterns.

The solution is a gamified "Decaying Skill Tree" for algorithms. The product forces active recall via spaced repetition. Users must prove conceptual mastery through micro-quizzes to keep their skill tree "healthy". Only when a concept reaches 100% mastery does the app recommend the specific LeetCode problems the user is now genuinely ready to solve.

## User & Persona
**Primary Persona:** Software engineers actively preparing for technical interviews who want structured, long-term retention rather than ad-hoc problem solving.

## Access Control
Full Login (email/password or OAuth) to support future expansion to a broader user base. Flat user model: every logged-in user has the same permissions, with no admin or role separation needed for the MVP.

## Success Criteria
### Primary
- The app displays a visual "Skill Tree" of curated core algorithmic concepts (e.g., Arrays, Hash Maps, Two Pointers).
- Users can take an AI-generated multiple-choice quiz to "unlock" or "restore" a concept's health to 100%.
- Upon reaching 100% mastery of a concept, the app reveals curated, hardcoded LeetCode problem links for the user to practice on.

### Secondary
- A simple, automated linear decay mechanism (e.g., mastery drops 20% per day) forces users to return for daily reviews.

### Guardrails
- **Performance:** AI quiz generation must respond in < 10 seconds.
- **Pedagogy:** Quizzes must test conceptual building blocks (e.g., recognizing when to use a technique) rather than syntax or memorized code solutions.

## Functional Requirements
- FR-001: [User] can [create an account and log in securely]. Priority: must-have
- FR-002: [User] can [view a dashboard showing their skill tree and current mastery percentage for each node]. Priority: must-have
- FR-003: [User] can [complete an AI-generated micro-quiz to increase the mastery health of a specific node]. Priority: must-have
- FR-004: [User] can [view a list of curated LeetCode problem recommendations when a node reaches 100% health]. Priority: must-have

## User Stories
### US-01: User completes their Daily Review
- **Given** a logged-in user whose "Two Pointers" node has decayed to 60% health
- **When** they click "Review" and pass the 3-question AI-generated quiz
- **Then** the node health is restored to 100%, and the app displays: "Mastery Restored! Apply your knowledge on LeetCode #167 (Two Sum II)."
#### Acceptance Criteria
- Quiz questions are dynamically generated based on the concept.
- Progress (health score) is successfully updated in the database.

## Business Logic
- **Decay Rule:** Concept mastery decays linearly over time (e.g., -20% every 24 hours). 
- **Restoration Rule:** Passing a quiz restores the health to 100%. Failing provides feedback but does not restore health.
- **Unlock Rule:** Curated LeetCode links are gated; they are only recommended/visible if the node is at 100% health.

## Data Model
- **User:** Auth credentials.
- **Concept (Static):** Hardcoded topics (e.g., Two Pointers) and their associated LeetCode URL recommendations.
- **UserProgress:** Joins User and Concept. Tracks `mastery_percentage` and `last_reviewed_at`.

## Non-Goals
- **Functional:** The app will NOT dynamically scrape LeetCode URLs or generate problem-specific quizzes for unknown URLs. It relies on a curated list of hardcoded topics.
- **Functional:** The app will NOT execute, compile, or validate user code.
- **Non-functional:** Complex spaced-repetition math (like the SuperMemo/Anki algorithms) is deferred. The MVP uses a simple linear decay script.

## Stack Openness
- **Product Type:** Web App.
- **Constraints:** Open to any modern web stack (e.g., React, Next.js, Postgres). No strict framework constraints.
