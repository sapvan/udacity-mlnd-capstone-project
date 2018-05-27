## Project Overview


Welcome to the travel blog automation project. As part of udacity's nanodegree, I have chosen this as my capstone project. The project makes use of the Keras library and is based on LSTM (Long short-term Memory) model, a variant of Recurrent Neural networks (RNNs)

Many travellers find very little time to blog on-the-go. For some travellers, blogging is one of the means to earn money to fund their future travel. Is it possible to automate travel blogging with artificial intelligence? Wouldn't it be great if your AI assistant helped you keep memories of your travels by automatically writing down stories about the places you visited? It turns out that this task could be tackled using deep learning because there is plenty of data available online.

## Project files

blog.txt - Input data
blog_bot.ipynb - Jupyter notebook

## Project Instructions

### Running project on AWS

1. Log into AWS account, choose region as __Oregon__ and request limit increase of ```g2.8xlarge``` to "1", if not opted earlier.
2. In the EC2 dashboard page, click on __Launch instance__ button
3. Select __AWS Marketplace__ and in the search bar, type __Ubuntu x64 with Tensorflow__.
4. Select the instance, leave all options to default, click __Review and launch__ button.
5. If you do not have an existing key pair, you will be asked to generate a private key. Once generated, save the privateKey.pem file in your computer.
6. Start instance from the AWS page, make a note of the IPv4 public IP. 
7. In your local computer, navigate to the location where you have saved the privateKey.pem file. 
8. Open terminal, type ```ssh -i privateKey.pem ubuntu@IPv4PublicIP```
9. Type the below commands to clone the project and configure jupyter notebook
```	
git clone https://github.com/sapvan/udacity-mlnd-capstone-project.git
cd udacity-mlnd-capstone-project
jupyter notebook --generate-config
pip install tqdm
pip install seaborn
sed -ie "s/#c.NotebookApp.ip = 'localhost'/#c.NotebookApp.ip = '*'/g" ~/.jupyter/jupyter_notebook_config.py
```
10. Start Jupyter notebook
```
jupyter notebook --ip=0.0.0.0 --no-browser
```
11. The above command will give you a URL somewhat like this: 
```http://0.0.0.0:8888/?token=eca2c164a11847f53aec732f0d79cca5d024120887657a19``` 
Copy the URL, replace 0.0.0.0 with your IPv4 IP and paste the link in your browser.

Happy learning!

### Local Install

__Prerequisites__: Tensorflow should be installed with GPU support. Follow [this guide](https://www.tensorflow.org/install/) for instructions. Platform - Linux.


1. Clone repository and navigate to the downloaded folder.
```	
https://github.com/sapvan/udacity-mlnd-capstone-project.git
cd udacity-mlnd-capstone-project
```
2. Type the below commands: 
	```
	conda env create -f requirements/blog-linux-gpu.yml
	source activate blog-bot
	```  
3. If step 2 throws errors, try the below commands instead.
	```
	conda create --name blog-bot python=3.5
	source activate blog-bot
	pip install -r requirements/requirements.txt
	```
	
4. Switch [Keras backend](https://keras.io/backend/) to TensorFlow.
		```
		KERAS_BACKEND=tensorflow python -c "from keras import backend"
		```

5. Create an [IPython kernel](http://ipython.readthedocs.io/en/stable/install/kernel_install.html) 
```
python -m ipykernel install --user --name blog-bot --display-name "blog-bot"
```

6. Open the notebook.
```
jupyter notebook blog_bot.ipynb
```

7. Change the kernel to match the blog-bot environment by using the drop-down menu (**Kernel > Change kernel > blog-bot**). 

Now you can run the notebook.