# Visual Attributes in the Wild (VAW)

This repository provides data for the VAW dataset as described in the <a href="https://openaccess.thecvf.com/content/CVPR2021/html/Pham_Learning_To_Predict_Visual_Attributes_in_the_Wild_CVPR_2021_paper.html" target="_blank">CVPR 2021</a> Paper:

### [Learning to Predict Visual Attributes in the Wild](https://openaccess.thecvf.com/content/CVPR2021/html/Pham_Learning_To_Predict_Visual_Attributes_in_the_Wild_CVPR_2021_paper.html)
[Khoi Pham](https://scholar.google.com/citations?user=o7hS8EcAAAAJ&hl=en),
[Kushal Kafle](https://kushalkafle.com), 
[Zhihong Ding](https://research.adobe.com/person/zhihong-ding/),
[Zhe Lin](https://research.adobe.com/person/zhe-lin/),
[Quan Tran](https://research.adobe.com/person/quan-hung-tran/),
[Scott Cohen](https://research.adobe.com/person/scott-cohen/),
[Abhinav Shrivastava](http://www.cs.umd.edu/~abhinav/)
 
![VAW Main Image](images/vaw_hero.png)

# Dataset Setup

Our VAW dataset is partly based on the annotations in the 
[GQA](https://cs.stanford.edu/people/dorarad/gqa/about.html) and 
the [VG-PhraseCut](https://github.com/ChenyunWu/PhraseCutDataset) datasets.  
Therefore, the images in the VAW dataset come from the [Visual Genome](https://visualgenome.org/) dataset which is also the source of the images in the GQA and the VG-Phrasecut datasets. 
This section outlines the annotation format and basic statistics of our dataset.

## Annotation Format

The annotations are found in ``data/train_part1.json``, ``data/train_part2.json`` , `data/val.json` and `data/test.json` for train (split into two parts to circumvent github file-size limit) , validation and test splits in the VAW dataset respectively.
The files consist of the following fields:

```
image_id: int (Image ids correspond to respective Visual Genome image ids)
instance_id: int (Unique instance ID)
instance_bbox: [x, y, width, height] (Bounding box co-ordinates for the instance)
instance_polygon: list of [x y] (List of vertices for segmentation polygon if exists else None)
object_name: str (Name of the object for the instance)
positive_attributes: list of str (Explicitly labeled positive attributes for the instance)
negative_attributes: list of str (Explicitly labeled negative attributes for the instance)
```

## Download Images

The images can be downloaded from the [Visual Genome](https://visualgenome.org/) website. 
The image_id field in our dataset corresponds to respective image ids in the v1.4 in the Visual Genome dataset.

## Explore Data and View Live Demo
Head over to [our accompanying website](http://vawdataset.com) to explore the dataset. 
The website allows exploration of the VAW dataset by filtering our annotations by objects, positive attributes, or negative attributes in the 
train/val set. The website also shows interactive demo for our SCoNE algorithm as described in our paper.

# Dataset Statistics

### Basic Stats

| Detail      |  Stat |
| :---        |    :----:   |
| Number of Instances      | 260,895       |
| Number of Total Images   | 72,274        |
| Number of Unique Attributes   | 620        |
| Number of Object Categories   | 2260        |
| Average Annotation per Instance (Overall)  | 3.56        |
| Average Annotation per Instance  (Train)  | 3.02       |
| Average Annotation per Instance  (Val)  | 7.03      |

# Citation
Please cite our CVPR 2021 paper if you use the VAW dataset or the SCoNE algorithm in your work.

````
@inproceedings{pham2021vaw,
  title={Learning to Predict Visual Attributes in the Wild},
  author={Pham, Khoi and Kafle, Kushal and Ding, Zhihong and Lin, Zhe and Tran, Quan and Cohen, Scott and Shrivastava, Abhinav},
  booktitle={CVPR},
  year={2021}
}
````

## Disclaimer and Contact

This dataset contains objects labeled with a variety of attributes, including those applied to people. 
Datasets and their use are the subject of important ongoing discussions in the AI community, 
especially datasets that include people, and we hope to play an active role in those discussions. 
If you have any feedback regarding this dataset, we welcome your input at `kkafle@adobe.com`
