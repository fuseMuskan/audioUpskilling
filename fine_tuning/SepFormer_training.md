
# Audio Separation

This notebook deals with pretraining the sepformer-wham model to your custom dataset.

## Folder Structure
The recipe expects the following folder structure:

- wham_dataset
  - tt
    - mix_both
    - s1
    - s2
  - cv
    - mix_both
    - s1
    - s2
  - tr
    - mix_both
    - s1
    - s2



## Main Code snippets

```bash
  git clone https://github.com/speechbrain/speechbrain/
  cd speechbrain
  pip install -r requirements.txt
  pip install -e .
  cd  recipes/WHAMandWHAMR/separation
  python train.py hparams/sepformer-wham.yaml --data_folder=/content/ gdrive/MyDrive/audioUpskilling/dataset/wham_dataset 
  ```

    
# References
https://huggingface.co/speechbrain/sepformer-wham
