# The Geeked Out Quantizer 2.0
🎯 Next-Generation GGUF Model Quantization

The Geeked Out Quantizer 2.0 is a comprehensive Python/Electron-based quantization toolkit for GGUF (GPT Generated Universal Format) large language models. Version 2.0 represents a complete rewrite and significant enhancement over version 1.0, offering unprecedented control, flexibility, and performance in model quantization.

## 📊 Core Features
### 33 Quantization Targets Across 4 Method Groups

| Method Group | Targets | Description |
|-------------|---------|-------------|
| **Ternary** | Ternary | Binary-like weights reduced to 3 levels (-1, 0, 1) |
| **K-Quants** | Q2_K, Q3_K, Q3_K_S, Q4_K, Q4_K_M, Q5_K, Q6_K, Q7_K, Q8_K | Krause quantization presets optimized for speed/quality balance |
| **IQ Series** | IL\_S, IQ2_S, IQ3_S, IQ4_S, IQ5_S | Importance-aware quantization with superior quality retention |
| **Float-Copy** | F16, BF16 | Floating-point preservation for lossless operations |

## 🖥️ Electron Desktop Interface
Cross-platform desktop application (Windows, macOS, Linux)
Modern UI built with React + Electron
Real-time quantization progress monitoring
Batch processing queue management
IMatrix generation and management

## ⚡ IMatrix Support
Importance Matrix generation for weight prioritization
GPU acceleration support (-IMatrixGpuLayers 99)
Configurable layer selection for targeted quantization
Enhanced quality retention for critical model layers

## 📦 Preset Profiles

| Profile | Target | Use Case |
|---------|--------|----------|
| **Q4_K_M Focus** | Q4_K_M | Balanced quality/speed (default recommendation) |
| **Plus** | Q4_K_M + IMatrix | Enhanced quality with importance weighting |
| **Archive** | Q8_K | Maximum quality for long-term storage |

## 🚀 Quick Start
### 5-Minute Setup

```bash
# Clone the repository
git clone https://github.com/LGxNDaRY-GeekedOutAi/The-Geeked-Out-Quantizer-2.0.git

# Navigate to project directory
cd The-Geeked-Out-Quantizer-2.0

# Install dependencies
npm install

# Start the application
npm start

# Or use the pre-built Windows installer
# Download the latest release from the GitHub Releases page.
```

## 🛠️ Usage Examples

### Basic Quantization
```bash
# Quantize a model to Q4_K_M (recommended baseline)
.\run.ps1 -Model "path/to/model.gguf" -Target Q4_K_M

# Quantize with IMatrix support
.\run.ps1 -Model "path/to/model.gguf" -Target Q4_K_M -IMatrixGpuLayers 99
```

### Batch Processing
```bash
# Quantize multiple models from a directory
.\quantize-all.ps1 -Directory "C:\Models\GGUF" -Preset Plus
```

### Importance Matrix Generation
```bash
# Generate IMatrix for first 99 layers using GPU acceleration
.\Generate-IMatrix.ps1 -Model "path/to/model.gguf" -Layers 99 -GPU
```

## 📦 Installation

### From Source (Recommended for Customization)
```bash
# Clone repository
git clone https://github.com/LGxNDaRY-GeekedOutAi/The-Geeked-Out-Quantizer-2.0.git

# Install Node.js dependencies
npm install

# Build the Electron application
npm run build

# Start the application
npm start
```

### Pre-built Binaries
Download the appropriate installer for your platform from the Releases page.

**Required Dependencies:**
- Python 3.8+
- GGUF model files (.gguf format)
- GPU with 4GB+ VRAM for accelerated quantization (optional but recommended)
- OpenMP runtime (libomp140.x86_64.dll included)

## 📋 Preset Profile Details

### Q4_K_M Focus
**Target:** Q4_K_M with IMatrix
- **Quality Enhancement:** Importance matrix weighting for critical layers
- **Additional VRAM:** ~500MB for IMatrix data
- **Best For:** Users who want Q4 quality with extra validation

### Archive Profile
- **Target:** Q8_K (8-bit Krause)
- **Quality:** Near-lossless preservation
- **VRAM Usage:** ~8GB per layer
- **Best For:** Archival, fine-tuning preparation, maximum fidelity

## 🔧 Configuration

### package.json Scripts

| Script | Description |
|--------|-------------|
| **start** | Launch Electron application |
| **build** | Package app for target platform |
| **dev** | Start development mode with hot-reload |
| **test** | Run unit tests |
| **lint** | Code quality checks |

### PowerShell Profile Files
( build,sort "admitted/*.json")