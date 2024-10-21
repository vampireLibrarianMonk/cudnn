# cuDNN Installation

### 1. Download the cuDNN `.deb` Package:
Visit the [NVIDIA cuDNN website](https://developer.nvidia.com/cudnn) to download the cuDNN `.deb` package for Ubuntu. Make sure to choose the correct version that matches your CUDA installation.

### 2. Install the cuDNN `.deb` Package:
Navigate to the directory where the `.deb` file is located and install it:
```bash
sudo dpkg -i cudnn-local-repo-ubuntu<version>-<version-details>.deb
```

### 3. Add the cuDNN Repository Key:
Add the cuDNN repository key to your system:
```bash
sudo cp /var/cudnn-local-repo-ubuntu<version>-<version-details>/cudnn-local-<keyring-id>-keyring.gpg /usr/share/keyrings/
```

### 4. Update the Package List:
Update the package list to include the cuDNN repository:
```bash
sudo apt-get update
```

### 5. Install cuDNN Packages:

1. Install the runtime library:
```bash
sudo apt-get install libcudnn8
```

2. Optionally, install the developer library and samples:
```bash
sudo apt-get install libcudnn8-dev libcudnn8-samples
```

### 6. Verify cuDNN Installation:
To verify that cuDNN is installed correctly, run the following:
```bash
cp -r /usr/src/cudnn_samples_v8/ $HOME
cd $HOME/cudnn_samples_v8/mnistCUDNN
make clean && make
./mnistCUDNN
```

If the sample runs successfully, cuDNN is installed and working correctly.
