# music-vae
A repository containing my experiment on implementing the [Music VAE](https://magenta.tensorflow.org/music-vae) model to extract the 4-bars drum samples from the [MIDI dataset](https://magenta.tensorflow.org/datasets/groove).

## Overview
- **VAE Model**: [Music VAE](https://github.com/magenta/magenta/tree/main/magenta/models/music_vae)
- **Input**: MIDI - 4-bar Dataset.
- **Process**: Train Music VAE.
- **Output**: 4-bars drum samples (MIDI), 4-bars drum interpolation (Additional).

## Folder Structure
```
├── ckpts
│   ├── groove-4-bar
│   |   ├── train # Your trained checkpoints & event logs go here
│   |   ├── eval # Your eval event logs go here
├── magenta # Copy the files from magenta repository: https://github.com/magenta/magenta/tree/main
├── results
│   ├── interpolate
│   |   ├── groove-4-bar # Interpolation results
│   ├── sample
│   |   ├── groove-4-bar # Drum sample results
```

## Environment Preparation

## Training Process
Training process is quite straightforward, steps-by-steps process has been explained in:
```bash
musicvae-train.ipynb
```

## Validation Process
Before/right after running the training notebook, the evaluation listener can be run on the **Evaluation** section of the below notebook.
```bash
musicvae-eval.ipynb
```

## Inference Process
Inference on the trained MusicVAE model can be seen on the **Inference - Sample** & **Inference - Interpolate** section of the below notebook.
```bash
musicvae-eval.ipynb
```

**Note** 
```
- Refer to the following link to download the full model checkpoints logs: [Checkpoints](https://drive.google.com/file/d/1U2PnPJu3igqZCaocP3G-6gmRtDzKK2VY/view?usp=sharing)
- Refer to the following link to downdload the full val event logs: [Event Logs](https://drive.google.com/file/d/1gaU3qYeJPechC51lHZQZc2dcvhQYqR2f/view?usp=sharing)
- A Tensorboard GUI has also been included in each notebook to monitor the metrics and losses of the training & validation process.
- Training is stopped at global_steps = 10.000 to prevent the overfitting. See the loss figures above for more details.
- Evaluation is done on the 2nd GPU, to prevent overlapping usage on the 1st GPU that is used for training.
```
