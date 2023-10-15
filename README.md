# Unflattering-Dataset
In this workshop, the students learn the process of image classification for training text-to-image AI models and build their own small, ‘unflattering’ dataset to experiment with the tools and share their thoughts about the machinery but personal process.

## Processes behind Dataset Curation & Creation

🡥 (1) Preprocess Data: Crop, Resize, Label. <br/>
🡥 (2) Training: How to train the model, what settings are needed <br/>
🡥 (3) Inference: How to use your trained model with text-to-image models <br/>

## (1) Preprocess Data


* Info: [Breakdown of LoRA](https://softwarekeep.com/help-center/how-to-use-stable-diffusion-lora-models) and [A111 SD Notebook](https://github.com/AUTOMATIC1111/stable-diffusion-webui)

### (1-1) Collect the images for a dataset
* We will collect a small collection of Images ~20-50 (the more the better)
* For faces or portraits the number of images can be lower, but for more complex objets, styles, concepts ~50-100 images are needed.
* A Pre-Trained Model: We will need a LARGE model which has already has a understanding of objects, styles, text/image knowledge. In this workshop, it would be best to use LoRA which is really good for quickly finetuning a model off of your data.
* Training Images can be JPG or PNG.
* Mininum size of training images 512x512. The larger the images the better.
  

### (1-2) Batch crop & rename images: [Birme.net](https://www.birme.net/?image_format=jpeg&quality_jpeg=100&rename=EnterNameHere-XXX)

* Settings for Birme: JPG (100%), 512 x 512, Save as Zip

<br/>![Brime Cropping](https://github.com/soyunparrrk/Unflattering-Dataset/blob/c1f991bc5ec2e9b149a15d4edbf2cbe7addc20c0/media/Brime%20Cropping.png)
_Michelin Man 🛞_

### (1-3) Label your images
Open a text editor of your preference and label (classify) each image. You can do it in one file.

** Pay attention to what comes to your mind when you do so. What decisions did you have to make when describing the image? What was easy? What was difficult? And why? **

### (1-4) Try automatic data labeling and compare it to yours

Use this colab notebook [Dataset cleaner](https://colab.research.google.com/drive/1pxk4SovIhZl4HaLmBJo50ZjCKOuofMwb#scrollTo=WBFik7accyDz). This will be used to prepare the images as a dataset for LoRA. It will also create captions for each image, which you can alter manually.

* Project Name -> Whatever you want, and keep a note of this.
Then you can start section (1) Setup. Once (1) is finished, go to section (4), and change the method to 'Photo Caption' - You can black list some words if you want to.

![Initial Captioning](https://github.com/soyunparrrk/Unflattering-Dataset/blob/69a351375a049c8436da981b51ade9a54429ce34/media/Initial%20Captionin.png)

* (4) will generate a caption & text file for every image, which stores the caption. You can alter this manually, by going into the text file, and changing the caption. Once this has been setup, you can close the colab notebook. Next, you will need to train the model using another colab notebook.

![File Structure for Images   Captions](https://github.com/soyunparrrk/Unflattering-Dataset/blob/69a351375a049c8436da981b51ade9a54429ce34/media/File%20Structure%20for%20Images%20%26%20Captions.png)

## (2) Training

Open and copy this notebook to your drive: [Lora Trainer](https://colab.research.google.com/drive/1-D0l9UdkmUx25EonusH0ZGtzqqPWgo_c#scrollTo=OglZzI_ujZq-)
  
In setup or section (1) you will need to refer back to the project name you had given in your last colab, and add it to the project name here. The training model we will use is 'AnyLora', if it is not selected already, you can do so by accessing the dropdown menu.

* Enable flip_aug
* Change the number of epochs to 20.
  
**_You can then run section (1) & Train!_**

Once the training has finished, you can download the fine-tuned models from the project folder. You should download the highest one/most recent.

## (3) Using it for Stable Diffusion

### (3-1) Add your model to the right directory on your Google Drive
After downloading the model, you will need to add it to the A111 model/lora directory. Add your model file (.safetensors) to your Google Drive in this path below.

** /content/gdrive/MyDrive/sd/stable-diffusion-web-ui/models/Lora **

### (3-2) Create images in Stable Diffusion with your own model

Open and copy this notebook to your drive: [Fast Stable Diffusion](https://colab.research.google.com/github/TheLastBen/fast-stable-diffusion/blob/main/fast_stable_diffusion_AUTOMATIC1111.ipynb#scrollTo=PjzwxTkPSPHf)

After excecuting all cells, start SDWebUI by clicking the link like this at the 'Start Stable-Diffusion' section: (https://xxx.gradio.live), and click on the LoRA tab.
![image](https://github.com/Caileannn/Unflattering-Dataset/assets/25906839/667b45ed-7bfd-447e-b814-8068ddff8ec5)

You can use this keyword anywhere in the prompt.

Some examples ✨

![swimming](https://github.com/Caileannn/Unflattering-Dataset/assets/25906839/2f28b8a3-b327-4c65-9ca8-5c9255de0dae)

![00044-3648499070](https://github.com/Caileannn/Unflattering-Dataset/assets/25906839/7e37faac-4d6a-4e18-bfd9-b74f077c4eda)

![00042-396555378](https://github.com/Caileannn/Unflattering-Dataset/assets/25906839/6dbdf04b-6360-4224-8331-680c0a6b658b)

![00034-1378921413](https://github.com/Caileannn/Unflattering-Dataset/assets/25906839/210e7b44-af93-44d7-bc0c-72528282bb50)





