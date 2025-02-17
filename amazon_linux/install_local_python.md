# ✅ **Install Local Python 3.10 on Amazon Linux**  

## **1️⃣ Install Required Dependencies**  
First, update your system and install necessary build tools:  

```bash
sudo yum groupinstall -y "Development Tools"
sudo yum install -y gcc gcc-c++ make zlib-devel bzip2 bzip2-devel readline-devel \
sqlite sqlite-devel openssl-devel xz xz-devel libffi-devel
```

---

## **2️⃣ Download and Extract Python Source**  
Now, download Python 3.10.12 from the official site:  

```bash
cd /usr/local/src
sudo wget https://www.python.org/ftp/python/3.10.12/Python-3.10.12.tgz
sudo tar -xf Python-3.10.12.tgz
cd Python-3.10.12
```

---

## **3️⃣ Build and Install Python Locally**  
To install Python **locally** (without replacing system Python), use the `--prefix` option:

```bash
./configure --prefix=$HOME/python-3.10.12 --enable-optimizations
make -j$(nproc)
make altinstall  # Prevents overwriting system python
```

Python will be installed in `$HOME/python-3.10.12`.

---

## **4️⃣ Add Python to PATH**  
Append the following line to `~/.bashrc` or `~/.zshrc`:

```bash
echo 'export PATH=$HOME/python-3.10.12/bin:$PATH' >> ~/.bashrc
source ~/.bashrc
```

Now check the Python version:

```bash
python3.10 --version
```

---

## **5️⃣ (Optional) Create a Virtual Environment**  
If you need a virtual environment:

```bash
python3.10 -m venv myenv
source myenv/bin/activate
```

---

## ✅ **Alternative: Use `pyenv` to Manage Python Versions**  
Instead of manually compiling, you can use **pyenv**:  

```bash
curl https://pyenv.run | bash
```

Add the following to your `~/.bashrc`:

```bash
export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init --path)"
```

Then install Python 3.10.12:

```bash
pyenv install 3.10.12
pyenv virtualenv 3.10.12 myenv
pyenv activate myenv
```
