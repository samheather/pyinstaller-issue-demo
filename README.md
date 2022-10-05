# Tested using Python 3.10.7 and 3.9.x

# Steps to reproduce:

```
git clone https://github.com/samheather/pyinstaller-issue-demo
cd pyinstaller-issue-demo
python3 -m venv venv
source venv/bin/activate
pip install -r requirements_m1.txt

# next install protobuf from source otherwise pip gives a non-M1 binary
pip install --no-binary :all: protobuf==3.19.4 --ignore-installed

#Finally, try running pyinstaller:
chmod +x build.sh
./build.sh
```
