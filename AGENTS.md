# GEMINI.md - FieldLogger-FMXTraining

## Project Overview
**FieldLogger-FMXTraining** is a comprehensive training project designed to teach experienced Delphi and C++Builder developers how to build cross-platform mobile applications using **FireMonkey (FMX)**.

The core of the training is the development of the **Field Logger** app, a mobile utility for field workers (e.g., insurance adjusters) to collect log data including timestamps, photos, geolocation, device orientation, and user notes.

### Key Technologies
- **Language:** Delphi (Object Pascal)
- **Framework:** FireMonkey (FMX) for cross-platform UI (iOS, Android, Windows, macOS)
- **Database:** InterBase (IBLite/ToGo) via FireDAC
- **Data Binding:** LiveBindings
- **Sensors:** TLocationSensor, TOrientationSensor, TMotionSensor, TCameraComponent
- **Reporting:** HTML/JSON export with Base64 image embedding and Share Sheet integration

## Directory Structure
- `lab-src/`: Contains 12 incremental lab projects (`Lab01` to `Lab12`), each building on the previous step.
- `docs/`: Training materials, including Markdown lab exercises (`.md`), PowerPoint slides (`.pptx`), and images.
- `legacy/`: Older source code and lab files.

## Building and Running
The projects are designed to be opened in **RAD Studio / Delphi 10.3 Rio** or newer.

1. **Open a Lab Project:** Navigate to `lab-src/LabXX-...` and open the `.dproj` or `.dpr` file.
2. **Target Platform:** Select the desired target platform (Android, iOS, or Windows for prototyping).
3. **InterBase Setup:** Ensure IBLite or InterBase ToGo is configured. Some labs require running InterBase scripts found in the documentation or code.
4. **Build:** Use `Project -> Build [ProjectName]` or `Shift+F9`.
5. **Run:** Press `F9` or use the `Run` button.

### Command Line Build (MSBuild)
To build from the command line (assuming RAD Studio environment variables are set):
```powershell
# Example for Lab07 Win32 Debug
msbuild "lab-src\Lab07-Implement functionality of the IProjectData interface\FieldLogger07.dproj" /t:Build /p:Config=Debug /p:Platform=Win32
```

## Development Conventions
- **Naming:** Follows standard Delphi PascalCase conventions for types and components (e.g., `TProject`, `formMain`).
- **Interfaces:** Uses interfaces for CRUD operations (e.g., `IProjectData`, `ILogData`) to decouple UI from data implementation.
- **DataModules:** Centralizes database connections and FireDAC components in `uDataModule.pas`.
- **Forms/Frames:** UI is composed of FMX Forms and Frames for reusability across screens.
- **Asynchronous Patterns:** Mobile development often requires async dialogs and sensor handling.
- **Documentation:** Key units like `fieldlogger.data.pas` use XML documentation comments.

## Lab Sequence
1.  **Lab01:** Projects list view
2.  **Lab02:** Creating, editing, and deleting projects
3.  **Lab03:** Master-Detail for Projects and Entries
4.  **Lab04:** Log entry details screen
5.  **Lab05:** Log entry capture
6.  **Lab06:** Data Modeling and CRUD Interface
7.  **Lab07:** Implement functionality of the IProjectData interface
8.  **Lab08:** Authenticate user against InterBase
9.  **Lab09:** Working with Default FMX Styles
10. **Lab10:** StyleBook and Working with Custom Styles
11. **Lab11:** Report generation
12. **Lab12:** Sharing Files via email
