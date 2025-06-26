
---

### **Setting Up Python in Visual Studio Code (VSCode)**

---



1. **Install Visual Studio Code (VSCode):**

   - Download VSCode from [VSCode Download Page](https://code.visualstudio.com/Download).
   - Select the installer for your operating system:
     - Linux: `.deb` or `.rpm` package.
     - macOS: `.dmg` file.
     - Windows: `.exe` file.

2. **Install Python Extension in VSCode:**

   - Open VSCode and click on the **Extensions** icon (or press `Ctrl+Shift+X`).
   - Search for **Python** and install the extension by Microsoft.

3. **Set Up Python in VSCode:**

   - Install Python:
     - **Linux:**
       ```bash
       sudo apt update
       sudo apt install python3 python3-pip
       ```
     - **macOS:**
       Install Homebrew if not already installed:
       ```bash
       /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
       ```
       Then use Homebrew:
       ```bash
       brew install python
       ```
     - **Windows:**
       Download Python from the [Official Python Website](https://www.python.org/downloads/).

   - Configure Python Interpreter in VSCode:
     - Press `Ctrl+Shift+P` → Type `Python: Select Interpreter` → Select Python 3.x.x.

4. **Run Python Code in VSCode:**

   - Open a Python file (`example.py`) in VSCode.
   - Click the **Run** button (▶) or press `F5`.

5. **Optional: Create a Virtual Environment:**

   - Create and activate:
     ```bash
     python3 -m venv myenv
     source myenv/bin/activate  # Linux/macOS
     myenv\Scripts\activate     # Windows
     ```
   - Install packages:
     ```bash
     pip install numpy pandas
     ```

6. **Troubleshooting:**

   - Python Not Detected: Ensure Python is installed and in your `PATH`.
   - Extension Not Loading: Reload VSCode or reinstall the Python extension.

7. **Resources:**

   - Official Guide: [VSCode Python Guide](https://code.visualstudio.com/docs/python/python-tutorial)
   - Videos:
     - [Python in VSCode](https://www.youtube.com/watch?v=D2cwvpJSBX4)
     - [Virtual Environment Setup](https://www.youtube.com/watch?v=Kg1Yvry_Ydk)

---
