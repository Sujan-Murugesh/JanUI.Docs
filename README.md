# JanUI — WinForms Control Library

<!-- LOGO — replace path with your actual uploaded image on NuGet/GitHub -->
<p align="center">
  <img src="https://raw.githubusercontent.com/Sujan-Murugesh/JanUI.Docs/main/assets/logo_title.png"
       alt="JanUI Logo" width="250" />
</p>

<p align="center">
  <img src="https://img.shields.io/nuget/v/JanUI.WinForms?style=flat-square&color=6366f1&label=NuGet" alt="NuGet version"/>
  <img src="https://img.shields.io/nuget/dt/JanUI.WinForms?style=flat-square&color=10b981&label=Downloads" alt="Downloads"/>
  <img src="https://img.shields.io/badge/.NET-6%20%7C%208-512BD4?style=flat-square" alt=".NET 6 | 8"/>
  <img src="https://img.shields.io/badge/Platform-Windows-0078D4?style=flat-square" alt="Windows"/>
  <img src="https://img.shields.io/badge/License-MIT-f59e0b?style=flat-square" alt="MIT License"/>
</p>

<p align="center">
  A modern, Bootstrap 5-inspired WinForms control library for .NET 6 and .NET 8.<br/>
  21 fully custom-painted, theme-aware controls — no OS chrome, no native widget artifacts.
</p>

---

## Screenshot

<!-- SCREENSHOT — replace with actual screenshot of your demo app -->
<p align="center">
  <img src="https://raw.githubusercontent.com/Sujan-Murugesh/JanUI.Docs/main/screenshots/screenshot-overview.png"
       alt="JanUI Controls Overview" width="800"/>
</p>

---

## ✨ Features

- **21 custom-painted controls** — every control owns its GDI+ paint logic
- **3-layer theming system** — user overrides → scheme tokens → JanTheme global
- **8 built-in colour schemes** — Primary, Success, Danger, Warning, Info, Secondary, Light, Dark
- **VS2022 designer support** — full Property Grid integration, ShouldSerialize/Reset pairs
- **Bootstrap 5-inspired** — familiar API for web developers moving to desktop
- **Multi-target** — `net6.0-windows` and `net8.0-windows`

---

## 📦 Installation

```shell
# NuGet Package Manager
Install-Package JanUI.WinForms

# .NET CLI
dotnet add package JanUI.WinForms
```

**Requirements:**
- .NET 6+ or .NET 8+ (Windows only)
- Add `<UseWindowsForms>true</UseWindowsForms>` to your `.csproj`
- Target must include `-windows` suffix (e.g. `net8.0-windows`)
- Visual Studio 2022 recommended

---

## 🚀 Quick Start

```csharp
using JanUI.WinForms.Controls;
using JanUI.WinForms.Themes;

// Apply a global theme to all Default-scheme controls
JanTheme.Apply(ThemePreset.Dark);

// Theme a single button
myButton.ThemeScheme = ColorScheme.Success;

// Show a toast notification
JanAlert.Show(this, "Saved successfully.", JanAlertType.Success, autoDismissMs: 3000);

// Collect user input
string? name = JanInputDialog.ShowText("Enter your name:");

// Load a data table
janTable1.Columns = new List<string> { "ID", "Name", "Status" };
janTable1.LoadData(GetRows());
```

---

## 🎨 Theming

Every colour resolves through three layers — first non-null wins:

| Priority | Layer | How to set |
|----------|-------|------------|
| 1 (highest) | **User** — per-instance explicit override | `button.BackgroundColor = Color.Red` |
| 2 | **Scheme** — full palette via ThemeScheme | `button.ThemeScheme = ColorScheme.Danger` |
| 3 (fallback) | **JanTheme** — application-wide global | `JanTheme.Apply(ThemePreset.Dark)` |

### Built-in colour schemes

<!-- SCHEMES SCREENSHOT -->
<p align="center">
  <img src="https://raw.githubusercontent.com/YOUR_USERNAME/JanUI/main/assets/screenshot-schemes.png"
       alt="JanUI colour schemes" width="700"/>
</p>

```csharp
button.ThemeScheme = ColorScheme.Primary;    // Bootstrap blue
button.ThemeScheme = ColorScheme.Success;    // Bootstrap green
button.ThemeScheme = ColorScheme.Danger;     // Bootstrap red
button.ThemeScheme = ColorScheme.Warning;    // Bootstrap amber
button.ThemeScheme = ColorScheme.Info;       // Bootstrap cyan
button.ThemeScheme = ColorScheme.Dark;       // Dark surface
```

---

## 🧩 Controls

### Feedback & Notifications
| Control | Description |
|---------|-------------|
| `JanAlert` | Bootstrap-style inline alert + floating toast with auto-dismiss |
| `JanInputDialog` | Modal input dialog — Text, Number, Decimal, Password types |
| `JanLoaderControl` | Animated loading spinner overlay |
| `JanProgressBar` | Custom progress bar with sliding value label |

### Input Controls
| Control | Description |
|---------|-------------|
| `JanButton` | Flat-style button with hover/active states |
| `JanCheckBox` | Custom-painted checkbox with rounded corners |
| `JanComboBox` | Dropdown with single and multi-select + badge chips |
| `JanDatePicker` | Date selector with custom themed calendar popup |
| `JanDropdownMenu` | Fully-themed context menu with 8 colour schemes |
| `JanRadioButton` | Custom-painted radio button |
| `JanTextBox` | Text input with placeholder, password mask, underline style |
| `JanToggleButton` | On/off toggle switch |

