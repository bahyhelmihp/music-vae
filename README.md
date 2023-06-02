# music-vae
A repository containing my experiment on implementing the [Music VAE](https://magenta.tensorflow.org/music-vae) model to extract the 4-bars drum samples from the [MIDI dataset](https://magenta.tensorflow.org/datasets/groove).

## Overview
- **VAE Model**: [Music VAE](https://github.com/magenta/magenta/tree/main/magenta/models/music_vae)
- **Input**: MIDI - 4-bar Dataset.
- **Process**: Train Music VAE.
- **Output**: 4-bars drum samples (MIDI), 4-bars drum interpolation (Additional).

## Folder Structure
```
├── assets # Figures
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
- Refer to the following link to download the full model checkpoints logs: [Checkpoints](https://drive.google.com/file/d/1U2PnPJu3igqZCaocP3G-6gmRtDzKK2VY/view?usp=sharing)
- Refer to the following link to downdload the full val event logs: [Event Logs](https://drive.google.com/file/d/1gaU3qYeJPechC51lHZQZc2dcvhQYqR2f/view?usp=sharing)

## Figures
#### Training Loss
<img src="/assets/training_loss.png" width="700">

#### Validation Loss
<img src="/assets/validation_loss.png" width="700">

### Validation Metrics
![Val metrics](/assets/validation_metrics.png)

- Training is stopped at global_steps = 10.000 to prevent overfitting. 
- Loss value stops decreasing in validation data, approaching 10.000 steps. 
- Same plateau pattern also observed in the validation metrics. 
- Time & resource constraint also taken into account.

## Samples
Generated Sample 1 | Generated Sample 2
:-: | :-:
https://github.com/bahyhelmihp/music-vae/assets/36230581/19a60e9c-54ae-401e-84ba-1c3451d0b135 | https://github.com/bahyhelmihp/music-vae/assets/36230581/5ca0d0ff-d04a-4d72-9f03-a8ee2626fe66



**Note** 
```
- A Tensorboard GUI has also been included in each notebook to monitor the metrics and losses of the training & validation process.
- Evaluation is done on the 2nd GPU, to prevent overlapping usage on the 1st GPU that is used for training.
```

## Acknowledgements
The code is developed based on https://github.com/magenta/magenta/tree/main/magenta/models/music_vae.
