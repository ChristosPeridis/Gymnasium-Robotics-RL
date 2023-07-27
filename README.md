# Ray-Robotics-Reinforcement-Learning
Leveraging the combined forces of the Gymnasium API and MuJoCo simulator to perform experiments and benchmark DRL SOTA algorithms on Robotic scenarios using the highly scalable and distributed Ray API.

# Installation
1. The present repository uses MuJoCo  physics simulator engine as its simulation backend. The version being used is MuJoCo210 which you can download from [here.](https://github.com/deepmind/mujoco/releases/tag/2.1.0)
2. Once you have downloaded the compressed MuJoCo file you will have to follow the next steps:
   * Create a hidden directory for MuJoCo simulator in your home directory: ```mkdir .mujoco```
   * Extract the compressed file in that directory: ```tar -xzf mujoco210-linux-x86_64.tar.gz -C ~/.mujoco/mujoco210```
   * Download the MuJoCo license key from [here.](https://roboti.us/file/mjkey.txt)
   * Add the license key inside the _.mujoco_ hidden folder.
3. MuJoCo's rendering capabilities are based on the following backends : glfw, osmesa, egl. It is important to make sure that these backends are installed in your system. You can install them by running the following command on the terminal: ```sudo apt-get install libglfw3 libglew2.0 libgl1-mesa-glx libosmesa6```. In case you have to use osmesa as a backend and you are facing issues **it is recomended to install the dev version :** ```sudo apt-get install libosmesa6-dev```
4. Clone the R3L GitHub repository: ``` git clone https://github.com/ChristosPeridis/R3L.git ``` and then navigate inside the repo ``` cd R3L ```
5. Depending on which operaing system you are working on create the R3L conda environment using the appropriate ``` .yml ``` file. For example if you are working in a Linux environment you need to run the folllowing command ``` conda env create -f Linux-environment.yml ```
  
> Because glfw is not working in headless environments and osmesa is running on CPU and not GPU, we recomend to use egl backend. The WSL2 environments have been tested and currently support only osmesa backend, hence all the processing is happening on the CPU.
> 
> It is important to note that the code on the present repository is using the latest MuJoCo python bindings from DeepMind as supose to the original MuJoCo_Py bindings from OpenAI. This is done so to decrease the installation difficulty since the original MuJoCo_Py bindings have been tested and proven to be difficult and time-consuming to setup. The configuration can go wrong very easily. Different version of MuJoCo simulator support different versions of MuJoCo_Py bindings and specific versions of MuJoCo_Py bindings require specific builds of Python done by specific gcc compilers.
