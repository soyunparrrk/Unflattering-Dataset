# Unflattering-Dataset
In this workshop, the students learn the process of image classification for training text-to-image AI models and build their own small, ‘unflattering’ dataset to experiment with the tools and share their thoughts about the machinery but personal process.

## Processes behind Dataset Curation & Creation

🡥 Preprocess Data: Crop, Resize, Label. <br/>
🡥 Training: How to train the model, what settings are needed <br/>
🡥 Inference: How to use your trained model with text-to-image models <br/>

## Preprocess: What will we need?

* Small Collection of Images ~20-50 (the more the better)
* For faces or portraits the number of images can be lower, but for more complex objets, styles, concepts ~50-100 images are needed.
* A Pre-Trained Model: We will need a LARGE model which has already has a understanding of objects, styles, text/image knowledge. In this workshop, it would be best to use LoRA which is really good for quickly finetuning a model off of your data.
* [Breakdown of LoRA](https://softwarekeep.com/help-center/how-to-use-stable-diffusion-lora-models)
* [A111 SD Notebook](https://github.com/AUTOMATIC1111/stable-diffusion-webui)
* Training Images can be JPG or PNG.
* Mininum size of training images 512x512. The larger the images the better.
* [Use this site to batch crop & rename images](https://www.birme.net/?image_format=jpeg&quality_jpeg=100&rename=EnterNameHere-XXX)
* Settings for Birme: JPG (100%), 512 x 512, Save as Zip)
* You can then use this Dataset cleaner colab notebook [here](https://colab.research.google.com/drive/1pxk4SovIhZl4HaLmBJo50ZjCKOuofMwb#scrollTo=WBFik7accyDz)
* This will be used to prepare the images as a dataset for LoRA. It will also create captions for each image, which you can alter manually.
* Project Name -> Whatever you want, and keep a note of this.
* Then you can start section (1) Setup
* Once (1) is finished, go to section (4), and change the method to 'Photo Caption' - You can black list some words if you want to.
* (4) will generate a caption & text file for every image, which stores the caption.
* You can alter this manually, by going into the text file, and changing the caption.
* Once this has been setup, you can close the colab notebook.
* Next, you will need to train the model using another colab notebook.
* [Lora Trainer](https://colab.research.google.com/drive/1-D0l9UdkmUx25EonusH0ZGtzqqPWgo_c#scrollTo=OglZzI_ujZq-)
* In setup or section (1) you will need to refer back to the project name you had given in your last colab, and add it to the project name here.
* The training model we will use is 'AnyLora', if it is not selected already, you can do so by accessing the dropdown menu.
* Enable flip_aug
* Change the number of epochs to 20.
* You can then run section (1) & Train!

Once the training has finished, you can download the fine-tuned models from the project folder. You should download the highest one/most recent.

After downloading the model, you will need to add it to the A111 model/lora directory.

_Maybe you have a preffered SDWebUI that you have used in other workshops, or you can use [this](https://colab.research.google.com/github/TheLastBen/fast-stable-diffusion/blob/main/fast_stable_diffusion_AUTOMATIC1111.ipynb#scrollTo=PjzwxTkPSPHf)_

Start SDWebUI, and click on the additional networks tab, and select the lora model you have trained.

You can use this keyword anywhere in the prompt.

