## Evaluation

The evaluation script is provided in `eval/evaluator.py`. 
We also provide `eval/eval.py` as an example to show how to use the evaluation script. 
In particular, `eval.py` expects as input the followings:
1. `fpath_pred`: path to the numpy array `pred` of your model prediction 
   (shape `(n_instances, n_class)`). `pred[i,j]` is the predicted probability 
   for attribute class `j` of instance `i`. We provide `test/pred.npy` as a sample 
   for this, which is the output of our best model (last row of table 2) in the paper.
2. `fpath_label`: path to the numpy array `gt_label` that contains the groundtruth label 
   of all instances in the test set (shape `(n_instances, n_class)`). `gt_label[i,j]` 
   equals 1 if instance `i` is labeled positive with attribute `j`, equals 0 if it is 
   labeled negative with attribute `j`, and equals 2 if it is unlabeled for attribute `j`. 
   We provide `eval/gt_label.npy` as a sample for this, which we have created from `data/test.json`.
3. Other files in folder `data` which have been set with default values in `eval/eval.py`.

From the `eval` folder, run the evaluation script as follows:
```
python test.py --fpath_pred pred.npy --fpath_label gt_label.npy
```
We recently updated the grouping of attributes, So, there is a small discrepancy 
between the scores of our `test/pred.npy` versus the numbers reported in the paper on each attribute group. 
A detailed attribute-wise breakdown will also be saved to `output_detailed.txt`.