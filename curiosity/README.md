# RL-ISY-PROJECT -- CURIOSITY DRIVEN EXPLORATION BY SELF SUPERVISED EXPLORATION

Understanding and implementation of paper by title 
"CURIOSITY DRIVEN EXPLORATION BY SELF SUPERVISED EXPLORATION" 
which was presented at ICML 2017 (internatioanl conference on machine learning)


authors of paper are:

**Deepak Pathak    (University of California, Berkeley)

**Pulkit Agrawal   (University of California, Berkeley)

**Alexei A. Efros  (University of California, Berkeley)

**Trevor Darrell   (University of California, Berkeley)

Offical website link with GitHub code: https://pathak22.github.io/noreward-rl/

## 1) INSTALLATION AND USAGE:

### 1. This code is based on Tensorflow. To install, run the following commands:

-- you might not need many of these, e.g., fceux is only for mario

    sudo apt-get install -y python-numpy python-dev cmake zlib1g-dev libjpeg-dev xvfb \
    libav-tools xorg-dev python-opengl libboost-all-dev libsdl2-dev swig python3-dev \
    python3-venv make golang libjpeg-turbo8-dev gcc wget unzip git fceux virtualenv \
    tmux

-- install the code

    git clone -b master --single-branch https://github.com/swagking0/Curiosity_exploration.git

    cd Curiosity_exploration/

    virtualenv curiosity

    source $PWD/curiosity/bin/activate

    pip install numpy

    pip install -r src/requirements.txt

    python curiosity/src/go-vncdriver/build.py

### 2. Running the trained model:

       cd Curiosity_exploration/src/

       python demo.py --env-id SuperMarioBros-1-1-v0 --ckpt ../models/models_me/mario_me (optional arg --record which records the video)

-- note: the mario level change can be achived by changing the level number (1 to 4) in env-id (example : SuperMarioBros-1-1-v0 to SuperMarioBros-1-2 or 3 or 4-v0) and to change the level (1 to 8) in env-id (example : SuperMarioBros-1-1-v0 to SuperMarioBros-2 or 3 or 4 ...-1-v0)

### 3. Tranning the model:

-- Note: Before tranning the model please check the src/constants.py to play and understand the variables invloved.

 case 1: If you want to train the model from sratch follow this commands:
 
 ** In src/train.py on line 38 make the --pretrain --> "default=None" and then use the below command
 
    python train.py --default --env-id SuperMarioBros-1-1-v0 --noReward
 
  case 2: If you want to continue the tranning from the last check point follow this commands:
  
  ** As mentioned above there is no need to change anything as the file is saved with pretrain dir. So, just use below command directly
  
    python train.py --pretrain PRETRAIN --default --env-id SuperMarioBros-1-1-v0 --noReward
  
4. Inferencing the trannied model:

-- Note: After the model is trained please go into src/inference.py and then go to line 84 to 86 and give out new finial model name and dir to save your trained model. which can then be used to test with src/demo.py. After making all the changes use the below command to inference the model sucessfully

    python inference.py --default --env-id mario 

## 3) TO CITE THIS REPOSITORY IN PUBLICATIONS:

    inproceedings{pathakICMl17curiosity,

    Author = {Pathak, Deepak and Agrawal, Pulkit and
    
              Efros, Alexei A. and Darrell, Trevor},
              
    Title = {Curiosity-driven Exploration by Self-supervised Prediction},
    
    Booktitle = {International Conference on Machine Learning ({ICML})},
    
    Year = {2017}
    
    }
    
## 4) OTHER HELPFUL POINTERS

- [PAPER](https://pathak22.github.io/noreward-rl/resources/icml17.pdf)

- [Reddit Discussion](https://redd.it/6bc8ul)

- [Media Articles (New Scientist, MIT Tech Review and others)](http://pathak22.github.io/noreward-rl/index.html#media)

## 5) ACKNOWLEDGEMENT

Vanilla A3C code is based on the open source implementation of [universe-starter-agent](https://github.com/openai/universe-starter-agent).
