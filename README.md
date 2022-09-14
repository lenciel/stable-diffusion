<h1 align='center'><b>Stable Diffusion MK Version</b></h1>

<p align='center'>
<<<<<<< HEAD
<img src="static/avatar.jpeg"/>
=======
<img src="docs/assets/logo.png"/>
>>>>>>> upstream/main
</p>

<p align="center">
    <img src="https://img.shields.io/github/last-commit/lenciel/stable-diffusion?logo=Python&logoColor=green&style=for-the-badge" alt="last-commit"/>
    <img src="https://img.shields.io/github/stars/lenciel/stable-diffusion?logo=GitHub&style=for-the-badge" alt="stars"/>
    <br>
    <img src="https://img.shields.io/github/issues/lenciel/stable-diffusion?logo=GitHub&style=for-the-badge" alt="issues"/>
    <img src="https://img.shields.io/github/issues-pr/lenciel/stable-diffusion?logo=GitHub&style=for-the-badge" alt="pull-requests"/>
</p>

<<<<<<< HEAD
This is a fork of lstein/stable-diffusion, which based on the wonderful open source text-to-image generator stable-diffusion but addding supports for M1/M2 chips and much more:
=======
# **Stable Diffusion Dream Script**
>>>>>>> upstream/main

This is a fork of
[CompVis/stable-diffusion](https://github.com/CompVis/stable-diffusion),
the open source text-to-image generator. It provides a streamlined
process with various new features and options to aid the image
generation process. It runs on Windows, Mac and Linux machines,
and runs on GPU cards with as little as 4 GB or RAM.

_Note: This fork is rapidly evolving. Please use the
[Issues](https://github.com/lstein/stable-diffusion/issues) tab to
report bugs and make feature requests. Be sure to use the provided
templates. They will help aid diagnose issues faster._

# **Table of Contents**

<<<<<<< HEAD
4. A notebook for running the code on Google Colab.

5. Upscaling and face fixing using the optional ESRGAN and GFPGAN
   packages.

6. Weighted subprompts for prompt tuning.

7. [Image variations](VARIATIONS.md) which allow you to systematically
generate variations of an image you like and combine two or more
images together to combine the best features of both.

8. Textual inversion for customization of the prompt language and images.

9. ...and more!

This fork is rapidly evolving, so use the Issues panel to report bugs
and make feature requests, and check back periodically for
improvements and bug fixes.

# Table of Contents

1. [Major Features](#features)
2. [Changelog](#latest-changes)
3. [Installation](#installation)
   1. [Linux](#linux)
   1. [Windows](#windows)
   1. [MacOS](README-Mac-MPS.md)
=======
1. [Installation](#installation)
2. [Major Features](#features)
3. [Changelog](#latest-changes)
>>>>>>> upstream/main
4. [Troubleshooting](#troubleshooting)
5. [Contributing](#contributing)
6. [Support](#support)

# Installation

This fork is supported across multiple platforms. You can find individual installation instructions below.

- ## [Linux](docs/installation/INSTALL_LINUX.md)
- ## [Windows](docs/installation/INSTALL_WINDOWS.md)
- ## [Macintosh](docs/installation/INSTALL_MAC.md)

## **Hardware Requirements**

**System**

You wil need one of the following:

- An NVIDIA-based graphics card with 4 GB or more VRAM memory.
- An Apple computer with an M1 chip.

**Memory**

- At least 12 GB Main Memory RAM.

**Disk**

- At least 6 GB of free disk space for the machine learning model, Python, and all its dependencies.

**Note**

If you are have a Nvidia 10xx series card (e.g. the 1080ti), please
run the dream script in full-precision mode as shown below.

Similarly, specify full-precision mode on Apple M1 hardware.

To run in full-precision mode, start `dream.py` with the
`--full_precision` flag:

```
(ldm) ~/stable-diffusion$ python scripts/dream.py --full_precision
```

# Features

## **Major Features**

- ## [Interactive Command Line Interface](docs/features/CLI.md)

- ## [Image To Image](docs/features/IMG2IMG.md)

- ## [Inpainting Support](docs/features/INPAINTING.md)

- ## [GFPGAN and Real-ESRGAN Support](docs/features/UPSCALE.md)

- ## [Seamless Tiling](docs/features/OTHER.md#seamless-tiling)

<<<<<<< HEAD
WINDOWS: As the default backend is not available on Windows, if you're using that platform, set the environment variable `PL_TORCH_DISTRIBUTED_BACKEND=gloo`

```
(ldm) ~/stable-diffusion$ python3 ./main.py --base ./configs/stable-diffusion/v1-finetune.yaml \
                                            -t \
                                            --actual_resume ./models/ldm/stable-diffusion-v1/model.ckpt \
                                            -n my_cat \
                                            --gpus 0, \
                                            --data_root D:/textual-inversion/my_cat \
                                            --init_word 'cat'
```
=======
- ## [Google Colab](docs/features/OTHER.md#google-colab)
>>>>>>> upstream/main

- ## [Web Server](docs/features/WEB.md)

- ## [Reading Prompts From File](docs/features/OTHER.md#reading-prompts-from-a-file)

- ## [Shortcut: Reusing Seeds](docs/features/OTHER.md#shortcuts-reusing-seeds)

- ## [Weighted Prompts](docs/features/OTHER.md#weighted-prompts)

- ## [Variations](docs/features/VARIATIONS.md)

- ## [Personalizing Text-to-Image Generation](docs/features/TEXTUAL_INVERSION.md)

- ## [Simplified API for text to image generation](docs/features/OTHER.md#simplified-api)

## **Other Features**

- ### [Creating Transparent Regions for Inpainting](docs/features/INPAINTING.md#creating-transparent-regions-for-inpainting)

- ### [Preload Models](docs/features/OTHER.md#preload-models)

# Latest Changes

- v1.14 (11 September 2022)

  - Memory optimizations for small-RAM cards. 512x512 now possible on 4 GB GPUs.
  - Full support for Apple hardware with M1 or M2 chips.
  - Add "seamless mode" for circular tiling of image. Generates beautiful effects. ([prixt](https://github.com/prixt)).
  - Inpainting support.
  - Improved web server GUI.
  - Lots of code and documentation cleanups.

- v1.13 (3 September 2022

  - Support image variations (see [VARIATIONS](docs/features/VARIATIONS.md) ([Kevin Gibbons](https://github.com/bakkot) and many contributors and reviewers)
  - Supports a Google Colab notebook for a standalone server running on Google hardware [Arturo Mendivil](https://github.com/artmen1516)
  - WebUI supports GFPGAN/ESRGAN facial reconstruction and upscaling [Kevin Gibbons](https://github.com/bakkot)
  - WebUI supports incremental display of in-progress images during generation [Kevin Gibbons](https://github.com/bakkot)
  - A new configuration file scheme that allows new models (including upcoming stable-diffusion-v1.5)
    to be added without altering the code. ([David Wager](https://github.com/maddavid12))
  - Can specify --grid on dream.py command line as the default.
  - Miscellaneous internal bug and stability fixes.
  - Works on M1 Apple hardware.
  - Multiple bug fixes.

<<<<<<< HEAD
For older changelogs, please visit **[CHANGELOGS](CHANGELOG.md)**.

# Installation

There are separate installation walkthroughs for [Linux](#linux), [Windows](#windows) and [Macintosh](#Macintosh)

## Linux

1. You will need to install the following prerequisites if they are not already available. Use your
   operating system's preferred installer

- Python (version 3.8.5 recommended; higher may work)
- git

2. Install the Python Anaconda environment manager.

```
~$  wget https://repo.anaconda.com/archive/Anaconda3-2022.05-Linux-x86_64.sh
~$  chmod +x Anaconda3-2022.05-Linux-x86_64.sh
~$  ./Anaconda3-2022.05-Linux-x86_64.sh
```

After installing anaconda, you should log out of your system and log back in. If the installation
worked, your command prompt will be prefixed by the name of the current anaconda environment, "(base)".

3. Copy the stable-diffusion source code from GitHub:

```
(base) ~$ git clone https://github.com/lstein/stable-diffusion.git
```

This will create stable-diffusion folder where you will follow the rest of the steps.

4. Enter the newly-created stable-diffusion folder. From this step forward make sure that you are working in the stable-diffusion directory!

```
(base) ~$ cd stable-diffusion
(base) ~/stable-diffusion$
```

5. Use anaconda to copy necessary python packages, create a new python environment named "ldm",
   and activate the environment.

```
(base) ~/stable-diffusion$ conda env create -f environment.yaml
(base) ~/stable-diffusion$ conda activate ldm
(ldm) ~/stable-diffusion$
```

After these steps, your command prompt will be prefixed by "(ldm)" as shown above.

6. Load a couple of small machine-learning models required by stable diffusion:

```
(ldm) ~/stable-diffusion$ python3 scripts/preload_models.py
```

Note that this step is necessary because I modified the original
just-in-time model loading scheme to allow the script to work on GPU
machines that are not internet connected. See [Workaround for machines with limited internet connectivity](#workaround-for-machines-with-limited-internet-connectivity)

7. Now you need to install the weights for the stable diffusion model.

For running with the released weights, you will first need to set up an acount with Hugging Face (https://huggingface.co).
Use your credentials to log in, and then point your browser at https://huggingface.co/CompVis/stable-diffusion-v-1-4-original.
You may be asked to sign a license agreement at this point.

Click on "Files and versions" near the top of the page, and then click on the file named "sd-v1-4.ckpt". You'll be taken
to a page that prompts you to click the "download" link. Save the file somewhere safe on your local machine.

Now run the following commands from within the stable-diffusion directory. This will create a symbolic
link from the stable-diffusion model.ckpt file, to the true location of the sd-v1-4.ckpt file.

```
(ldm) ~/stable-diffusion$ mkdir -p models/ldm/stable-diffusion-v1
(ldm) ~/stable-diffusion$ ln -sf /path/to/sd-v1-4.ckpt models/ldm/stable-diffusion-v1/model.ckpt
```

8. Start generating images!

```
# for the pre-release weights use the -l or --liaon400m switch
(ldm) ~/stable-diffusion$ python3 scripts/dream.py -l

# for the post-release weights do not use the switch
(ldm) ~/stable-diffusion$ python3 scripts/dream.py

# for additional configuration switches and arguments, use -h or --help
(ldm) ~/stable-diffusion$ python3 scripts/dream.py -h
```

9. Subsequently, to relaunch the script, be sure to run "conda activate ldm" (step 5, second command), enter the "stable-diffusion"
   directory, and then launch the dream script (step 8). If you forget to activate the ldm environment, the script will fail with multiple ModuleNotFound errors.

### Updating to newer versions of the script

This distribution is changing rapidly. If you used the "git clone" method (step 5) to download the stable-diffusion directory, then to update to the latest and greatest version, launch the Anaconda window, enter "stable-diffusion", and type:

```
(ldm) ~/stable-diffusion$ git pull
```

This will bring your local copy into sync with the remote one.

## Windows

### Notebook install (semi-automated)

We have a
[Jupyter notebook](https://github.com/lstein/stable-diffusion/blob/main/Stable-Diffusion-local-Windows.ipynb)
with cell-by-cell installation steps. It will download the code in this repo as
one of the steps, so instead of cloning this repo, simply download the notebook
from the link above and load it up in VSCode (with the
appropriate extensions installed)/Jupyter/JupyterLab and start running the cells one-by-one.

Note that you will need NVIDIA drivers, Python 3.10, and Git installed
beforehand - simplified
[step-by-step instructions](https://github.com/lstein/stable-diffusion/wiki/Easy-peasy-Windows-install)
are available in the wiki (you'll only need steps 1, 2, & 3 ).

### Manual installs

#### pip

See
[Easy-peasy Windows install](https://github.com/lstein/stable-diffusion/wiki/Easy-peasy-Windows-install)
in the wiki

#### Conda

1. Install Anaconda3 (miniconda3 version) from here: https://docs.anaconda.com/anaconda/install/windows/

2. Install Git from here: https://git-scm.com/download/win

3. Launch Anaconda from the Windows Start menu. This will bring up a command window. Type all the remaining commands in this window.

4. Run the command:

```
git clone https://github.com/lstein/stable-diffusion.git
```

This will create stable-diffusion folder where you will follow the rest of the steps.

5. Enter the newly-created stable-diffusion folder. From this step forward make sure that you are working in the stable-diffusion directory!

```
cd stable-diffusion
```

6. Run the following two commands:

```
conda env create -f environment.yaml    (step 6a)
conda activate ldm                      (step 6b)
```

This will install all python requirements and activate the "ldm" environment which sets PATH and other environment variables properly.

7. Run the command:

```
python scripts\preload_models.py
```

This installs several machine learning models that stable diffusion
requires. (Note that this step is required. I created it because some people
are using GPU systems that are behind a firewall and the models can't be
downloaded just-in-time)

8. Now you need to install the weights for the big stable diffusion model.

For running with the released weights, you will first need to set up
an acount with Hugging Face (https://huggingface.co). Use your
credentials to log in, and then point your browser at
https://huggingface.co/CompVis/stable-diffusion-v-1-4-original. You
may be asked to sign a license agreement at this point.

Click on "Files and versions" near the top of the page, and then click
on the file named "sd-v1-4.ckpt". You'll be taken to a page that
prompts you to click the "download" link. Now save the file somewhere
safe on your local machine. The weight file is >4 GB in size, so
downloading may take a while.

Now run the following commands from **within the stable-diffusion
directory** to copy the weights file to the right place:

```
mkdir -p models\ldm\stable-diffusion-v1
copy C:\path\to\sd-v1-4.ckpt models\ldm\stable-diffusion-v1\model.ckpt
```

Please replace "C:\path\to\sd-v1.4.ckpt" with the correct path to wherever
you stashed this file. If you prefer not to copy or move the .ckpt file,
you may instead create a shortcut to it from within
"models\ldm\stable-diffusion-v1\".

9. Start generating images!

```
# for the pre-release weights
python scripts\dream.py -l

# for the post-release weights
python scripts\dream.py
```

10. Subsequently, to relaunch the script, first activate the Anaconda
command window (step 3), enter the stable-diffusion directory (step 5,
"cd \path\to\stable-diffusion"), run "conda activate ldm" (step 6b),
and then launch the dream script (step 9).

**Note:** Tildebyte has written an alternative ["Easy peasy Windows
install"](https://github.com/lstein/stable-diffusion/wiki/Easy-peasy-Windows-install)
which uses the Windows Powershell and pew. If you are having trouble
with Anaconda on Windows, give this a try (or try it first!)

### Updating to newer versions of the script

This distribution is changing rapidly. If you used the "git clone"
method (step 5) to download the stable-diffusion directory, then to
update to the latest and greatest version, launch the Anaconda window,
enter "stable-diffusion", and type:

```
git pull
```

This will bring your local copy into sync with the remote one.

## Macintosh

See [README-Mac-MPS](README-Mac-MPS.md) for instructions.

# Simplified API for text to image generation

For programmers who wish to incorporate stable-diffusion into other
products, this repository includes a simplified API for text to image
generation, which lets you create images from a prompt in just three
lines of code:

```
from ldm.simplet2i import T2I
model   = T2I()
outputs = model.txt2img("a unicorn in manhattan")
```

Outputs is a list of lists in the format [[filename1,seed1],[filename2,seed2]...]
Please see ldm/simplet2i.py for more information. A set of example scripts is
coming RSN.

# Workaround for machines with limited internet connectivity

My development machine is a GPU node in a high-performance compute
cluster which has no connection to the internet. During model
initialization, stable-diffusion tries to download the Bert tokenizer
and a file needed by the kornia library. This obviously didn't work
for me.

To work around this, I have modified ldm/modules/encoders/modules.py
to look for locally cached Bert files rather than attempting to
download them. For this to work, you must run
"scripts/preload_models.py" once from an internet-connected machine
prior to running the code on an isolated one. This assumes that both
machines share a common network-mounted filesystem with a common
.cache directory.

```
(ldm) ~/stable-diffusion$ python3 ./scripts/preload_models.py
preloading bert tokenizer...
Downloading: 100%|██████████████████████████████████| 28.0/28.0 [00:00<00:00, 49.3kB/s]
Downloading: 100%|██████████████████████████████████| 226k/226k [00:00<00:00, 2.79MB/s]
Downloading: 100%|██████████████████████████████████| 455k/455k [00:00<00:00, 4.36MB/s]
Downloading: 100%|██████████████████████████████████| 570/570 [00:00<00:00, 477kB/s]
...success
preloading kornia requirements...
Downloading: "https://github.com/DagnyT/hardnet/raw/master/pretrained/train_liberty_with_aug/checkpoint_liberty_with_aug.pth" to /u/lstein/.cache/torch/hub/checkpoints/checkpoint_liberty_with_aug.pth
100%|███████████████████████████████████████████████| 5.10M/5.10M [00:00<00:00, 101MB/s]
...success
```
=======
For older changelogs, please visit **[CHANGELOGS](docs/CHANGELOG.md)**.
>>>>>>> upstream/main

# Troubleshooting

Please check out our **[Q&A](docs/help/TROUBLESHOOT.md)** to get solutions for common installation problems and other issues.

# Contributing

Anyone who wishes to contribute to this project, whether documentation, features, bug fixes, code cleanup, testing, or code reviews, is very much encouraged to do so. If you are unfamiliar with
how to contribute to GitHub projects, here is a [Getting Started Guide](https://opensource.com/article/19/7/create-pull-request-github).

A full set of contribution guidelines, along with templates, are in progress, but for now the most important thing is to **make your pull request against the "development" branch**, and not against "main". This will help keep public breakage to a minimum and will allow you to propose more radical changes.

## **Contributors**

This fork is a combined effort of various people from across the world. [Check out the list of all these amazing people](docs/CONTRIBUTORS.md). We thank them for their time, hard work and effort.

# Support

For support,
please use this repository's GitHub Issues tracking service. Feel free
to send me an email if you use and like the script.

Original portions of the software are Copyright (c) 2020 Lincoln D. Stein (https://github.com/lstein)

# Further Reading

Please see the original README for more information on this software
and underlying algorithm, located in the file [README-CompViz.md](docs/README-CompViz.md).
