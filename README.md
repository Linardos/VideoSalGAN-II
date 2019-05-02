# SalEMA

## What SalEMA is

This work is an improvement on [VideoSalGAN](https://github.com/imatge-upc/saliency-2018-videosalgan).
In both of these works, the goal is to explore how a model trained on static images for the task of saliency prediction can be extended to do the same thing on videos. The video saliency dataset used for our experiments was the DHF1K.

![TemporalEDmodel](https://raw.githubusercontent.com/Linardos/SalEMA/gh-pages/TemporalEDmodel.jpg)

![QResults](https://raw.githubusercontent.com/Linardos/SalEMA/gh-pages/QResultsEMA.png)

## Model

Download our best configuration of the SalEMA model [here](https://imatge.upc.edu/web/sites/default/files/projects/saliency/public/VideoSalGAN-II/SalEMA30.pt)

## Installation

- Clone the repo:

```shell
git clone https://github.com/Linardos/SalEMA
```

- Install requirements ```pip install -r requirements.txt``` 
- Install [PyTorch 1.0](http://pytorch.org/):

```shell
pip3 install torch torchvision
```

## Inference

You may use our pretrained model for inference on either of the 3 datasets: DHF1K [[link]](https://drive.google.com/file/d/1vfRKJloNSIczYEOVjB4zMK8r0k4VJuWk/view), Hollywood-2 [[link]](https://drive.google.com/file/d/1vfRKJloNSIczYEOVjB4zMK8r0k4VJuWk/view), UCF-sports [[link]](https://drive.google.com/drive/folders/1sW0tf9RQMO4RR7SyKhU8Kmbm4jwkFGpQ):

To perform inference on DHF1K validation set:

```python inference.py -dataset=DHF1K -pt_model=SalEMA30.pt -start=600 -end=700 -dst=/path/to/output -src=/path/to/DHF1K/frames```

To perform inference on Hollywood-2 or UCF-sports test set (because of the way the dataset is structured, it's convenient to use the same path for dst and src):

```python inference.py -dataset=Hollywood-2 -pt_model=SalEMA30.pt -dst=/path/to/Hollywood-2/testing -src=/path/to/Hollywood-2/testing```
```python inference.py -dataset=UCF-sports -pt_model=SalEMA30.pt -dst=/path/to/UCF-sports/testing -src=/path/to/UCF-sports/testing```
