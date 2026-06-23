# Changelog

All notable changes to **JanUI.WinForms** will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [1.0.0] — 2026-06-23

### 🎉 Initial Release

First public release of **JanUI.WinForms** — a modern, Bootstrap 5-inspired WinForms
control library for .NET 6 and .NET 8 with 21 fully custom-painted, theme-aware controls.

### Added

#### Theming System
- **3-layer colour resolution** — user overrides → scheme tokens → JanTheme global fallback
- **8 built-in colour schemes** — Primary, Success, Danger, Warning, Info, Secondary, Light, Dark
- **JanTheme** — static global theme class with `Apply(ThemePreset)` for application-wide theming
- **JanControlBase** — base class implementing the full 3-layer theming contract
- **ColorScheme enum** — scheme selector shared across all themed controls
- **SchemeToken** — per-scheme colour token resolver

#### Feedback & Notifications
- **JanAlert** — Bootstrap-style inline alert and floating toast notification
  - 8 alert types (Info, Success, Warning, Danger, Primary, Secondary, Light, Dark, Custom)
  - Auto-dismiss with configurable delay and countdown progress bar
  - Static `Show()` helpers for one-line toast creation
  - 7 screen positions (TopLeft, TopCenter, TopRight, BottomLeft, BottomCenter, BottomRight, CenterScreen)
  - Dismissible × button, custom icon support, configurable border radius

- **JanInputDialog** — Modern themed modal input dialog
  - 5 input types: Text, WholeNumber, Decimal, PositiveNumber, Password
  - Built-in validation with inline error messages and focus highlighting
  - 7 themes: Default, Info, Success, Warning, Danger, Dark, Custom
  - Static `ShowText()`, `ShowWholeNumber()`, `ShowDecimal()`, `ShowPositiveNumber()`, `ShowPassword()` helpers
  - Draggable borderless window

- **JanLoaderControl** — Animated loading spinner overlay
  - Covers entire form or specific container control
  - Semi-transparent overlay using screen-capture background blending
  - Configurable spinner size, arc thickness, spin speed, and colours

- **JanProgressBar** — Custom progress bar with value label
  - Independent channel (track) and slider heights
  - 5 text positions: None, Left, Right, Center, Sliding
  - Configurable prefix/suffix symbols and `ShowMaximum` mode

#### Input Controls
- **JanButton** — Flat-style button with full 3-layer theming
- **JanCheckBox** — Custom-painted checkbox with GDI+ vector checkmark
- **JanComboBox** — Bootstrap-style dropdown with single and multi-select badge chips
- **JanDatePicker** — Themed date picker with custom themed calendar popup
- **JanDropdownMenu** — Fully themed ContextMenuStrip with 8 colour schemes and two visual modes
- **JanRadioButton** — Custom-painted radio button with GDI+ circle rendering
- **JanTextBox** — Text input with placeholder, password mask, underline style, and focus ring
- **JanToggleButton** — On/off toggle switch with solid and outline modes

#### Layout & Navigation
- **JanCard** — Gradient container card with drop shadow and hover effect
- **JanPanel** — Rounded panel with gradient or solid background fill
- **JanSidebar** — Full-featured expandable navigation sidebar
  - Header (brand + toggle), Nav (item tree), Footer (user profile) sections
  - Expand/collapse animation with 4 easing curves
  - Unlimited nav item nesting, badge chips, icon tinting, hover tooltips
  - 21 sidebar-specific colour tokens
  - `NavItemClicked`, `GroupToggled`, `ExpandedChanged` events
  - `Expand()`, `Collapse()`, `Toggle()`, `SetActiveItem(key)` public API
- **JanSidePanel** — Panel with independent per-corner radius control

#### Data Display
- **JanChart** — Multi-type chart control
  - 6 chart types: Bar (Grouped/Stacked), Line, Spline, Area, Pie, Donut
  - Smooth entry animation, interactive hover tooltips, legend with 4 positions
  - VS2022 designer CollectionEditor support
- **JanTable** — Full-featured Bootstrap-style data table
  - Sorting, search, per-column filters, pagination
  - Row selection, checkboxes, inline cell editing, column resizing
  - 4 responsive modes: None, Fill, FillEqual, AutoFit
  - Custom JanScrollBar on both axes, striped rows/columns
  - `RowClicked`, `CellEdited`, `RowChecked`, `SelectionChanged` events

#### Decorative & Utilities
- **JanCircularPictureBox** — Circular image frame with gradient border
- **JanEllipseControl** — Non-visual component applying rounded corners to any control via Win32 GDI32
- **JanScrollBar** — Custom scrollbar (internal, used by JanTable and JanSidebar)

### Technical
- Multi-target: `net6.0-windows` and `net8.0-windows`
- No external dependencies — pure WinForms + GDI+
- Full Visual Studio 2022 designer support with ShouldSerialize/Reset pairs
- XML documentation file included for IntelliSense
- Symbol package (`.snupkg`) published for debugging support

---

## Upcoming

### [1.1.0] — Planned
- JanProductCard control
- Dark mode global theme preset
- JanTable export to CSV
- Additional animation easing curves
- Demo application (installable via NuGet)

---

*For bug reports and feature requests, visit the
[JanUI.Docs repository](https://github.com/Sujan-Murugesh/JanUI.Docs).*
