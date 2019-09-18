# Deep learning for liver NAS and fibrosis scoring

Repository for the upcoming publication "Deep learning enables pathologist-like scoring of NASH models"

## Requirements:

- CUDA compatible GPU
- Python 3.x
- Libraries: yaml, keras, tensorflow, matplotlib, pandas, sklearn (plus a number of common libraries, you will find them as imports)

## Set-up:

1. Clone this repository to your local machine.
2. Download images and model weights from: https://osf.io/p48rd/ and extract them under ./model/ 
*Imporant note:* The OSF repository with images and CNN weights will be made public <b>after</b> acceptance of the publication. Contact: fabian.heinemann@boehringer-ingelheim.com if you like to get access before publication.

## Training a new model:

1. Complete train.yaml (or a copy). A least you need to set:
..* model_path (Path where the .h5 file with the CNN weights will be stored)
..* model_file_name (Filename of model)
..* ground_truth_path (Path where the tiles with the ground truth are located)
2. Run
``` 
$python classify.py -c train.yaml
```
This will generate a new model file.

Please note, that trained models for ballooning, inflammation, steatosis and fibrosis have been uploaded to: https://osf.io/p48rd/ and there is no need to train a new model unless you want to add own data.
 
## Classification of a scanned liver section:

1. Prerequisite: Scanned liver slide stained with Masson's trichrome and cut into tiles:
.. * Higher resolution tiles (0.44 mm/px, 299x299 px², for ballooning, inflammation and steatosis)
...* Placed under: ./classification_data/<exp_no>/tiles/tiles/
..* Lower resolution tiles (1.32 mm/px, 299x299 px², for fibrosis)
...* Placed under: ./classification_data/<exp_no>/big_tiles/tiles/

<exp_no> is your experiment id.
