# DeepFashion2 Dataset
DeepFashion2 is a comprehensive fashion dataset. It contains 491K diverse images of 13 popular clothing categories from both 
commercial shopping stores and consumers. It totally has 801K clothing clothing items, where each item in an image is labeled 
with category, style, bounding box, dense landmarks and per-pixel mask.There are also 873K Commercial-Consumer clothes pairs.\
We have 391K images for training, 34K images for validation and 67K images for test.

# Download the Data
Below provides the links to validation set. We wil soon release training set and test set.
* Images(...)
* Annotations(...)

# Data Organization
Each image in seperate image set has a unique six-digit number such as 000001.jpg. A corresponding annotation file in json
format is provided in annotation set such as 000001.json. \
Each annotation file is organized as below: 
* source: a string, where 'shop' indicates that the image is from commercial store while 'user' indicates that the image is 
taken by users.
* pair id: a number. Images from the same shop and their corresponding consumer-taken images have the same pair id.
  * item 1 
    * category name: a string indicating the category of the item.
    * category id: a number corresponding to the category name.
    * style: a number to distinguish between clothing items from images with the same pair id. Clothing items with different 
    style numbers from images with the same pair id have different styles such as color, printing, and logo. In this way, a 
    clothing item from shop images and a clothing item from user image are positive commercial-consumer pair if they have the same
    style number greater than 0 and they are from images with the same pair id.
    * bounding box: [x1,x2,y1,y2].
    * landmarks: [x1,y1,v1,...,xn,yn,vn], where v represents the visibility: v=2 visible; v=1 occlusion; v=0 not labeled.
    * segmentation: [[x1,y1,...xn,yn],[ ]], where [x1,y1,xn,yn] represents a polygon and a single clothing item may need more than 
    one polygon.
  * item 2\
  ...<br>
  * item n

In validation set, we provide query image names in (query.txt) and gallery image names in (gallery.txt). In Commercial-Consumer Clothes Retrieval benchmark, during evaluation, each query clothing item with style number greater than 0 has ground truth corresponding gallery clothing item.

# Dataset Statistics

# Citation
If you use the DeepFashion2 dataset in your work, please cite it as:
