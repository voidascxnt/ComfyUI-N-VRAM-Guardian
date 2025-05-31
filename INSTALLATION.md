# Installation Guide for ComfyUI VRAM Guardian

This guide will walk you through installing and setting up ComfyUI VRAM Guardian for optimal VRAM monitoring and emergency termination.

## 📋 Prerequisites

### System Requirements

- **Operating System**: Windows 10/11, Ubuntu 18.04+, or other Linux distributions
- **Python**: 3.8 or higher
- **GPU**: NVIDIA GPU with CUDA support (RTX series recommended)
- **VRAM**: 8GB minimum (16GB recommended for optimal thresholds)
- **ComfyUI**: Latest version installed and working

### Required Software

- **NVIDIA Drivers**: Latest stable drivers installed
- **CUDA Toolkit**: Compatible with your PyTorch installation
- **Git**: For cloning the repository
- **pip**: Python package manager

## 🚀 Quick Installation

### Method 1: Direct Clone (Recommended)

```bash
# Navigate to your ComfyUI custom_nodes directory
cd /path/to/ComfyUI/custom_nodes

# Clone the repository
git clone https://github.com/YOUR_USERNAME/ComfyUI-VRAM-Guardian.git

# Navigate to the project directory
cd ComfyUI-VRAM-Guardian

# Install dependencies
pip install -r requirements.txt

# Restart ComfyUI
```

### Method 2: ComfyUI Manager (Coming Soon)

1. Open ComfyUI
2. Go to **Manager** → **Install Custom Nodes**
3. Search for "VRAM Guardian"
4. Click **Install**
5. Restart ComfyUI

## 🔧 Detailed Installation Steps

### Step 1: Verify Prerequisites

**Check Python version:**
```bash
python --version
# Should show Python 3.8 or higher
```

**Check NVIDIA GPU:**
```bash
nvidia-smi
# Should display your GPU information
```

**Check ComfyUI installation:**
- Ensure ComfyUI starts without errors
- Verify you can run basic workflows

### Step 2: Install VRAM Guardian

**Clone the repository:**
```bash
cd ComfyUI/custom_nodes
git clone https://github.com/YOUR_USERNAME/ComfyUI-VRAM-Guardian.git
```

**Install Python dependencies:**
```bash
cd ComfyUI-VRAM-Guardian
pip install -r requirements.txt
```

### Step 3: Verify Installation

**Start ComfyUI:**
```bash
cd /path/to/ComfyUI
python main.py
```

**Check for VRAM Guardian:**
- Look for the VRAM Guardian overlay in the ComfyUI interface
- Check the console for initialization messages
- Verify the settings panel is accessible

## ⚙️ Configuration

### Initial Setup

1. **Open ComfyUI** with VRAM Guardian installed
2. **Locate the VRAM Guardian overlay** (top-right by default)
3. **Click the settings gear icon**
4. **Configure your settings:**

### Recommended Settings by GPU

**RTX 4080 (16GB VRAM):**
```
VRAM Threshold: 12GB (75% of total)
Monitoring Frequency: 500ms
Termination Method: Memory Guard Thread
Temperature Limit: 85°C
```

**RTX 3090 (24GB VRAM):**
```
VRAM Threshold: 18GB (75% of total)
Monitoring Frequency: 500ms
Termination Method: Memory Guard Thread
Temperature Limit: 83°C
```

**RTX 3080 (10GB VRAM):**
```
VRAM Threshold: 8GB (80% of total)
Monitoring Frequency: 300ms
Termination Method: Memory Guard Thread
Temperature Limit: 85°C
```

**RTX 3070 (8GB VRAM):**
```
VRAM Threshold: 6.5GB (81% of total)
Monitoring Frequency: 300ms
Termination Method: Memory Guard Thread
Temperature Limit: 85°C
```

### Advanced Configuration

**Custom Thresholds:**
- **Conservative**: 70% of total VRAM
- **Balanced**: 75% of total VRAM (recommended)
- **Aggressive**: 85% of total VRAM (higher risk)

**Monitoring Frequency:**
- **High Responsiveness**: 200-300ms (higher CPU usage)
- **Balanced**: 500ms (recommended)
- **Low Impact**: 1000ms (lower responsiveness)

## 🛠️ Troubleshooting

### Common Issues

**VRAM Guardian overlay not visible:**
```bash
# Check console for error messages
# Verify dependencies are installed:
pip list | grep pynvml
pip list | grep psutil
```

**Permission errors on Linux:**
```bash
# Add user to video group:
sudo usermod -a -G video $USER
# Logout and login again
```

**CUDA errors:**
```bash
# Verify CUDA installation:
nvcc --version
# Reinstall PyTorch if needed:
pip install torch --index-url https://download.pytorch.org/whl/cu118
```

### Log Files

**Enable debug logging:**
1. Edit `__init__.py`
2. Set `DEBUG = True`
3. Restart ComfyUI
4. Check console output for detailed logs

**Common log locations:**
- **Windows**: `ComfyUI/logs/vram_guardian.log`
- **Linux**: `~/.comfyui/logs/vram_guardian.log`

### Performance Issues

**High CPU usage:**
- Increase monitoring frequency (500ms → 1000ms)
- Disable memory leak detection temporarily
- Check for competing monitoring software

**Delayed termination:**
- Decrease monitoring frequency (500ms → 300ms)
- Switch to Signal-Based Interruption method
- Verify GPU drivers are up to date

## 🔄 Updating

### Manual Update
```bash
cd ComfyUI/custom_nodes/ComfyUI-VRAM-Guardian
git pull origin main
pip install -r requirements.txt --upgrade
```

### Automatic Updates (Future Feature)
- Enable auto-updates in settings panel
- Checks for updates on ComfyUI startup
- Prompts for user confirmation before updating

## 🧪 Testing Your Installation

### Basic Functionality Test

1. **Start ComfyUI** with a simple workflow
2. **Monitor VRAM usage** in the overlay
3. **Test settings panel** - change threshold temporarily
4. **Verify alerts** - watch for color changes as VRAM increases

### Emergency Termination Test

⚠️ **Warning**: This will forcefully terminate ComfyUI

1. **Load a large workflow** that uses significant VRAM
2. **Lower the threshold** to current usage level
3. **Start generation** and watch for automatic termination
4. **Reset threshold** to normal level afterward

### Performance Test

1. **Run normal workflows** for 30+ minutes
2. **Monitor CPU usage** - should remain under 0.5%
3. **Check memory leaks** - VRAM Guardian's own memory usage
4. **Verify responsiveness** - UI should remain smooth

## 📞 Getting Help

If you encounter issues during installation:

1. **Check the [Troubleshooting](#troubleshooting) section** above
2. **Search existing [Issues](https://github.com/YOUR_USERNAME/ComfyUI-VRAM-Guardian/issues)**
3. **Create a new issue** with:
   - Your system specifications
   - Installation steps attempted
   - Error messages or console output
   - Screenshots if relevant

## 🎉 Success!

Once installed successfully, you should see:
- ✅ VRAM Guardian overlay in ComfyUI
- ✅ Real-time VRAM monitoring
- ✅ Settings panel accessible
- ✅ No error messages in console
- ✅ Responsive interface during normal operation

**Your VRAM is now protected!** 🛡️