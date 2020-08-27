
# Energy-based MIXer (EMIX)

<p align="center"><img src="/images/2s_vs_1sc.gif" height="200" width="400" />  <img src="/images/so_many_baneling.gif"  height="200" width="400" /></p>

This is the original implementation of EMIX introduced in ["Energy-based Surprise Minimization for Multiagent Value Factorization"](https://arxiv.org/pdf/2007.13690.pdf). EMIX is a multi-agent value factorization algorithm built on top of QMIX. EMIX minimizes surprise by utilizing the energy across agents in the case of multi-agent partially-observable settings. EMIX makes use of a novel surprise value function in conjunction with an energy operator to minimize surprise. Additionally, EMIX addresses overestimation error by making use of a multiple target function scheme in a scalable manner. EMIX demonstrates state-of-the-art surprise minimization performance on the [StarCraft II Multi-Agent Challenge (SMAC)](https://github.com/oxwhirl/smac) micromanagement benchmark.  

Find out more-  
- [arXiv](https://arxiv.org/abs/2007.13690)  
- [Project Website](https://karush17.github.io/emix-web/)  
- [Blog Post](https://karush17.github.io/emix-web/blog.html)  
- [Videos](https://karush17.github.io/emix-web/videos.html)  

<p align="center"><img src="/images/emix.gif" height="500" width="600" /></p>

## Installation

Our implementation of EMIX makes use of [PyMARL](https://github.com/oxwhirl/pymarl) (writtent in PyTorch) and is built on top of the QMIX implementation.  

#### 1. Docker Support  

[Skip this step if using a local machine]  

Build the Dockerfile using

```
cd docker
bash build.sh
```

#### 2. StarCraft II and SMAC  

The following command will download SC2 in the '3rdparty' folder and copy the custom SMAC maps required for experiments-
```
bash install_sc2.sh
```

#### 3. Library Dependencies  

Library dependencies are listed in the `requirements.txt` file and can be installed using the following command-  

```
pip install -r requirements.txt
```


## Executing Experiments  

#### 1. Local Machine  

Once the installation is complete, EMIX experiments can be executed using the following command:
```
python3 prog/main.py --config=emix --env-config=sc2 with env_args.map_name=2s3z
```
The config files consist of default hyperparameter values. To change these for EMIX refer to `emix.yaml` config file located in `prog/config` folder.  

#### 2. Docker Container  

To run experiments using the Docker container use the following-  
```
bash run.sh $GPU python3 src/prog.py --config=emix --env-config=sc2 with env_args.map_name=2s3z
```
All results will be stored in the Results folder. For additional details on loading and saving models please refer to the [PyMARL](https://github.com/oxwhirl/pymarl) page.  


## Credits

EMIX was developed by [Karush Suri](https://karush17.github.io/) from the University of Toronto under the supervision of Xiao Qi Shi from RBC Captial Markets, Yuri A. Lawryshyn and Konstantinos N. Plataniotis from the Center for Management of Technology and Entrepreneurship (CMTE) and the Multimedia Laboratory at the University of Toronto respectively. Special thanks to our sponsors RBC Capital Markets and RBC Innovation Lab and to the staff of CMTE.

## License

Code licensed under the Apache License v2.0
