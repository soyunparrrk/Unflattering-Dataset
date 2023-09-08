# Unflattering-Dataset
In this workshop, the students learn the process of image classification for training text-to-image AI models and build their own small, ‘unflattering’ dataset to experiment with the tools and share their thoughts about the machinery but personal process.

## Processes behind Dataset Curation & Creation

🡥 (1) Preprocess Data: Crop, Resize, Label. <br/>
🡥 (2) Training: How to train the model, what settings are needed <br/>
🡥 (3) Inference: How to use your trained model with text-to-image models <br/>

## (1) Preprocess Data

* Small Collection of Images ~20-50 (the more the better)
  
* For faces or portraits the number of images can be lower, but for more complex objets, styles, concepts ~50-100 images are needed.
* A Pre-Trained Model: We will need a LARGE model which has already has a understanding of objects, styles, text/image knowledge. In this workshop, it would be best to use LoRA which is really good for quickly finetuning a model off of your data.
  
[Breakdown of LoRA](https://softwarekeep.com/help-center/how-to-use-stable-diffusion-lora-models) and [A111 SD Notebook](https://github.com/AUTOMATIC1111/stable-diffusion-webui)

* Training Images can be JPG or PNG.
* Mininum size of training images 512x512. The larger the images the better.
* [Use this site to batch crop & rename images](https://www.birme.net/?image_format=jpeg&quality_jpeg=100&rename=EnterNameHere-XXX)
* Settings for Birme: JPG (100%), 512 x 512, Save as Zip)

<br/>![Brime Cropping](https://github.com/Caileannn/Unflattering-Dataset/assets/25906839/838d8abc-08c1-4a17-a2fc-660d6e6110d6)
  
You can then use this Dataset cleaner colab notebook [here](https://colab.research.google.com/drive/1pxk4SovIhZl4HaLmBJo50ZjCKOuofMwb#scrollTo=WBFik7accyDz). This will be used to prepare the images as a dataset for LoRA. It will also create captions for each image, which you can alter manually.

* Project Name -> Whatever you want, and keep a note of this.
Then you can start section (1) Setup. Once (1) is finished, go to section (4), and change the method to 'Photo Caption' - You can black list some words if you want to.

![Initial Captionin](https://github.com/Caileannn/Unflattering-Dataset/assets/25906839/b28f7470-1460-46d6-8cbc-96378fd43818)

(4) will generate a caption & text file for every image, which stores the caption. You can alter this manually, by going into the text file, and changing the caption. Once this has been setup, you can close the colab notebook. Next, you will need to train the model using another colab notebook.

![File Structure for Images   Captions](https://github.com/Caileannn/Unflattering-Dataset/assets/25906839/a25ea580-977d-4fc2-ad0f-d482b1968c85)

## (2) Training

Open this notebook: [Lora Trainer](https://colab.research.google.com/drive/1-D0l9UdkmUx25EonusH0ZGtzqqPWgo_c#scrollTo=OglZzI_ujZq-)
  
In setup or section (1) you will need to refer back to the project name you had given in your last colab, and add it to the project name here. The training model we will use is 'AnyLora', if it is not selected already, you can do so by accessing the dropdown menu.

* Enable flip_aug
* Change the number of epochs to 20.
  
**_You can then run section (1) & Train!_**

Once the training has finished, you can download the fine-tuned models from the project folder. You should download the highest one/most recent.

After downloading the model, you will need to add it to the A111 model/lora directory.

_Maybe you have a preffered SDWebUI that you have used in other workshops, or you can use [this](https://colab.research.google.com/github/TheLastBen/fast-stable-diffusion/blob/main/fast_stable_diffusion_AUTOMATIC1111.ipynb#scrollTo=PjzwxTkPSPHf)_

Start SDWebUI, and click on the LoRA tab to add your model.

![image](https://github.com/Caileannn/Unflattering-Dataset/assets/25906839/667b45ed-7bfd-447e-b814-8068ddff8ec5)

You can use this keyword anywhere in the prompt.

Some examples ✨
![swimming](https://github.com/Caileannn/Unflattering-Dataset/assets/25906839/2f28b8a3-b327-4c65-9ca8-5c9255de0dae)

![00044-3648499070](https://github.com/Caileannn/Unflattering-Dataset/assets/25906839/7e37faac-4d6a-4e18-bfd9-b74f077c4eda)

![00042-396555378](https://github.com/Caileannn/Unflattering-Dataset/assets/25906839/6dbdf04b-6360-4224-8331-680c0a6b658b)

![00034-1378921413](https://github.com/Caileannn/Unflattering-Dataset/assets/25906839/210e7b44-af93-44d7-bc0c-72528282bb50)





