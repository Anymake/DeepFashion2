# DeepFashion2 Dataset
DeepFashion2 is a comprehensive fashion dataset. It contains 491K diverse images of 13 popular clothing categories from both 
commercial shopping stores and consumers. It totally has 801K clothing clothing items, where each item in an image is labeled 
with scale, occlusion, zoom-in, viewpoint, category, style, bounding box, dense landmarks and per-pixel mask.There are also 873K Commercial-Consumer clothes pairs.\
We have 391K images for training, 34K images for validation and 67K images for test.\
Examples of DeepFashion2 are shown below:
![image](https://github.com/switchablenorms/DeepFashion2/blob/master/image/annotation.jpg)
<font size=8>*From (1) to (4), each row represents clothes images with different variations. At each row, we partition the images into two groups, the left three columns represent clothes from commercial stores, while the right three columns are from customers.In each group, the three images indicate three levels of difficulty with respect to the corresponding variation.Furthermore, at each row, the items in these two groups of images are from the same clothing identity but from two different domains, that is, commercial and customer.The items of the same identity may have different styles such as color and printing.Each item is annotated with landmarks and masks.*</font>
# Download the Data
Below provides the links to validation set. We will soon release training set and test set.
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
    * bounding box: [x1,y1,x2,y2]，where "x_1" and "y_1" represent the lower left point coordinate of bounding box, "x_2" and "y_2" represent the upper right point coordinate of bounding box. 
    * landmarks: [x1,y1,v1,...,xn,yn,vn], where v represents the visibility: v=2 visible; v=1 occlusion; v=0 not labeled.
    * segmentation: [[x1,y1,...xn,yn],[ ]], where [x1,y1,xn,yn] represents a polygon and a single clothing item may contain more than one polygon.
    * scale: a number, where 1 represents small scale, 2 represents modest scale and 3 represents large scale.
    * occlusion: a number, where 1 represents no occlusion, 2 represents partial occlusion and 3 represents heavy occlusion.
    * zoom-in: a number, where 1 represents no zoom-in, 2 represents medium zoom-in and 3 represents lagre zoom-in.
    * viewpoint: a number, where 1 represents no wear, 2 represents frontal viewpoint and 3 represents side or back viewpoint.
  * item 2\
  ...<br>
  * item n

In validation set, we provide query image names in (list_query.txt) and gallery image names in (list_gallery.txt). In Commercial-Consumer Clothes Retrieval benchmark, during evaluation, each query clothing item with style number greater than 0 has corresponding ground truth gallery clothing item.

# Dataset Statistics

# Citation
If you use the DeepFashion2 dataset in your work, please cite it as:
