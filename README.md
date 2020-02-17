# Slalom with docker
forked slalom + docker build & execution environment enabled ssh connection.

https://github.com/sebva/docker-sgx
https://github.com/ftramer/slalom

## fix problem
1. Copy eigen library to Include/eigen.
2. Create folders SGXDNN/bin and SGXDNN/bin_sgx.

## How to build
refered by slalom. We ignore CUDA part.

```
cd slalom
pip install -r requirements.txt

cd slalom/App
make

cd slalom/SGXDNN
make

cd slalom
make # hw mode or
make SGX_MODE=SIM # if you want sim mode.
```

We use enclave.singed.so and App.enclave_bridge.so



## Connection is refused by docker?
Change password for ssh connection.

```
$ docker-compose up
$ docker-compose exec sgx-dev /bin/bash
# passwd root
```

https://qiita.com/kochizufan/items/c6c1b12748a4e08fde3f