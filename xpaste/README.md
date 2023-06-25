# Dockerfile of X Paste

- 📝 Step 1: Modify base image and pip mirror url in `Dockerfile`
```dockerfile
# base image
FROM <YOUR BASE IMAGE>

# pip url
RUN pip config set global.index-url <YOUR PIP MIRROR URL>

```
- 📁 Step 2: Move model weights to `models`  
move downloaded weights to `models` in current `xpaste` folder  
the tree of directory after moving is like:
```plaintext
├── models
│   ├── resnet50_miil_21k.pkl
│   ├── swin_base_patch4_window7_224_22k.pkl
```

- 🏗️ Step 3: Build docker image  
```shell
docker build -t xpaste:v0.1 . --network host
```

- 🚀 Step 4: Run  
```shell
docker run -t -i --net host --gpus all xpaste:v0.1 /bin/bash 
```