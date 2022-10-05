# Environment tested on:
 * MacOS 12.5.1, M1 Pro MacBook Pro, 32GB RAM
 * Python 3.10.7

# Steps to reproduce:

```
git clone https://github.com/samheather/pyinstaller-issue-demo
cd pyinstaller-issue-demo
python3 -m venv venv
source venv/bin/activate
pip install -r requirements_m1.txt

# next install protobuf from source otherwise pip gives a non-M1 binary
pip install --no-binary :all: protobuf==3.19.4 --ignore-installed

#Finally, try running pyinstaller (contained within the 2-line `build.sh`):
chmod +x build.sh
./build.sh
```

In case you need to run the built executable:
```
./dist/diffusionbee_backend/diffusionbee_backend

# Wait for it to start - first load would involve downloading some model weights
# Once you get to the following console readout: `sdbk inrd`, enter the following prompt:

b2py t2im {"prompt":"cat"}

# If things are still failing, this will execute with CPU and not GPU.
```
