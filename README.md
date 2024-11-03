
# Termux Aircrack-ng Installer
![License](https://img.shields.io/badge/license-MIT-blue)
![Platform](https://img.shields.io/badge/platform-Termux-green)

A guide to manually install the `aircrack-ng` package on Termux, providing a solution to install `aircrack-ng` manually after it was removed from the Termux package repository.

## Problem
When trying to install `aircrack-ng` on Termux using:
```bash
pkg install aircrack-ng
```
You might encounter the following error:
```
E: Unable to locate package aircrack-ng
```

![Installation Error](https://user-images.githubusercontent.com/95903270/218306989-1c45813f-6f59-44c7-843e-d95160018101.jpg)

## Reason for the Issue
The Termux repository maintainers have removed the "aircrack-ng" package from the root repository, which results in this error.

## Solution
To resolve this, we’ll install `aircrack-ng` manually in Termux following these steps.

---

## Installation Guide

### Prerequisites
- Ensure that Termux is installed on your Android device.

### Steps
1. **Update Termux**: Before starting, update the package lists:
   ```bash
   pkg update && pkg upgrade
   ```
2. **Download Required Packages**:
   Install any dependencies needed to compile `aircrack-ng`.
   ```bash
   pkg install libnl libssl-dev
   ```
3. **Download Aircrack-ng Source**:
   Download the latest version of `aircrack-ng` from the official repository.
   ```bash
   git clone https://github.com/aircrack-ng/aircrack-ng.git
   cd aircrack-ng
   ```
4. **Build and Install**:
   Follow these steps to compile and install `aircrack-ng`.
   ```bash
   ./configure
   make
   make install
   ```

---

## Usage
After installation, you can start using `aircrack-ng` with the following command:
```bash
aircrack-ng [options] <inputfile>
```

### Example
To crack a `.cap` file with a known dictionary:
```bash
aircrack-ng -w wordlist.txt -b <target_bssid> capture.cap
```

## Features
- **Manual Installation**: Overcomes the repository limitations by manually installing `aircrack-ng`.
- **Quick Setup**: Provides a step-by-step setup process.
- **Compatibility**: Works directly within the Termux environment on Android.

---

## FAQ

**Q: I am getting an error during compilation. What should I do?**  
A: Ensure that all dependencies are correctly installed. Running `pkg install libnl libssl-dev` again might help resolve missing packages.

**Q: Can I update `aircrack-ng` using the same process?**  
A: Yes, just pull the latest version from the repository and repeat the build steps.

---

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact
For questions or support, please reach out to:
- **Email**: support@example.com
- **GitHub Issues**: [Open an issue](https://github.com/your-repo/issues)

---

Happy cracking with `aircrack-ng` on Termux!
