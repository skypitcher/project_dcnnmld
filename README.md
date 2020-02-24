# Project DCNN-MLD
Offical repo for the paper titled "A MIMO Detector with Deep Learning in the Presence of Correlated Interference"

## Dependencies
1. `pip install tensorflow-gpu==1.12` (you have to install cuda by your hand)
2. `pip install matplotlib`
3. `pip install mpmath`

## How to run benchmark?
1. Establish all the dependencies
2. Keep calm and run `python test.py`

## How to train model?
1. Generate training set and valid set
2. train your model
there is a example code snippet for you
```
def generate_training_set_and_valid_set(rho, sir_db):
    print("Generating data sets, rho={:.1f} sir={}".format(rho, sir_db))
    training_set = DataSet(flag=1, rho=rho, sir=sir_db)  # flag == 1 : training set
    training_set.produce_all()

    valid_set = DataSet(flag=1, rho=rho, sir=sir_db)  # flag == 2 : valid set
    valid_set.produce_all()
    
def train_model(rho, sir_db, is_improved=True):
    model = DCNNMLD(rho, sir_db, is_improved=is_improved)
    model.train()
    
def gennerate_data_and_then_train_model(rho, sir_db, is_improved=True):
    generate_training_set_and_valid_set(rho, sir_db)
    train_model(rho, sir_db, is_improved)
```

## License
Anti 996 License Version 1.0

[![LICENSE](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE)
<a href="https://996.icu"><img src="https://img.shields.io/badge/link-996.icu-red.svg" alt="996.icu"></a>
