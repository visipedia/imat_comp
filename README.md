![banner](assets/banner.jpg)

# iMaterialist Competition - Fashion

# 2019 Competition
The 2019 competition, sponsored by Google, is part of the [FGVC6 workshop](http://fgvc.org) at [CVPR](http://cvpr2019.thecvf.com/). 

Please open an issue if you have questions or problems with the dataset.



## Kaggle
We are using Kaggle to host the leaderboard. Checkout the competition page [here](https://www.kaggle.com/c/imaterialist-challenge-fashion-2019).



## Dates (TBD)
|||
|----|---------------|
Data Released| April 2019|
Submission Server Open | TBD|
Submission Deadline|  TBD|
Winners Announced| June 2019|



## Details

Visual analysis of clothing is a topic that has received increasing attention in recent years. Being able to recognize apparel products and associated attributes from pictures could enhance shopping experience for consumers, and increase work efficiency for fashion professionals.

We present a new clothing dataset with the goal of introducing a novel fine-grained segmentation task by joining forces between the fashion and computer vision communities. The proposed task unifies both categorization and segmentation of rich and complete apparel attributes, an important step toward real-world applications. While early work in computer vision addressed related clothing recognition tasks, these are not designed with fashion insiders’ needs in mind, possibly due to the research gap in fashion design and computer vision. To address this, we first propose a fashion taxonomy built by fashion experts, informed by product description from the internet. To capture the complex structure of fashion objects and ambiguity in descriptions obtained from crawling the web, our standardized taxonomy contains **46** apparel objects (**27** main apparel items and **19** apparel parts), and **92** related fine-grained attributes. Secondly, a total of 50K clothing images (10K with both segmentation and fine-grained attributes, 40K with apparel instance segmentation) in daily-life, celebrity events, and online shopping are labeled by both domain experts and crowd workers for fine-grained segmentation.

In this competition, we challenge you to develop algorithms that will help with an important step towards automatic product detection – to accurately assign segmentations and attribute labels for fashion images. Individuals/Teams with top submissions will be invited to present their work live at the FGVC6 workshop.



![example](assets/example.jpg)

For more information on the Evaluation Metric, Data / Submission Format, Rules and participating the iMaterialist Competition, please see the [Kaggle challenge page](https://www.kaggle.com/c/imaterialist-challenge-fashion-2019).



## Details

There are a total of 46 apparel objects annotated with segmentations, 92 fine-grained attributes for each apparel item segmentations, with 41,403 training and 7,241 validation images.

Apparel instance segmentations include 27 main apparel objects  (jackets, dresses, skirts, etc) and 19 apparel parts (sleeves, collars, etc). A total of 92 fine-grained attributes was annotated by expert for main apparel objects.

| Annotation Types                       | Train  | Val   | Test  | Total  |
| -------------------------------------- | ------ | ----- | ----- | ------ |
| Instances                              | 34,128 | 6,023 | 0     | 40,151 |
| Instances with fine-grained attributes | 6,975  | 1,218 | 2,048 | 10,241 |
| Total                                  | 41,403 | 7,241 | 2,048 | 50,392 |



## Annotation Format

We follow the annotation format of the [COCO dataset](http://mscoco.org/dataset/#download) and add additonal fields, such as attributes. The annotations are stored in the [JSON format](http://www.json.org/) and are organized as follows: 

```
{
 "info": info,
 "categories": [category],
 "attributes": [attribute],
 "images": [image],
 "annotations": [annotation],
 "licenses": [license]
}

info{
  "year" : int,
  "version" : str,
  "description" : str,
  "contributor" : str,
  "url" : str,
  "date_created" : datetime,
}

category{
  "id" : int,
  "name" : str,
  "supercategory" : str,  # parent of this label
  "level": int,           # levels in the taxonomy
  "taxonomy_id": string,
}

attribute{
  "id" : int,
  "name" : str,
  "supercategory" : str,  # parent of this label
  "level": int,           # levels in the taxonomy
  "taxonomy_id": string,
}

image{
  "id" : int,
  "width" : int,
  "height" : int,
  "file_name" : str,
  "license" : int,
  "time_captured": string,
  "original_url": string,
  "isstatic": int, 
}

annotation{
  "id" : int,
  "image_id" : int,
  "category_id" : int,
  "attribute_ids": [int],
  "segmentation" : [polygon],
  "bbox" : [x,y,width,height],
  "area" : int,
  "iscrowd": int,
}

polygon[x1, y1, x2, y2, ...], where x, y are the coordinates of vertices, int

license{
  "id" : int,
  "name" : str,
  "url" : str
}
```



## Differences from iMat Fashion 2018

Whereas iMat-Fashion-2018 covered fine-grained attributes classification, this year our competition introduces a novel task, which is to jointly learn apparel instance segmentation with fine-grained attributes classification. Our 2019 dataset also propose a fashion taxonomy built by fashion experts, with total 149 apparel categories and attributes. 

For more details on iMat Fashion 2018, please see [this page](https://www.kaggle.com/c/imaterialist-challenge-fashion-2018).

