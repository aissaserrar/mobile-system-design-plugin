# Mobile & Flutter Non-Functional Requirements Checklist

Use this list when defining FNR. Select and quantify the relevant items. Not every feature needs every category.

## Performance & Responsiveness
- Frame rate target (60 fps or 120 fps) for primary interactions
- List/scroll performance with expected data volume
- Cold start / warm start time
- Animation duration and complexity budget
- Memory ceiling on mid-range devices
- Flutter-specific: avoid excessive rebuilds, heavy work on UI isolate, costly Platform Channel calls in hot paths

## Battery & Network
- Offline capability level (full offline, read-only cache, online-only)
- Background work constraints
- Data usage limits (important for metered networks)
- Sync frequency and conflict strategy

## Accessibility
- Minimum touch target size (48×48 dp recommended)
- Color contrast ratios (WCAG AA or higher)
- Screen reader support (TalkBack / VoiceOver)
- Dynamic type / text scaling support
- Reduced motion preference handling

## Localization & Internationalization
- RTL layout support (critical for Arabic)
- String externalization
- Date, number, and currency formatting (e.g., Algerian dinar)
- Layout flexibility for longer translations

## Security & Privacy
- Sensitive data handling (tokens, PII)
- Biometric or secure storage needs
- Network security (certificate pinning, etc.)

## Reliability & Error Handling
- Offline error states and recovery
- Network timeout and retry behavior
- Graceful degradation when native features are unavailable

## Maintainability & Testability
- Component isolation expectations
- Analytics or feature-flag hooks
- Platform-specific code boundaries (Pigeon / Platform Channels)

## Design System Specific
- Token usage constraints (spacing, color, typography scales)
- Component variant limits
- Theming (light/dark/high-contrast) requirements
- Consistency with existing patterns
