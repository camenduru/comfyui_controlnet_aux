# ComfyUI's ControlNet Auxiliary Preprocessors

This is a rework of [comfyui_controlnet_preprocessors](https://github.com/Fannovel16/comfy_controlnet_preprocessors) based on [ControlNet auxiliary models by 🤗](https://github.com/patrickvonplaten/controlnet_aux). I think the old repo isn't good enough to maintain.

All old workflows still can be used with custom nodes in this repo but the version option won't do anything. Almost all v1 preprocessors are replaced by v1.1 except those doesn't apppear in v1.1.

You don't need to care about the differences between v1 and v1.1 lol.

The code is copy-pasted from the respective folders in https://github.com/lllyasviel/ControlNet/tree/main/annotator and connected to [the 🤗 Hub](https://huggingface.co/lllyasviel/Annotators).

All credit & copyright goes to https://github.com/lllyasviel.

# Q&A:
* Why some nodes doesn't appear after I installed this repo?

This repo has a new mechanism which will skip any custom node can't be imported. If you meet this case, please create a issue on [Issues tab](https://github.com/Fannovel16/comfyui_controlnet_aux/issues) with the log from the command line.

# Installation:
## Using ComfyUI Manager (recommended):
Install [ComfyUI Manager](https://github.com/ltdrdata/ComfyUI-Manager) and do steps introduced there to install this repo.

## Alternative:
If you're running on Linux, or non-admin account on windows you'll want to ensure `/ComfyUI/custom_nodes` and `comfyui_controlnet_aux` has write permissions.

There is now a **install.bat** you can run to install to portable if detected. Otherwise it will default to system and assume you followed ConfyUI's manual installation steps. 

If you can't run **install.bat** (e.g. you are a Linux user). Open the CMD/Shell and do the following:
  - Navigate to your `/ComfyUI/custom_nodes/` folder
  - Run `git clone https://github.com/Fannovel16/comfyui_controlnet_aux/`
  - Navigate to your `comfyui_controlnet_aux` folder
    - Portable/venv:
       - Run `path/to/ComfUI/python_embeded/python.exe -s -m pip install -r requirements.txt`
	- With system python
	   - Run `pip install -r requirements.txt`
  - Start ComfyUI

# Nodes
Please note that this repo only supports preprocessors making hint images (e.g. stickman, canny edge, etc).
## Line Extractors
* Binary Lines
* Canny Edge
* HED Lines
* Normal Lineart
* Anime Lineart
* Manga Lineart
* M-LSD Lines
* PiDiNet Lines
* Scribble Lines
* Scribble XDoG Lines

## Normal and Depth Map
* LeReS - Depth Map
* MiDaS - Normal Map
* MiDaS - Depth Map
* BAE - Normal Map
* Zoe - Depth Map

## Faces and Poses
* DWPose Pose Recognition
* OpenPose Pose Recognition
* MediaPipe Face Mesh

## Semantic Segmentation
* OneFormer ADE20K Segmentor
* UniFormer Segmentor
* OneFormer COCO Segmentor

## T2IAdapter-only
* Color Pallete
* Content Shuffle

# Examples
> A picture is worth a thousand words

Credit to https://huggingface.co/thibaud/controlnet-sd21. You can get the same kind of results from preprocessor nodes of this repo.
## Line Extractors
### Canny Edge
![](https://huggingface.co/thibaud/controlnet-sd21/resolve/main/example_canny.png)
### HED Lines
![](https://huggingface.co/thibaud/controlnet-sd21/resolve/main/example_hed.png)
### Normal Lineart
![](https://huggingface.co/thibaud/controlnet-sd21/resolve/main/example_lineart.png)
### Scribble/Fake Scribble
![](https://huggingface.co/thibaud/controlnet-sd21/resolve/main/example_scribble.png)

## Normal and Depth Map
### Depth (idk the preprocessor they use)
![](https://huggingface.co/thibaud/controlnet-sd21/resolve/main/example_depth.png)
## Zoe - Depth Map
![](https://huggingface.co/thibaud/controlnet-sd21/resolve/main/example_zoedepth.png)
## BAE - Normal Map
![](https://huggingface.co/thibaud/controlnet-sd21/resolve/main/example_normalbae.png)

## Faces and Poses
### OpenPose
![](https://huggingface.co/thibaud/controlnet-sd21/resolve/main/example_openpose.png)
![](https://huggingface.co/thibaud/controlnet-sd21/resolve/main/example_openposev2.png)

## Semantic Segmantation
### OneFormer ADE20K Segmentor
![](https://huggingface.co/thibaud/controlnet-sd21/resolve/main/example_ade20k.png)

## T2IAdapter-only
### Color Pallete for T2I-Adapter
![](https://huggingface.co/thibaud/controlnet-sd21/resolve/main/example_color.png)

# Testing workflow
https://github.com/Fannovel16/comfyui_controlnet_aux/blob/master/tests/test_cn_aux_full.json
![](https://github.com/Fannovel16/comfyui_controlnet_aux/blob/master/tests/pose.png?raw=true)
