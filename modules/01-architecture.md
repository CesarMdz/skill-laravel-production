# Architecture (Laravel)

## High-value rules
- Controllers must be thin: orchestration only
- Validation: FormRequest
- Authorization: Policies/Gates
- Business rules: Actions/Services (testable)
- Side effects: Events/Jobs (idempotent)

## Red flags
- Fat controllers with queries + business logic + formatting
- Validation inside controller
- Authorization missing or duplicated
- Direct use of env() outside config

## Output expected from reviewer/AI
- Identify where logic should move (Action/Service)
- Identify missing FormRequest/Policy
- Suggest minimal refactor (small PR-safe steps)
