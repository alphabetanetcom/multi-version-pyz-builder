# Multi-Version PYZ Builder Script Documentation

[![DOI](https://zenodo.org/badge/890990481.svg)](https://doi.org/10.5281/zenodo.14194336)
[![License](https://img.shields.io/badge/license-Custom-blue.svg)](LICENSE.md)
[![Python Version](https://img.shields.io/badge/python-3.6%2B-blue)](https://www.python.org/downloads/)
[![Cross-Platform](https://img.shields.io/badge/cross--platform-yes-brightgreen.svg)](#4-detailed-description-of-operation)
[![Multi-Version](https://img.shields.io/badge/multi--version-support-brightgreen.svg)](#3-main-functions-of-the-script)
[![Code Protection](https://img.shields.io/badge/code-protection-green.svg)](#3-main-functions-of-the-script)
[![Secure Code](https://img.shields.io/badge/secure-code-green.svg)](#1-introduction)
[![Code Obfuscation](https://img.shields.io/badge/code-obfuscation-blue.svg)](#6-recommendations-and-best-practices)
[![Secure Transfer](https://img.shields.io/badge/secure-transfer-blue.svg)](#1-introduction)
[![Encryption](https://img.shields.io/badge/encryption-enabled-brightgreen.svg)](#6-recommendations-and-best-practices)

*Version: 1.3\
© 2024 αβ.net (alphabetanet.com) - Alpha Beta Network. All Rights Reserved.*

---

**Note:** This project is currently in **Beta Testing** and available for free.

**Table of Contents**

- [1. Introduction](#1-introduction)
- [2. Installation](#2-installation)
  - [2.1 Installing Required Packages](#21-installing-required-packages)
- [3. Main Functions of the Script](#3-main-functions-of-the-script)
- [4. Detailed Description of Operation](#4-detailed-description-of-operation)
- [5. Usage Examples](#5-usage-examples)
  - [5.1 Basic Usage](#51-basic-usage)
  - [5.2 Example with Detailed Steps](#52-example-with-detailed-steps)
- [6. Recommendations and Best Practices](#6-recommendations-and-best-practices)
- [Appendix A: Installation of Required Packages](#appendix-a-installation-of-required-packages)
- [Appendix B: Real-World Example - Universal Python Module with Multi-Version Compatibility](#appendix-b-real-world-example---universal-python-module-with-multi-version-compatibility)
- [Appendix C: Contact Information](#appendix-c-contact-information)

---

# 1. Introduction

The **Multi-Version PYZ Builder Script** is a command-line tool designed to create a **Universal Python Module** optimized for **cross-platform** and **multi-version compatibility**. It allows developers to bundle multiple **protected** `.pyc` files—each corresponding to a different Python version—into a single `.pyz` archive. This approach significantly enhances **Python code security** by using previously compiled and protected versions of code, making it more difficult for others to reverse-engineer or analyze the source code.

**Key features of the script include:**

- **Cross-Platform Compatibility**: The generated `.pyz` files can be executed on any operating system where Python 3.6+ is installed, including Windows, macOS, and Linux/Unix systems.

- **Multi-Version Support**: Supports multiple Python versions by including protected `.pyc` files for each targeted Python version. Automatically detects the current Python interpreter version at runtime and executes the corresponding code.

- **Enhanced Code Protection**: Integrates with the [**Local Python Code Protector Script**](https://github.com/alphabetanetcom/local-python-code-protector) or any other protection tool to use previously compiled and protected `.pyc` files, adding layers of **code obfuscation** and **encryption**.

- **Secure Code Sharing**: Facilitates **secure code distribution** without exposing the original source code, aligning with **Python code security best practices**.

This tool is ideal for developers who need to distribute their Python modules securely across different platforms and Python versions while maintaining a high level of code protection.

---

# 2. Installation

Before using the Multi-Version PYZ Builder Script, ensure that you have **Python 3.6+** installed on your system.

## 2.1 Installing Required Packages

The script requires the following Python packages:

- **requests**

- **psutil**

- **cryptography**

- **astor**

You can install them using `pip`:

```bash
pip install requests psutil cryptography astor
```

Ensure that you are using the correct version of `pip` associated with your Python 3 installation. If you are using a virtual environment, activate it before installing the packages.

**Note:** The script automatically checks for required packages and installs them if they are missing.

---

# 3. Main Functions of the Script

The Multi-Version PYZ Builder Script provides the following functionalities:

- **Bundling Multiple Protected `.pyc` Files**: Combines multiple `.pyc` files, each corresponding to a different Python version, into a single `.pyz` archive.

- **Automatic Python Version Detection**: The generated `.pyz` file automatically detects the Python version at runtime and executes the appropriate protected `.pyc` file.

- **Integration with Code Protection Tools**: Designed to work seamlessly with protected `.pyc` files generated by the **Local Python Code Protector Script** or similar tools, enhancing code security through obfuscation and encryption.

---

# 4. Detailed Description of Operation

## 4.1 Prerequisites

To use the Multi-Version PYZ Builder Script effectively, you need:

- **Protected `.pyc` Files**: Compiled and protected `.pyc` files for each Python version you wish to support. These can be generated using the **Local Python Code Protector Script**.

- **Naming Convention**: The naming convention for the `.pyc` files should follow this pattern:

  ```
  module_name_python36.pyc   (for Python 3.6)
  module_name_python37.pyc   (for Python 3.7)
  module_name_python38.pyc   (for Python 3.8)
  module_name_python39.pyc   (for Python 3.9)
  module_name_python310.pyc  (for Python 3.10)
  module_name_python311.pyc  (for Python 3.11)
  module_name_python312.pyc  (for Python 3.12)
  module_name_python313.pyc  (for Python 3.13)
  ```

- **Script Placement**: Place the `multi_version_pyz_builder.py` script in the same directory as the compiled `.pyc` files.

## 4.2 How the Script Works

1. **Scans for Protected `.pyc` Files**: The script searches the current directory for all `.pyc` files that match the naming pattern.

2. **Groups Files by Module Name**: Files are grouped based on their base module names.

3. **Generates a Multi-Version `__main__.py`**: For each module, the script generates a `__main__.py` file that contains code to detect the Python version at runtime and execute the corresponding `.pyc` file.

4. **Creates the `.pyz` Archive**: Packages the `__main__.py` and the protected `.pyc` files into a single `.pyz` archive using Python's `zipapp` module.

5. **Outputs the Universal Module**: The resulting `.pyz` file is a universal Python module that can be executed on different platforms and Python versions.

---

# 5. Usage Examples

## 5.1 Basic Usage

Assuming you have prepared the protected `.pyc` files for different Python versions, follow these steps:

1. **Place the Script and `.pyc` Files Together**: Ensure that the `multi_version_pyz_builder.py` script and your protected `.pyc` files are in the same directory.

2. **Run the Script**:

   ```bash
   python multi_version_pyz_builder.py
   ```

3. **Output**:

   - The script will generate a `.pyz` file for each module found. For example, if your module is named `my_module`, the output will be `my_module.pyz`.

   - The script will display messages indicating the progress and successful creation of the `.pyz` file.

## 5.2 Example with Detailed Steps

**Step 1: Prepare Protected `.pyc` Files**

Use the **Local Python Code Protector Script** to generate protected `.pyc` files for your module for each desired Python version.

```bash
# Example for Python 3.6
python local_python_code_protector.py -f my_module.py
```

Repeat the process for other Python versions, adjusting as necessary (e.g., using virtual environments with different Python versions).

**Step 2: Place Files in the Same Directory**

Ensure that all the `my_module_python*.pyc` files and `multi_version_pyz_builder.py` are in the same directory.

**Step 3: Run the Multi-Version PYZ Builder Script**

```bash
python multi_version_pyz_builder.py
```

**Step 4: Distribute the `my_module.pyz` File**

The generated `my_module.pyz` file can now be distributed and executed on any platform with Python 3.6+.

**Step 5: Running the Universal Module**

Users can execute the module using:

```bash
python my_module.pyz
```

---

# 6. Recommendations and Best Practices

- **Enhance Protection with Multiple Layers**: To strengthen the security of your code, consider applying the **Local Python Code Protector Script** multiple times to each `.pyc` file before using them with the Multi-Version PYZ Builder. This adds additional layers of protection through obfuscation and encryption.

- **Ensure Version Compatibility**: Generate protected `.pyc` files for all Python versions you intend to support. This guarantees that your module will run seamlessly across different environments, adhering to **cross-platform compatibility**.

- **Test Thoroughly**: Before distributing the universal `.pyz` file, test it on different operating systems and Python versions to confirm functionality and compatibility.

- **Follow Naming Conventions**: Adhere strictly to the naming conventions for `.pyc` files to ensure that the script correctly identifies and packages them.

- **Maintain Secure Code Practices**: Combine this approach with other **Python code security best practices** to maximize protection and ensure the integrity of your code.

---

# Appendix A: Installation of Required Packages

The `multi_version_pyz_builder.py` script requires the following Python packages:

- **requests**

- **psutil**

- **cryptography**

- **astor**

**Installing Packages with pip**

You can install these packages using the following command:

```bash
pip install requests psutil cryptography astor
```

Ensure that you are using the correct version of `pip` associated with your Python 3 installation. If you are working within a virtual environment, activate it before installing the packages.

---

# Appendix B: Real-World Example - Universal Python Module with Multi-Version Compatibility

In this appendix, we present a **real-world example** of using the Multi-Version PYZ Builder Script to create a **secure, cross-platform, and multi-version compatible Python module**.

## B.1 Overview

The file `system_hardware_id_generator.pyz` is a universal Python module that encapsulates multiple protected `.pyc` files, each corresponding to a different Python version. It is optimized for **cross-platform** and **multi-version compatibility**, automatically detecting the current Python interpreter version and executing the appropriate protected module.

## B.2 Construction of the Universal Module

### B.2.1 Protected `.pyc` Files

Eight protected `.pyc` files were generated for different Python versions using the **Local Python Code Protector Script**. The protection process was applied **twice** to each file to strengthen the security.

**Protected files:**

- `system_hardware_id_generator_python36.pyc` (Python 3.6)

- `system_hardware_id_generator_python37.pyc` (Python 3.7)

- `system_hardware_id_generator_python38.pyc` (Python 3.8)

- `system_hardware_id_generator_python39.pyc` (Python 3.9)

- `system_hardware_id_generator_python310.pyc` (Python 3.10)

- `system_hardware_id_generator_python311.pyc` (Python 3.11)

- `system_hardware_id_generator_python312.pyc` (Python 3.12)

- `system_hardware_id_generator_python313.pyc` (Python 3.13)

### B.2.2 Using Multi-Version PYZ Builder

The integration of these files into a single `.pyz` archive was achieved using the **Multi-Version PYZ Builder**.

**Steps:**

1. **Place Files in the Same Directory**:

   - Ensure that all the `system_hardware_id_generator_python*.pyc` files and `multi_version_pyz_builder.py` are in the same directory.

2. **Run the Multi-Version PYZ Builder Script**:

   ```bash
   python multi_version_pyz_builder.py
   ```

3. **Output**:

   - The script generates `system_hardware_id_generator.pyz`.

## B.3 Using the Universal Module

**To generate the Hardware ID (HWID) on any supported platform:**

1. **Execute the `.pyz` file**:

   ```bash
   python system_hardware_id_generator.pyz
   ```

2. **The module will display the HWID**:

   ```
   Your Hardware ID (HWID) is: 123456789012345678
   ```

**Notes:**

- Ensures **secure code execution** without exposing the original source code.

- Compatible with multiple Python versions, making it an ideal solution for environments with varied Python installations.

## B.4 Advantages of Using a Universal `.pyz` File

- **Secure Code Sharing**: The source code is deeply protected from analysis and recovery, ensuring high levels of **Python code security** and **code obfuscation**.

- **Simplified Distribution**: Only one `.pyz` file needs to be distributed, regardless of the Python version or operating system of the end-user.

- **Enhanced Protection**: By using pre-compiled and protected versions of the code, it adds an extra layer of security against decompilation and unauthorized access.

---

# Appendix C: Contact Information

If you experience issues or have questions not covered in this
documentation, please contact the **Alpha Beta Network Research Team**.

-   **Website:** https://alphabetanet.com \| https://αβ.net

-   **Official Telegram Channel**: https://t.me/alphabetanetcom

Stay connected to receive updates, provide feedback, and get early
access to extended functionality.

------------------------------------------------------------------------

© 2024 αβ.net (alphabetanet.com) - **Alpha Beta Network**. All Rights
Reserved.
