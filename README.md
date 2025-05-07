# NUS-WIDE

## Dataset Access
The dataset can be accessed from [huggingface](https://huggingface.co/datasets/Lxyhaha/NUS-WIDE).

## Dataset Overview
The NUS-WIDE dataset is a large-scale multi-label image dataset that can be widely used for image classification and multi-label learning tasks. It contains **269,648 images** collected from Flickr, annotated with **81 concept labels** .
```
Training set：161,789 images
Test set：107,859 images
```
## Dataset Directory Structure
```
NUS-WIDE
├── Groundtruth
│   ├── TrainTestLabels
│   │   ├── Labels_zebra_Train.txt 
│   │   ├── Labels_zebra_Test.txt
│   │   ├── Labels_window_Train.txt
│   │   ├── Labels_window_Test.txt
│   │   └── ···
│   ├── AllLabels
│   │   ├── Labels_zebra.txt
│   │   ├── Labels_window.txt
│   │   └── ···
├── ConceptsList
│   ├── Concepts81.txt
│   └── Concepts81.mat

NUS_WID_Tags
├── Train_Tags81.txt
├── Train_Tags1k.dat
├── Test_Tags81.txt
├── Test_Tags1k.dat
├── TagList1k.txt
├── Final_Tag_List.txt
├── All_Tags.txt
├── AllTags81.txt
├── AllTags1k.txt

```
After downloading the dataset, it contains two zip files: `NUS-WIDE.zip`and `NUS_WID_Tags.zip`.

## Folder and File Description

### NUS-WIDE.zip
This archive contains two folders: `Groundtruth` and `ConceptsList`.
 
#### **- Groundtruth**
This folder contains two subfolders: `TrainTestLabels` and `AllLabels`.
- **TrainTestLabels**: Contains 162 `.txt` files in total.  
  - `Labels_<concept>_Train.txt` and `Labels_<concept>_Test.txt` represent the labels for 81 concepts on the training and test sets, respectively.  
  - Each file contains one row per image, with a binary value (`0` or `1`) indicating whether the image belongs to the corresponding concept.  
  - The training set contains 161,789 samples, and the test set contains 107,859 samples.
- **AllLabels**: Contains 81 `.txt` files, each corresponding to one concept.  
  - Each file contains 269,648 lines, with `0` or `1` indicating whether the image belongs to that concept, covering the full dataset (training + test).

#### **- ConceptsList** 
This folder provides the list of 81 predefined concept names used in the dataset.

### NUS_WID_Tags.zip
This archive contains 9 files, with descriptions as follows:

#### **- Train_Tags81.txt, Test_Tags81.txt**  
Contain the labels for the training and test sets in terms of the 81 predefined concepts.  
- Each row is an 81-dimensional binary vector, where `1` indicates that the sample belongs to the corresponding concept, and `0` otherwise.

#### **- Train_Tags1k.dat, Test_Tags1k.dat**  
Contain the labels for the training and test sets in terms of 1000 tags.  
- Each row is a 1000-dimensional binary vector representing tag presence.

#### **- TagList1k.txt**  
A list of the 1000 tag names used in the 1k-tag representation.

#### **- Final_Tag_List.txt**  
A refined list of 5018 tags, as referenced in the original NUS-WIDE paper:  
> *NUS-WIDE: A Real-World Web Image Database from National University of Singapore*

These tags were filtered and processed from the original Flickr tag data.

#### **- All_Tags.txt, AllTags81.txt, AllTags1k.txt**  
These files provide binary matrices indicating tag presence for all 269,648 images:

- `All_Tags.txt`: 269,648 × 5018 binary matrix (5018 tag space)
- `AllTags81.txt`: 269,648 × 81 binary matrix (concept label space)
- `AllTags1k.txt`: 269,648 × 1000 binary matrix (1000 tag space)

## Citation
If you use the NUS-WIDE dataset in your research or publications, please cite the following paper:

```
@inproceedings{chua2009nus,
  title={Nus-wide: a real-world web image database from national university of singapore},
  author={Chua, Tat-Seng and Tang, Jinhui and Hong, Richang and Li, Haojie and Luo, Zhiping and Zheng, Yantao},
  booktitle={Proceedings of the ACM international conference on image and video retrieval},
  pages={1--9},
  year={2009}
}
