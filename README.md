**Warning!** The optimization may not converge on some GPUs. We've personally experienced issues on Tesla V100 and P40 GPUs. When running the code, make sure you get similar results to the paper first. Easiest to check using text inpainting notebook.  Try to set double precision mode or turn off cudnn. 

**DIP_gettingstart.ipynb 파일을 참고하여 환경설정 및 설명 참고**

이 프로젝트는  "Deep image prior" 논문과 관련 구현 github 코드를 활용하여 구현하였습니다.
기존의 'inpainting' 코드를 응용해 사용자가 영상에서 지우고싶은 글씨를 지울 수 있도록 새롭게 customize 해보았습니다.

=> 'inpainting_with_custom_mask.ipynb'

*기대 효과*
- random한 noise 영상에 대해 학습없이 clean한 결과영상을 얻을 수 있음.
- super resolution, denoising, inpainting과 같은 여러 응용에 이용될 수 있음.
- 사용자가 직접 마스크를 제작하여 영상에서 마스크 부분을 inpainting시킬 수 있음 ⭐️

# Deep image prior

In this repository we provide *Jupyter Notebooks* to reproduce each figure from the paper:

> **Deep Image Prior**

> CVPR 2018

> Dmitry Ulyanov, Andrea Vedaldi, Victor Lempitsky


[[paper]](https://sites.skoltech.ru/app/data/uploads/sites/25/2018/04/deep_image_prior.pdf) [[supmat]](https://box.skoltech.ru/index.php/s/ib52BOoV58ztuPM) [[project page]](https://dmitryulyanov.github.io/deep_image_prior)

![](data/teaser_compiled.jpg)

Here we provide hyperparameters and architectures, that were used to generate the figures. Most of them are far from optimal. Do not hesitate to change them and see the effect.

We will expand this README with a list of hyperparameters and options shortly.

# Install

Here is the list of libraries you need to install to execute the code:
- python = 3.6
- [pytorch](http://pytorch.org/) = 0.4
- numpy
- scipy
- matplotlib
- scikit-image
- jupyter

All of them can be installed via `conda` (`anaconda`), e.g.
```
conda install jupyter
```


or create an conda env with all dependencies via environment file

```
conda env create -f environment.yml
```

## Docker image

Alternatively, you can use a Docker image that exposes a Jupyter Notebook with all required dependencies. To build this image ensure you have both [docker](https://www.docker.com/) and  [nvidia-docker](https://github.com/NVIDIA/nvidia-docker) installed, then run

```
nvidia-docker build -t deep-image-prior .
```

After the build you can start the container as

```
nvidia-docker run --rm -it --ipc=host -p 8888:8888 deep-image-prior
```

you will be provided an URL through which you can connect to the Jupyter notebook.


# Citation
```
@article{UlyanovVL17,
    author    = {Ulyanov, Dmitry and Vedaldi, Andrea and Lempitsky, Victor},
    title     = {Deep Image Prior},
    journal   = {arXiv:1711.10925},
    year      = {2017}
}
```
