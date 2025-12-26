# VisionMol-Apple-VR

## 项目简介
**VisionMol-Apple-VR** 是一个基于 **visionOS**（兼容 iOS / macOS）的 3D 蛋白质可视化与交互应用。  

应用支持加载 PDB（Protein Data Bank）文件，提供多种分子显示模式、测量与标注功能、窗口管理，以及基础的多人协作能力。  

---

## 核心功能
- **打开 PDB 文件**：通过系统文件选择器导入 PDB 文件  
- **示例 PDB 文件**：内置 4 个示例（1BNA, 1CRN, 1STP, 2PTC）  
- **多种显示模式**：球棍模型、线框模型等  
- **化学键显示**：支持开关化学键显示  
- **测量工具**：选择原子并测量原子间距离  
- **标注与交互**：记录和共享分子结构标注  
- **多窗口与刷新**：加载后自动打开 3D 窗口  
- **性能模式**：低质量渲染模式提升运行流畅度  
- **协作功能**：通过 MultipeerConnectivity 框架共享分子模型状态  

---

## 平台与技术
- **平台**：visionOS 2、iOS 18、macOS 15  
- **技术栈**：SwiftUI, RealityKit, Swift Concurrency, MultipeerConnectivity, SwiftPM  
- **PDB 解析**：`Protein3DViewer/Protein/PDBParser.swift`  

---

## 目录结构
- `Protein3DViewer/` 应用与核心逻辑（SwiftUI, AppModel, Views, Collaboration）  
- `AppModel.swift` 全局状态与显示控制  
- `ControlPanelView.swift` 控制面板  
- `SamplePDBPickerView.swift` 示例文件选择  
- `Protein/` 分子与 PDB 解析逻辑  
- `PDBFile/` 示例 PDB 文件目录（1BNA, 1CRN, 1STP, 2PTC）  
- `RealityKitContent/` RealityKit 3D 内容  
- `Package.swift` SwiftPM 配置  

---

## 快速开始
1. 使用 Xcode 打开工程并选择目标设备（visionOS / iOS / macOS）  
2. 构建并运行  
3. 在应用控制面板中：  
   - 点击 **Sample PDB File** → 选择示例文件  
   - 或点击 **Open PDB File** → 导入本地 `.pdb` 文件  
4. 加载完成后，应用会自动打开 3D 模型窗口  

---

## 🔑 审核指引
为便于 App Store 审核，本应用已内置 4 个示例 PDB 文件：**1BNA, 1CRN, 1STP, 2PTC**。  

**测试步骤：**  
1. 打开应用 → 进入 **控制面板**  
   ![Sample PDB View](Docs/ControlPanel.png)

2. 点击 **Sample PDB File**  
3. 选择一个示例文件（如 1BNA）  
   ![Sample PDB View](Docs/Sample.png)

4. 分子会以 3D 模型显示，支持：  
   - 切换显示模式  
   - 开关化学键显示  
   - 使用测量工具  
   - 添加标注  
   ![Sample PDB View](Docs/Show.png)

⚠️ 所有示例文件均小于 10KB，确保加载快速流畅。  

---

## 使用提示
- 加载模型后，可在控制面板切换显示模式、开关化学键显示  
- 测量功能：点击原子即可标记测量点并显示原子间距离  
- 协作功能需要网络连接与相应权限支持  

---

## 网址
- **支持网址**: https://github.com/WangLabforComputationalBiology/VisionMol-Apple-VR.git  

---

## 构建与资源
- 项目使用 SwiftPM 管理依赖与资源  
- `Package.swift` 使用 `resources: [.process("PDBFile")]` 打包示例文件  
- 资源加载机制：SwiftPM 环境使用 `Bundle.module`，App 环境使用 `Bundle.main`  

---

## 致谢与许可
- PDB 文件格式由 **RCSB PDB** (Research Collaboratory for Structural Bioinformatics Protein Data Bank) 维护；示例文件仅用于演示与测试  
- 许可证请参考根目录下的 `LICENSE` 文件  