### Layout & Navigation
| Control | Description |
|---------|-------------|
| `JanCard` | Gradient card container with shadow and hover effect |
| `JanPanel` | Rounded panel with gradient background |
| `JanSidebar` | Expandable navigation sidebar with header, nav, footer sections |
| `JanSidePanel` | Panel with independent per-corner radius |

### Data Display
| Control | Description |
|---------|-------------|
| `JanChart` | Chart control — Bar, Line, Spline, Area, Pie, Donut |
| `JanTable` | Full-featured data table with search, sort, pagination, filters |

### Decorative & Utilities
| Control | Description |
|---------|-------------|
| `JanCircularPictureBox` | Circular image frame with gradient border |
| `JanEllipseControl` | Applies rounded corners to any WinForms control via GDI32 |
| `JanScrollBar` | Custom scrollbar (used internally by JanTable and JanSidebar) |

---

## 📸 Control Gallery

<!-- GALLERY — add individual control screenshots here -->

### JanButton & JanToggleButton
<p align="center">
  <img src="https://raw.githubusercontent.com/YOUR_USERNAME/JanUI/main/assets/screenshot-buttons.png"
       alt="JanButton and JanToggleButton" width="700"/>
</p>

### JanTable
<p align="center">
  <img src="https://raw.githubusercontent.com/YOUR_USERNAME/JanUI/main/assets/screenshot-table.png"
       alt="JanTable" width="700"/>
</p>

### JanChart
<p align="center">
  <img src="https://raw.githubusercontent.com/YOUR_USERNAME/JanUI/main/assets/screenshot-chart.png"
       alt="JanChart" width="700"/>
</p>

### JanSidebar
<p align="center">
  <img src="https://raw.githubusercontent.com/YOUR_USERNAME/JanUI/main/assets/screenshot-sidebar.png"
       alt="JanSidebar" width="700"/>
</p>

### JanAlert & JanInputDialog
<p align="center">
  <img src="https://raw.githubusercontent.com/YOUR_USERNAME/JanUI/main/assets/screenshot-dialogs.png"
       alt="JanAlert and JanInputDialog" width="700"/>
</p>

### JanComboBox (Multi-select)
<p align="center">
  <img src="https://raw.githubusercontent.com/YOUR_USERNAME/JanUI/main/assets/screenshot-combobox.png"
       alt="JanComboBox multi-select" width="700"/>
</p>

### JanDatePicker & JanCard
<p align="center">
  <img src="https://raw.githubusercontent.com/YOUR_USERNAME/JanUI/main/assets/screenshot-datepicker-card.png"
       alt="JanDatePicker and JanCard" width="700"/>
</p>

---

## 💡 Common Patterns

### Toast notification
```csharp
// Success — auto-dismisses
JanAlert.Show(this, "Record saved.", JanAlertType.Success, autoDismissMs: 3500);

// Danger — persistent
JanAlert.Show(this, "Connection failed.", JanAlertType.Danger,
    autoDismissMs: 0, position: JanAlertPosition.TopRight);
```

### Sidebar navigation
```csharp
var sidebar = new JanSidebar
{
    Dock      = DockStyle.Left,
    BrandText = "MyApp",
    UserName  = "Sujan Perera",
    UserEmail = "sujan@example.com"
};

sidebar.Items.Add(new JanSidebarNavItem { Text = "Dashboard", Key = "home" });
sidebar.Items.Add(new JanSidebarNavItem { Text = "Reports",   Key = "reports" });
sidebar.NavItemClicked += (s, e) => LoadPage(e.Item.Key);
this.Controls.Add(sidebar);
```

### Data table with search and pagination
```csharp
var table = new JanTable
{
    Dock           = DockStyle.Fill,
    ShowSearch     = true,
    ShowPagination = true,
    StripedRows    = true,
    ResponsiveMode = ResponsiveMode.Fill
};
table.Columns = new List<string> { "ID", "Name", "Role", "Status" };
table.LoadData(GetUsers());
table.RowClicked += (s, e) => OpenUser(e.RowData[0]);
this.Controls.Add(table);
```

### Multi-series chart
```csharp
var chart = new JanChart { ChartType = JanChartType.Bar, Dock = DockStyle.Fill };

var revenue = chart.AddSeries("Revenue", Color.FromArgb(99, 102, 241));
revenue.Points.Add(new JanChartDataPoint("Q1", 48000));
revenue.Points.Add(new JanChartDataPoint("Q2", 62000));
revenue.Points.Add(new JanChartDataPoint("Q3", 57000));

this.Controls.Add(chart);
```

---

## 📐 Namespace Summary

| Namespace | Contents |
|-----------|----------|
| `JanUI.WinForms.Controls` | All 21 UI controls |
| `JanUI.WinForms.Themes` | JanTheme, ColorScheme, SchemeToken, JanControlBase |
| `JanUI.WinForms.Helpers` | Shared enums, drawing utilities, extension methods |

---

## 📋 Requirements

| Requirement | Detail |
|-------------|--------|
| .NET version | .NET 6+ or .NET 8+ (Windows only) |
| Windows Forms | `<UseWindowsForms>true</UseWindowsForms>` in `.csproj` |
| Target suffix | Must target `-windows` (e.g. `net8.0-windows`) |
| IDE | Visual Studio 2022 recommended |
| Platform | Windows only |

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.

---

<p align="center">
  Built with ❤️ for the WinForms community<br/>
  <strong>JanUI.WinForms.Controls</strong>
</p>
