# storage-2023

## diffusers

### diable tqdm in pipeline

```bash
pipeline.set_progress_bar_config(disable=True)
```

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

install cuda
```bash
lsb_release -a
wget https://developer.download.nvidia.com/compute/cuda/11.8.0/local_installers/cuda_11.8.0_520.61.05_linux.run
sudo sh cuda_11.8.0_520.61.05_linux.run
```


## python 代码自动排版

1. **Black** - Black 是一个无情的 Python 代码格式化程序，它采取了一个样式指南，并自动重新格式化您的代码以与该样式保持一致。
   - 安装：`pip install black`
   - 使用：在命令行中运行 `black your_script.py`

2. **autopep8** - autopep8 会自动格式化 Python 代码以符合 PEP 8 风格指南。
   - 安装：`pip install autopep8`
   - 使用：在命令行中运行 `autopep8 --in-place --aggressive --aggressive your_script.py`

3. **YAPF (Yet Another Python Formatter)** - YAPF 由 Google 开发，它会重写你的 Python 程序，以形成最佳的排版格式，与 Black 类似。
   - 安装：`pip install yapf`
   - 使用：在命令行中运行 `yapf --in-place your_script.py`

4. **isort** - isort 对 Python 的 import 语句进行排序和分类，它可以与以上的格式化工具配合使用。
   - 安装：`pip install isort`
   - 使用：在命令行中运行 `isort your_script.py`
