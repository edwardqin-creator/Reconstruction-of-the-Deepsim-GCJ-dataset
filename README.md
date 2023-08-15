# Clone Detection (GCJ)

This project is a  reconstruction version of **DeepSIM: Deep Learning Code Functional Similarity** 's Google Code Jam(GCJ) dataset.

The [original dataset format](https://github.com/parasol-aser/deepsim/tree/master/dataset) provided by the author is complicated and must be stored by matrices for latter use, so we followed the design of [CodeXGLUE -- Clone Detection(BCB)](https://github.com/microsoft/CodeXGLUE/tree/main/Code-Code/Clone-detection-BigCloneBench)  and reconstruct the original raw dataset into the corresponding format.



## Task Definition

Given two codes as the input, the task is to do binary classification (0/1), where 1 stands for semantic equivalence and 0 for others. Models are evaluated by F1 score.



## Dataset

### Data Format

1. GCJ/googlejam4.tar.gz contains the raw data consisting of projects collected from the Google Code Jam (GCJ) competition. The authors claim to have collected 1,669 projects from 12 competition problems. However, upon analyzing this file, we found that they have provided [only 1,665 projects](https://github.com/parasol-aser/deepsim/issues/9) from the 12 competition problems.
2. data.jsonl is stored in jsonlines format. Each line in the uncompressed file represents one function. One row is illustrated below.
   - **func:** the function
   - **idx:** index of the example
3. train.txt/valid.txt/test.txt provide examples, stored in the following format: idx1 idx2 label

### Data Statistics

|       | #Examples | label==1 | label==0 |
| :---: | :-------: | :------: | :------: |
| Train |  720,345  |  19.87%  |  80.13%  |
| Valid |  332,467  |  19.79%  |  80.21%  |
| Test  |  332,468  |  19.87%  |  80.13%  |


