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
