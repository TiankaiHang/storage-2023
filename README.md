# storage-2023

## Init script

```bash
# tmux
cd
git clone https://github.com/gpakosz/.tmux.git
ln -s -f .tmux/.tmux.conf
cp .tmux/.tmux.conf.local .

# cv2
sudo apt-get update && sudo apt-get install ffmpeg libsm6 libxext6  -y

# htop
sudo apt-get install htop -y

# azcopy
if command -v azcopy >/dev/null 2>&1; then
    echo "azcopy exists"
else
    wget https://aka.ms/downloadazcopy-v10-linux --no-check-certificate -O azcopy.tar;
    mkdir azcopy10 ;
    tar -xvf azcopy.tar -C azcopy10/;
    sudo cp azcopy10/*/azcopy /usr/bin/;
    sudo azcopy --version;
fi
```

```bash
sudo /opt/conda/bin/pip uninstall torch torchvision torchaudio -y 
# pip install torch==2.0.1+cu118 torchvision==0.15.2+cu118 torchaudio==2.0.2 --index-url https://download.pytorch.org/whl/cu118

source activate
conda create -n torch python=3.9 -y
conda activate torch

pip install torch==2.0.1+cu118 torchvision==0.15.2+cu118 torchaudio==2.0.2 --index-url https://download.pytorch.org/whl/cu118

# (Optional) Makes the build much faster
pip install ninja
# Set TORCH_CUDA_ARCH_LIST if running and building on different GPU types
pip install -v -U git+https://github.com/facebookresearch/xformers.git@main#egg=xformers
# (this can take dozens of minutes)
```
