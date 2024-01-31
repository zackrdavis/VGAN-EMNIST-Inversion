# Vanilla GAN with Inversion and export to ONNX

Training a GAN on the EMNIST alphanumeric handwriting dataset, performing inversion, and exporting to ONNX. Network and training code copied almost verbatim from Diego Gomez's great PyTorch [implementation](https://github.com/diegoalejogm/gans).

I've written about this project in more detail [here](https://zackrdavis.github.io/fonting-with-gans/).

## Untwisting EMNIST

EMNIST from PyTorch is mirrored and rotated 90 degrees, so I fix the data with some transforms.

![a grid of handwritten numbers and letters with each one mirrored and rotated 90 degrees](twisted_samples.png "twisted")

## Training

Nothing new to see here.

![Two rows of white glyphs on a black background. The letters are distorted and unreadable.](weirdos.png "Obageyix loernags!")

## Inversion

Gradient-descent search through the generator's inputs in search of a good example of each character.

![A grid of black tiles with white forms that slowly become handwritten characters.](search.gif "satisfaction")

## Exporting to ONNX

Worked just as advertised.
