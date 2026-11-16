# Examples: Strong vs Weak Requirements

## Functional Requirements

**Weak**
- User can manage club members.

**Strong**
- The system shall allow an authenticated admin to add a new member by entering name, phone, and membership type.
- Acceptance: Member appears in the list within 2 seconds when online; validation errors shown inline; duplicate phone numbers rejected.
- The system shall support searching members by name or phone.
- Acceptance: Results update as the user types; empty state shown when no matches.

## Non-Functional Requirements

**Weak**
- The app should be fast and support Arabic.

**Strong**
- Primary member list must scroll at 60 fps with 150 items on a mid-range Android device (Snapdragon 7-series or equivalent).
- All interactive elements must have a minimum touch target of 48×48 dp.
- Full RTL layout support for Arabic; no hardcoded left/right padding.
- Offline: cached member list readable for 7 days; write operations queued and synced when connectivity returns.

## Out of Scope

**Weak**
- Not everything is included.

**Strong**
- Out of scope for this phase:
  - Payment collection
  - Push notifications
  - Custom native animations beyond standard Flutter transitions
  - iOS-only features (e.g., Live Activities)
  - Multi-club switching (single club context only)

## Design System Impact Example

- New: `MemberListItem` component with states (default, selected, offline-cached)
- Token: Ensure 48 dp minimum touch target token exists
- RTL: All spacing in list item must use logical properties
- No new Platform Channels required
