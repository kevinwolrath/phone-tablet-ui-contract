# Empty, loading, error and notice states

Read this when changing how a page or section presents missing data, loading, errors or notices. The page chooses which state applies; this contract owns how that state appears.

## Zero data

A section is zero-data when its underlying value or collection contains no useful user data, even if it could still render a heading, explanation or count of zero.

- Whole-page empty state: explain the absence and offer the appropriate primary action when one exists.
- Empty section inside an otherwise useful page: collapse or hide it by default.
- Do not keep large empty cards merely for symmetry with populated sections.
- Do not add redundant boxes saying `No items yet`, `Nothing recorded` or `0 items` simply to occupy space.
- Keep the creation/population action discoverable without reserving a large empty container.
- Explain an absence only when the absence itself is meaningful or potentially confusing.

Judge the rendered result, not the component name. A reusable `EmptyState` that creates a large useless container is still the wrong result.

## Loading and error

Loading should communicate progress without making stale controls appear actionable.

Errors should be understandable and, when recovery is possible, expose the relevant recovery action rather than a collection of generic controls.
