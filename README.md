# Ray-Robotics-Reinforcement-Learning
Leveraging the combined forces of the Gymnasium API and MuJoCo simulator to perform experiments and benchmark DRL SOTA algorithms on Robotic scenarios using the highly scalable and distributed Ray API.

# Installation
The present repository uses MuJoCo physics simulator engine as its simulation backend. We updated the repository from using MuJoCo210 to the newer version 2.3.3. Additionaly we have created .yml configuration files for each of the platforms we support, in order to make easier the instalation process. Currently the supported platforms are the following:
1. `Linux`
2. `Linux-Server`
3. `Windows11 through WSL2`

The steps for installing R3L API to your working environment are the following:
1. MuJoCo's rendering capabilities are based on the following backends : glfw, osmesa, egl. It is important to make sure that these backends are installed in your system. You can install them by running the following command on the terminal: `sudo apt-get install libglfw3 libglew2.0 libgl1-mesa-glx libosmesa6`. In case you have to use osmesa as a backend and you are facing issues **it is recomended to install the dev version :** `sudo apt-get install libosmesa6-dev`
2. Clone the R3L repository by running the following command on the terminal: `git clone https://github.com/ChristosPeridis/R3L.git`
3. Navigate to the project's folder by running `cd R3L`
4. Based on the platform that you are working on select the approprate .yml file and create the custom conda environment by running the following command: `conda env create -f <your_platform>-environment.yml`

For more advanced experiments you work with the [Gymnasium-Robotics-R3L](https://github.com/ChristosPeridis/Gymnasium-Robotics-R3L/tree/main) which is an extension of the R3L API which facilitates more challenging robotics environments. You can install Gymnasium-Robotics-R3L to your R3L conda environment by following the instraction found [here](https://github.com/ChristosPeridis/Gymnasium-Robotics-R3L/tree/main).
  
> **Note:** Because glfw is not working in headless environments and osmesa is running on CPU and not GPU, we recomend to use egl backend. The WSL2 environments have been tested and currently support only osmesa backend, hence all the processing is happening on the CPU.
>
> **Note:** To run R3L on a WSL2 system you will need to install the WSL2 Ubuntu 20.04.06 LTS, which is the version currently supportd by the R3L API. Relative works have been contactd to suppurt WSL2 Ubuntu 22.04 LTS, however it is still on beta stage.
> 
> **Note:** The code on the present repository is using the latest MuJoCo python bindings from DeepMind as supose to the original MuJoCo_Py bindings from OpenAI. This is done so to decrease the installation difficulty since the original MuJoCo_Py bindings have been tested and proven to be difficult and time-consuming to setup. The configuration can go wrong very easily. Different version of MuJoCo simulator support different versions of MuJoCo_Py bindings and specific versions of MuJoCo_Py bindings require specific builds of Python done by specific gcc compilers.
