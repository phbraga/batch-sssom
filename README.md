# Batch SS-SOM

Deep Categorization with Semi-Supervised Self-Organizing Maps

It was presented in the 2020 World Conference on Computational Intelligence (WCCI), precisely at the International Joint Conference on Neural Networks (IJCNN), as a Virtual Conference, Formerly Glasgow, Scotland - UK.

### Cite:

Please cite our paper if you use this code in your own work:

```bibtex
@inproceedings{braga2020semi,
  title         = {Deep Categorization with Semi-Supervised Self-Organizing Maps},
  author        = {Braga, Pedro H. M. and Medeiros, Heitor R. and Bassani, Hansenclever F},
  booktitle     = {2020 International Joint Conference on Neural Networks (IJCNN)},
  pages         = {1--8},
  year          = {2020},
  organization  = {IEEE}
}
```

### Requirements:

1. Libs:

        Python 3.6+
        CUDA 10.0+
        Pytorch 1.3.1+
        Pandas
        Scipy
        NumPy
        Scikit-Learn

2. A file containing all the paths to the datasets you want to use. Please refer to [this](https://github.com/hfbassani/pbml/blob/master/phmb4/Parameters/inputPathsTrain) example.


### Manually Setup of  Conda Environment

    conda create -n bsssom python=3.6 -y
    conda activate bsssom (or source activate bsssom)
    conda install pytorch torchvision cudatoolkit=10.2 -c pytorch -y
    conda install pandas -y
    conda install scipy -y
    conda install numpy -y
    conda install scikit-learn -y

### Parameters

  To run Batch SS-SOM, there are 11 parameters to set:

   - a_t
   - lp
   - dsbeta
   - age_wins
   - e_b
   - e_n
   - epsilon_ds
   - minwd
   - epochs
   - seed
   - push_rate<br/><br/>

   You can follow [this](https://github.com/hfbassani/pbml/blob/master/phmb4/Parameters/deep-sssom_0) example, where the first eleven rows represent the first set of parameters, the next 11 rows the second set and so on.

   Also, it is important to update the constant _noClass_, if necessary. The default value is 999.

   The sample code to generate the parameters with LHS, as in the paper, is available [here](https://github.com/hfbassani/pbml/tree/master/params-gen/).


## Training

For instance, you can use a similar commands to execute the model:

- 1% of labels

```train
python train_sssom.py -i inputPathsTrain01 -t inputPathsTest -r results/ -p deep-sssom_0 --batch-size 32
```

- 100% of labels

```train
python train_sssom.py -i inputPathsTrain -t inputPathsTest -r results/ -p deep-sssom_0 --batch-size 32
```

## Evaluation

See [py-scripts](https://github.com/hfbassani/pbml/tree/master/phmb4/py_scripts).
