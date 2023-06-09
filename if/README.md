# Dockerfile of DeepFloyd IF

- 📝 Step 1: Modify base image and pip mirror url in `Dockerfile`
```dockerfile
# base image
FROM <YOUR BASE IMAGE>

# pip url
RUN pip config set global.index-url <YOUR PIP MIRROR URL>

```
- 📁 Step 2: Move model weights to `.cache`  
move `IF_` and `clip` folder from your `.cache` (`~/.cache`) to `.cache` in current `if` folder  
the tree of directory after moving is like:
```plaintext
├── .cache
│   ├── clip
│   └── IF_
```

- 🏗️ Step 3: Build docker image  
```shell
docker build -t if:v0.1 . --network host
```

- 🚀 Step 4: Run  
```shell
docker run -t -i --net host --gpus all if:v0.1 /bin/bash
```