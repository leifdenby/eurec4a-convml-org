# Unsupervised Neural Network classification of organisation during EUREC4A

This repository contains a details around and links to a dataset of
unsupervised cloud-organisation classification during the EUREC4A field
campaign based on technique published in [L Denby
(2020)](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2019GL085190)
([model sourcecode](https://github.com/leifdenby/convml_tt)).

![Example of NN classification of EUREC4A upwind domain on 2nd Feb
2020](docs/goes16_202002051.gif)

# Dataset description

## Level-1: embedding vectors

The trained neural network produces a organisation classification
*embedding vector* for tiles (currently 256 x 256 pixels, 250km x 250km)
from the channels 1, 2 and 3 (visible range) GOES-16 satellite imagery.
The neural network is trained so that for tiles that contain similar cloud
structures it will produce embedding vectors that describe points that are
close in the embedding space.  Currently the embedding vectors have length
100 and so span a 100D embedding space.

## Level-2: PCA decomposition of embedding vectors (across entire compaign)

There is some redundancy in the 100 dimensions of the embedding space
vectors (the clouds are not likely to be different in 100 ways...) and so
to address that level 2 contains a PCA decomposition of the embedding
space. The PCA analysis is done across the entire EUREC4A field campaign
(spanning 15th Jan to 23rd Feb 2020). 
