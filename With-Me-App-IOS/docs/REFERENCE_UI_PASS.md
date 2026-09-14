# Reference UI pass — September 2026

This pass applies the visual language from the supplied behavior check-in screenshot to the main app shell while keeping the existing routes and feature logic intact.

## Updated

- Login and sign-up now use the warm sunset/sea backdrop, cream cards, teal controls, and With Me mascot.
- Home now uses the same cream question-card / option-tile language as the reference screen.
- Main navigation bar and drawer were changed from blue-grey to the cream/teal visual system.
- Shared home action buttons now look like the selectable rows in the reference UI.
- The existing guided check-in was tightened to match the reference proportions more closely:
  - 86 px minimum question card height
  - 59 px minimum option row height
  - existing progress dots, avatar footer, cream surfaces, teal selection state, and sunset backdrop retained
- The app-level theme now defaults to `buildWithMeTheme()` so unstyled Material controls inherit the same palette.

## Intentionally unchanged

Feature-specific legacy screens such as Dashboard, Mood Tracker, Settings, FAQ, and breathing exercise details still contain some hard-coded blue-grey colors. Their logic is untouched in this pass. They can be migrated screen-by-screen using the same shared tokens in `lib/WithMe/Theme/WithMeTheme.dart`.

## Main files changed

- `lib/main.dart`
- `lib/Components/MainScaffold.dart`
- `lib/Components/NavBar.dart`
- `lib/Components/ActionButton.dart`
- `lib/Components/WelcomeCardComponent.dart`
- `lib/Screens/HomeScreen.dart`
- `lib/Screens/LoginScreen.dart`
- `lib/Screens/SignUpScreen.dart`
- `lib/ViewModels/HomeViewModel.dart`
- `lib/WithMe/Screens/CheckInScreen.dart`
- `lib/WithMe/Components/WithMeControls.dart`

## Validation note

The editing environment used for this pass does not include the Flutter SDK, so a full `flutter analyze` / iOS build could not be run here. The changed Dart files were checked for balanced syntax delimiters and relative imports. Run `flutter analyze` and then launch on your iOS simulator/device before merging.

---

## Scenic With Me Companion pass

This pass specifically updates the **With Me Companion** flow so it visually matches the scenic mascot reference more closely:
- added a new scenic companion background asset under `assets/with_me/companion_scenic_bg.png`
- redesigned `WithMeBackdrop` to use the scenic artwork instead of the prior abstract sunset painter
- updated the With Me welcome, greeting, chat, and check-in screens with translucent glass cards, scenic overlays, and mascot-first composition
- restyled companion controls and bubbles so the interaction UI feels closer to the reference image
