# VisionMol2

## Introduction
**VisionMol2** is a **visionOS-based (compatible with iOS/macOS)** 3D protein visualization and interaction app.  

The app supports loading PDB (Protein Data Bank) files, provides multiple visualization modes, measurement and annotation tools, window management, and basic collaboration features.  

---

## Core Features
- **Open PDB File**: Import local PDB files via system file picker  
- **Sample PDB File**: 4 sample PDB files included (1BNA, 1CRN, 1STP, 2PTC)  
- **Visualization Modes**: Ball-stick model, wireframe model, etc.  
- **Bond Display**: Toggle bond visibility  
- **Measurement Tool**: Select atoms and measure distances between atoms  
- **Annotation & Interaction**: Record and share molecular structure annotations  
- **Multi-window & Refresh**: Auto-open 3D window after loading  
- **Performance Mode**: Low-quality rendering mode for faster performance  
- **Collaboration**: Share molecular model state via MultipeerConnectivity framework  

---

## Platforms & Tech
- **Platforms**: visionOS 2, iOS 18, macOS 15  
- **Tech stack**: SwiftUI, RealityKit, Swift Concurrency, MultipeerConnectivity, SwiftPM  
- **PDB Parsing**: `Protein3DViewer/Protein/PDBParser.swift`  

---

## Project Structure
- `Protein3DViewer/` App logic (SwiftUI, AppModel, Views, Collaboration)  
- `AppModel.swift` Global state and display control  
- `ControlPanelView.swift` Control panel  
- `SamplePDBPickerView.swift` Sample file picker  
- `Protein/` Protein & PDB parsing logic  
- `PDBFile/` Sample PDB directory (1BNA, 1CRN, 1STP, 2PTC)  
- `RealityKitContent/` RealityKit content  
- `Package.swift` SwiftPM config  

---

## Quick Start
1. Open the project in Xcode and select a target device (visionOS / iOS / macOS).  
2. Build and run.  
3. In the app Control Panel:  
   - Tap **Sample PDB File** → Select a sample file  
   - Or tap **Open PDB File** → Import a local `.pdb` file  
4. Once loaded, the app will auto-open the 3D model window.  

---

## 🔑 App Review Testing Notes
For App Store Review, 4 sample PDB files are included: **1BNA, 1CRN, 1STP, 2PTC**.  

**Steps to test:**  
1. Open the app → Go to **Control Panel**  
   ![Sample PDB View](Docs/ControlPanel.png)

2. Tap **Sample PDB File**  
3. Select one of the samples (e.g. 1BNA)  
   ![Sample PDB View](Docs/Sample.png)

4. The molecule will be displayed in 3D. You can:  
   - Switch visualization modes  
   - Toggle bond display  
   - Use the measurement tool  
   - Add annotations  
   ![Sample PDB View](Docs/Show.png)

⚠️ All sample files are under 10KB, ensuring quick and smooth loading.  

---

## Usage Tips
- After loading, use the Control Panel to switch visualization modes and toggle bond display.  
- Measurement: tap atoms to mark measurement points and display distances between atoms.  
- Collaboration requires network connection and appropriate permission support.  

---

## Support & Feedback
- **Support URL**: https://visionmol2support.notion.site/VisionMol2-Support-289c2abcef1280f1a197ebe2d6a7e178

---

## Build & Resources
- Project managed via SwiftPM  
- `Package.swift` packs samples via `resources: [.process("PDBFile")]`  
- Resource loading mechanism: `Bundle.module` (SwiftPM) → `Bundle.main` (App)  

---

## Acknowledgements & License
- PDB format maintained by **RCSB PDB** (Research Collaboratory for Structural Bioinformatics Protein Data Bank); sample files for demonstration and testing purposes only  
- License available in the root `LICENSE` file  
