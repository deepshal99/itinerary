# Itinerary Builder

A concept for a cinematic, emotionally warm itinerary builder that guides travelers through a conversational, one-intent-per-screen flow. The experience is inspired by Airbnb’s question-led onboarding and focuses on calm energy, tactile delight, and AI-assisted planning.

## Experience System
- Read the [Itinerary Builder Experience System](design/itinerary_experience.md) for the full visual language, component definitions, and interaction guidance.
- Explore the [Conversational Flow](design/flow.yml) to understand the step-by-step structure powering the guided planning journey.

## MVP Scope
1. Conversational onboarding (destination → vibe → duration → dates).
2. AI-suggested experiences and Trip Stack builder.
3. Smart day grouping with tactile timeline editing.
4. Map-first visualization with day filters.
5. Save & relive mode with memory timeline.

## Technology Notes
The concept assumes a modern React/Next.js stack with motion handled by Framer Motion or React Spring and conversational orchestration powered by a state machine (e.g., XState). AI suggestions can be integrated via serverless endpoints while retaining user control at every step.

## Brand Tone
Calm, confident, and friendly — a travel partner who listens. Microcopy should stay human, optimistic, and lightly playful.

