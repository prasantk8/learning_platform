Based on the MVP's scope and architecture, here is the detailed build plan broken down into user stories with clear acceptance criteria. The plan is optimized for rapid development and includes strategies for parallel AI assistance and robust documentation to ensure continuity.

Agile Development Plan: User Stories & Sprints
Our goal is to build and ship as fast as possible. We will approach this in a modular way, treating each pillar as a set of user stories to be completed within short development cycles.

Sprint 1: Core Framework & Socratic Tutor (Target: 3-5 days)
User Story 1.1 (Developer): As a developer, I want to set up the project's core framework and version control, so that I have a stable foundation for all future work.

Acceptance Criteria:

A Git repository is created with a main and develop branch.

A .gitignore file is committed to the repository.

The core folder structure is created: frontend/, backend/, models/, docs/, data/.

A README.md is created with instructions for a developer to set up the environment and run the project.

A context.md file is created in the root, summarizing the project's goal, architecture, and current state.

User Story 1.2 (User): As a user, I want to interact with a basic Socratic Math Tutor, so that I can ask it questions and get relevant answers about 10th-grade Algebra.

Acceptance Criteria:

The Mistral 7B Instruct (GGUF) model is successfully loaded by the FastAPI Orchestrator.

A POST /tutor/ask endpoint is functional and returns a JSON response.

The endpoint correctly takes a user's prompt and uses a system prompt to frame the response as a math tutor.

The Flutter frontend has a chat interface that can send text to the endpoint and display the response.

Sprint 2: Inner World & Launchpad Integration (Target: 3-5 days)
User Story 2.1 (User): As a user, I want to record my emotional state via a daily text check-in, so that I can track my inner well-being.

Acceptance Criteria:

The fine-tuned DistilBERT model for sentiment analysis is loaded by the FastAPI Orchestrator.

A POST /checkin/emotional endpoint is functional and returns a sentiment classification (e.g., joy, calm, sadness).

The sentiment and the timestamp are successfully stored in the SQLite database.

The Flutter frontend has a dedicated UI element for the daily check-in that calls this endpoint.

User Story 2.2 (User): As a user, I want the system to show me relevant content based on what I am learning in the Socratic Tutor, so that I can connect academic concepts to real-world applications.

Acceptance Criteria:

The explore_feed.json file is present and correctly structured with tags.

The Concept Weaving Python logic is implemented to parse keywords from the tutor's response (e.g., "quadratic," "factor").

When a new math concept is introduced, the system triggers a call to an internal endpoint that returns a list of matching content items from the explore_feed.json.

The Flutter frontend displays the curated Explore Feed list.

Sprint 3: Optimization, Polish & On-Device Validation (Target: 2-4 days)
User Story 3.1 (Developer): As a developer, I want to validate the on-device performance of the app on a lighter model, so that we can ensure it runs well on the target user's compute.

Acceptance Criteria:

A build script is created to swap the Mistral 7B model with the Gemma 2B model.

The Socratic Tutor and Concept Weaving logic work correctly with the smaller model.

Performance metrics (e.g., response time, memory usage) are recorded for both Mistral 7B and Gemma 2B.

User Story 3.2 (User): As a user, I want a seamless and bug-free MVP, so that I have a delightful first experience with the product.

Acceptance Criteria:

All endpoints are properly secured and validated.

All user flows are tested end-to-end to ensure there are no crashes or unexpected behavior.

The UI has a polished look and feel that reflects the product's quality.
