# music-vae
A repository containing my experiment on implementing the [Music VAE](https://magenta.tensorflow.org/music-vae) model to extract the 4-bars drum samples from the [MIDI dataset](https://magenta.tensorflow.org/datasets/groove).

## Overview
- **VAE Model**: [Music VAE](https://github.com/magenta/magenta/tree/main/magenta/models/music_vae)
- **Input**: MIDI - 4-bar Dataset.
- **Process**: Train Music VAE.
- **Output**: 4-bars drum samples (MIDI).

## Folder Structure
```bash
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
musicvae-train.ipynb
```

**Note** 
```
- A Tensorboard in-cell GUI has also been included in each notebook, to monitor the metrics and losses of the training & validation process
- Training was stopped at global_steps = 10.000, because the validation losses has stop decreasing.
```
