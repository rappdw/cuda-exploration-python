# cuda-exploration-python
Repo to learn/explore Numba CUDA support

This repo is structured to run against an EC2 GPU instance using dockerutils conventions

Try:

```
create-dock -i p2.xlarge -m gpu
source dock gpu
build-image base
run-image -g dev
nvprof python explore/getting_started/VectorAdd.py
```
