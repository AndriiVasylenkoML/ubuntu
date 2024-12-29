# How install old python:
To install a local version of Python (e.g., Python 3.10.12) in a virtual environment on Ubuntu without replacing the global system version of Python (e.g., Python 3.12.3), follow these steps:

1. Install Required Tools
```
sudo apt update
sudo apt install -y build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev \
libreadline-dev libffi-dev curl libbz2-dev libsqlite3-dev wget
```
2. Download Python [Source](https://www.python.org/ftp/python/)
```
wget https://www.python.org/ftp/python/3.10.12/Python-3.10.12.tgz
```

Extract the source code:
```
tar -xf Python-3.10.12.tgz
cd Python-3.10.12
```
3. Build and Install Python Locally
Custom directory:
```
./configure --prefix=$HOME/python-3.10.12 --enable-optimizations
```
```
make -j$(nproc)
make altinstall
```
- The make altinstall command prevents overwriting the default python3 binary.
- Python will be installed in the $HOME/python-3.10.12 directory.
4. Add Python to PATH
Append the following line to your ~/.bashrc or ~/.zshrc file:
```
export PATH=$HOME/python-3.10.12/bin:$PATH
```
Reload the shell configuration:
```
source ~/.bashrc
```
Check the Python version:
```
python3.10 --version
```
1. Install Required Tools
First, ensure you have the necessary tools to build Python from source:
```
sudo apt update
```
```
sudo apt install -y build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev \
libreadline-dev libffi-dev curl libbz2-dev libsqlite3-dev wget
```
2. Download Python Source
Visit the official Python releases page or use the following commands to download the source for Python 3.10.12:
```
wget https://www.python.org/ftp/python/3.10.12/Python-3.10.12.tgz
```
Extract the source code:
```
tar -xf Python-3.10.12.tgz
cd Python-3.10.12
```
3. Build and Install Python Locally
Configure the build to install Python to a custom directory:
```
./configure --prefix=$HOME/python-3.10.12 --enable-optimizations
Build and install Python (this may take some time):
```
```
make -j$(nproc)
make altinstall
```
The make altinstall command prevents overwriting the default python3 binary.
Python will be installed in the $HOME/python-3.10.12 directory.
4. Add Python to PATH
To use this version of Python, add it to your PATH. Append the following line to your ~/.bashrc or ~/.zshrc file:
```
export PATH=$HOME/python-3.10.12/bin:$PATH
```
Reload the shell configuration:

```
source ~/.bashrc
```
Check the Python version:

```
python3.10 --version
```

5. Create a Virtual Environment
Create a virtual environment:

```
python3.10 -m venv myenv
```

Activate the virtual environment:

```
source myenv/bin/activate
```
---
### Notes
1. Global Python Remains Unaffected:
Since Python 3.10.12 is installed locally and not as a global replacement, the system Python 3.12.3 remains untouched.
2. Use of pyenv (Optional):
Alternatively, you can use pyenv to manage multiple Python versions. This tool simplifies the installation and switching between Python versions.
Installation:

```
curl https://pyenv.run | bash
```

Add pyenv to your shell:

```
export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init --path)"
```

Install Python 3.10.12 with pyenv:

```
pyenv install 3.10.12
pyenv virtualenv 3.10.12 myenv
pyenv activate myenv
```
