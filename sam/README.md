# Dockerfile of DeepFloyd IF

- 📝 Step 1: Modify base image and pip mirror url in `Dockerfile`
```dockerfile
# base image
FROM <YOUR BASE IMAGE>

# pip url
RUN pip config set global.index-url <YOUR PIP MIRROR URL>

```
- 📁 Step 2: Move model weights to `.cache`  
move downloaded weights to `checkpoint` in current `sam` folder  
the tree of directory after moving is like:
```plaintext
├── checkpoint
│   ├── sam_vit_b_01ec64.pth
│   ├── sam_vit_h_4b8939.pth
│   └── sam_vit_l_0b3195.pth
```

- 🏗️ Step 3: Build docker image  
```shell
docker build -t sam:v0.1 . --network host
```

- 🚀 Step 4: Run  
```shell
docker run -t -i --net host --gpus all sam:v0.1 /bin/bash 
```