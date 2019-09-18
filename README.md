# Deep learning for liver NAS and fibrosis scoring

Repository for the upcoming publication "Deep learning enables pathologist-like scoring of NASH models"

## Set-up:

1. Clone repository to your local machine.
2. Download images and model weights from: https://osf.io/p48rd/ and extract them under ./model/ 
*Imporant note:* The OSF repository with images and CNN weights will be made public *after* acceptance of the publication. Contact: fabian.heinemann@boehringer-ingelheim.com if you like to get access before publication.

## Training a model:

## Classification:

If you want to classify new samples, extract image patches under ./classification_data/exp_no/ in two subfolders:
- tiles/tiles/ (tiles for analysis of ballooning, inflammation, steatosis)
- tiles_big/tiles/ (tiles for analysis of fibrosis)