# What is this?
Going through this [Generative Deep Learning](https://www.ebooks.com/en-us/book/210833591/generative-deep-learning/david-foster/) book.  The original [repo](https://github.com/davidADSP/Generative_Deep_Learning_2nd_Edition) uses Docker but I'm trying to run these on SageMaker which does not support it. So the notebooks are slightly modified.

# Datasets

I am uploaing the datasets to an S3 bucket @ `s3://sagemaker-datasets-ara`.

In SageMaker, download them into a persistent directory like `/home/sagemaker-user/data`.

```
cd /home/sagemaker-user/data
aws s3 cp s3://sagemaker-datasets-ara/celeba-dataset.zip .
aws s3 cp s3://sagemaker-datasets-ara/lego-brick-images.zip .
aws s3 cp s3://sagemaker-datasets-ara/epirecipes.zip .
```

# Creating an iPython kernel

## Create/activate a conda environment

```
conda create -n myenv python=3.10 -y
conda activate myenv
```

## Install dependencies

```
pip install -U pip
pip install -r requirements.txt
```

## Create an iPython kernel

```
pip install ipykernel
python -m ipykernel install --user --name gen-deep-learning --display-name "Generative-Deep-Learning"
```

# Running the notebooks

Configure space and use an `ml.g4dn.xlarge` instance.

Start the space.

Go to JupyterLab and open the notebooks.
