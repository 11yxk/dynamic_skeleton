# dynamic_skeleton
Pytorch Implementation of paper '' A Module Selection-based Approach for Efficient Skeleton Human Action Recognition''

# Data Preparation
Please follow the instructions of a https://github.com/Uason-Chen/CTR-GCN
# Training & Testing

### Training

```
# Example: training network on NTU RGB+D 60 cross subject
python main.py --config ./config/nturgbd-cross-subject/default.yaml
```
### Testing

- For example, to test the joint modality of nturgbd-cross-subject dataset using second scheme, run the following command:
```
python main.py --config ./config/nturgbd-cross-subject/default.yaml --phase test --save-score True --weights weight/CS_joint.pt --model model.dynamic_ctrgcn_scheme2_test.Model
```

- To ensemble the results of different modalities, run 
```
# Example: ensemble four modalities on NTU RGB+D 60 cross subject
python ensemble.py --datasets ntu/xsub --joint-dir work_dir/ntu/csub/ctrgcn --bone-dir work_dir/ntu/csub/ctrgcn_bone --joint-motion-dir work_dir/ntu/csub/ctrgcn_motion --bone-motion-dir work_dir/ntu/csub/ctrgcn_bone_motion
```

### Pretrained Models

- Pretrained Models are placed in the folder /weights.


## Acknowledgements

This repo is based on [CTR-GCN](https://github.com/Uason-Chen/CTR-GCN).

Thanks original authors for their work!
