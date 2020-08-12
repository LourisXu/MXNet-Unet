# MXNet-Unet
Use the library for Deep Learning, [MXNet](http://mxnet.incubator.apache.org/) to achieve this project.
For details of the model, you can read the [paper](http://www.arxiv.org/pdf/1505.04597.pdf).

**Note:**
- **In order to get output of the same size as the input, padding is added to the convolution layer and the upper sampling layer is modified. (See model.py)**
- **You must modify the parameters, 'COLORMAP' and 'CLASSES'(if it was used), where our labels are defined. (See settings.py)**

You can also use other methods to implement up-sampling, where only the transposed convolution layer is used.

## Architecture
```
·
|-- UNet_log.txt
|-- checkpoints
|   |-- epoch_0450_model.params
|   `-- epoch_0500_model.params
|-- data
|   |-- test
|   |-- test.txt
|   |-- test_mask_jpg
|   |-- train
|   |-- train.txt
|   `-- train_mask_jpg
|-- load.py
|-- model.py
|-- nohup.out
|-- settings.py
|-- train.py
`-- utils
    |-- convert.py
    `-- txt.py
```
## Settings
```
usage: python settings.py [options]

Set the arguments of the U-Net demo.

optional arguments:
  -h, --help            show this help message and exit
  --version             show program's version number and exit
  --gpu_id [GPU_ID [GPU_ID ...]]
                        a list to enable GPUs. (defalult: None)
  --is_crop IS_CROP     a flag to enable cropping. (default: True)
  --crop_height CROP_HEIGHT
                        the height to crop the images. (default: 572)
  --crop_width CROP_WIDTH
                        the width to crop the images. (default: 572)
  --learning_rate LEARNING_RATE
                        the learning rate of optimizer. (default: 0.1)
  --momentum MOMENTUM   the momentum of optimizer. (default: 0.99))
  --batch_size BATCH_SIZE
                        the batch size of model. (default: 3)
  --num_epochs NUM_EPOCHS
                        the number of epochs to train model. (defalult: 5)
  --num_classes NUM_CLASSES
                        the classes of output. (default: 2)
  --optimizer OPTIMIZER
                        the optimizer to optimize the weights of model.
                        (default: sgd)
  --data_dir DATA_DIR   the directory of datasets. (default: data)
  --log_dir LOG_DIR     the directory of 'UNet_log.txt'. (default: ./)
  --checkpoints_dir CHECKPOINTS_DIR
                        the directory of checkpoints. (default: ./checkpoints)
  --is_even_split IS_EVEN_SPLIT
                        whether or not to even split the data to all GPUs.
                        (default: True)

To see the settings.py for more details.

```
