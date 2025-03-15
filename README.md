# PySparkSetupTutorial
PySpark Setup Tutorial

# Installing and Setting Up PySpark

This guide provides step-by-step instructions for installing and setting up PySpark on a Linux system.

## Prerequisites

- Ensure you have Python and pip installed.
- This guide assumes you are using a Debian-based Linux distribution (e.g., Ubuntu).

## Installation Steps

### Step 1: Install OpenJDK 11

First, update your package list and install OpenJDK 11:

```bash
# Update package list
sudo apt-get update

# Install OpenJDK 11
sudo apt-get install openjdk-11-jdk -y
```

### Step 2: Set JAVA_HOME for OpenJDK 11

Configure the Java environment by setting `JAVA_HOME`. You may need to select the correct Java version if multiple versions are installed:

```bash
# Configure Java alternatives
sudo update-alternatives --config java

# Set JAVA_HOME (assuming OpenJDK 11 is installed)
export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
```

### Step 3: Apply Changes

Apply the environment changes by sourcing your shell configuration file:

```bash
# Apply changes to the current shell session
source ~/.bashrc
```

### Step 4: Verify Java Installation

Check if Java is correctly installed:

```bash
# Verify Java version
java -version
```

### Step 5: Install PySpark

Install PySpark using pip:

```bash
# Install PySpark
pip install pyspark
```

### Step 6: Test PySpark

Start a Python interactive console:

```python
# Start Python interactive console
python
```

Test PySpark:

```python
# Test PySpark
from pyspark.sql import SparkSession
spark = SparkSession.builder.getOrCreate()
print(spark.version)
```

If the Spark version prints without errors, PySpark is set up correctly.

---

### Notes

- Ensure that your `JAVA_HOME` path matches the actual installation directory of OpenJDK 11.
- If you encounter issues with Java alternatives, you might need to manually configure the `JAVA_HOME` variable in your shell configuration file (`~/.bashrc` or similar).
- PySpark requires Java to be installed and properly configured.
