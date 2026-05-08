# Bottles: Invisible Proceed Button on libadwaita 1.9+

## Issue

When installing a program that requires local resources (e.g. `url: local` in the installer YAML), the "Proceed" button in the installer dialog is invisible. Users can select the local file, but cannot continue with the installation because the button never appears.

This affects Bottles 63.2 (native/AUR build) running on systems with libadwaita 1.9.0 or later. The Flatpak version is unaffected because it bundles an older libadwaita.

## Root Cause

In `bottles/frontend/ui/dialog-installer.blp`, the `btn_proceed` widget is a bare `GtkButton` placed as a direct child of `Adw.PreferencesPage`:

```
Adw.PreferencesPage {
  Adw.PreferencesGroup group_resources { ... }

  Button btn_proceed { ... }   // <-- not rendered by libadwaita 1.9+
}
```

`AdwPreferencesPage` expects all children to be `AdwPreferencesGroup` widgets. In libadwaita < 1.9, bare widgets were still rendered. In 1.9+, non-group children are silently dropped.

## Fix

Wrap `btn_proceed` in an `Adw.PreferencesGroup`:

```diff
- Button btn_proceed {
-   label: _("Proceed");
-   sensitive: false;
-   visible: false;
-   halign: center;
-   valign: center;
-
-   styles [
-     "pill",
-     "suggested-action",
-   ]
- }
+ Adw.PreferencesGroup {
+   Button btn_proceed {
+     label: _("Proceed");
+     sensitive: false;
+     visible: false;
+     halign: center;
+     valign: center;
+
+     styles [
+       "pill",
+       "suggested-action",
+     ]
+   }
+ }
```

## Affected Versions

- **Bottles**: 63.2
- **libadwaita**: 1.9.0+ (confirmed on CachyOS with `libadwaita 1:1.9.0-1.1`)
- **Not affected**: Flatpak builds (bundle older libadwaita)

## Status

Patched locally. Should be reported upstream at [bottlesdevs/Bottles](https://github.com/bottlesdevs/Bottles).
