# Data Collection
After determining a problem statement or objective, the next step in any ML/DL problem is to understand the data that will be gathered, and to ensure that it's expansive enough to provide as robust of a model as possible.

## Characteristics of the Data

Since this is a multi-classifcation problem, there needs to be enough data for each "class" or breed of dog. This requires not only enough images of each breed, but with enough variety and diversity that the model can generalize well during inference.
This would imply some images with:
* Multiple dogs (both same and different breeds)
* Breeds with different physical traits (e.g. Black and red vs all white German Shepherds)
* With and without humans
* Various settings (contrast against a snowy background vs a living room)

## Acquiring the Data

[**Fatkun Batch Download Image**](https://chrome.google.com/webstore/detail/fatkun-batch-download-ima/nnjjahlikiabnchcpehcpkdeckfgnohf?hl=en) is a Chrome extension that aggregates all image files open in your Chrome browser or tab. Images can be filtered based on size and then saved.

![picture](https://github.com/ParthivNaresh/Dogs-ObjectDetection-SageMaker/blob/DataAcquisition/DataCollection/Fatkun_01.jpg)

> Chrome has a default setting that initiates a popup asking you to confirm where you want to save each file.
This needs to be turned off before downloading hundreds of images otherwise you'll spend half your time accepting dialogues.
Choose a default location and fire away.

![picture](https://github.com/ParthivNaresh/Dogs-ObjectDetection-SageMaker/blob/DataAcquisition/DataCollection/Fatkun_02.jpg)

![picture](https://github.com/ParthivNaresh/Dogs-ObjectDetection-SageMaker/blob/DataAcquisition/DataCollection/Fatkun_03.jpg)

This step will take a while as you try to collect as much data as possible. For organizational purposes keep different folders for each breed. Download as many images as you want, these models rely on a lot of data so you can't have too much.

## Creating an S3 Bucket

Amazon Simple Storage Service (S3) is a way to store data within the AWS ecosystem. The AWS Command Line Interface (CLI) and the AWS SDK (Boto3) allow for easy management of this data. We'll be using both of these later, but for now we need to create the S3 bucket where all of our dog images will go for easy access.

