# dynamic_skeleton
Pytorch Implementation of paper '' A Module Selection-based Approach for Efficient Skeleton Human Action Recognition''.
Our method can be easily combined to other state-of-the-art skeleton-based backbone networks, we provide [CTR-GCN](https://github.com/Uason-Chen/CTR-GCN) as backbone in this repo.

# Data Preparation
Please follow the instructions of https://github.com/Uason-Chen/CTR-GCN
# Training & Testing

### Training

```
# Example: training network on NTU RGB+D 60 cross subject
python main.py --config ./config/nturgbd-cross-subject/default.yaml
```
### Testing

```
# Example: testing the joint modality of nturgbd-cross-subject dataset using second scheme
python main.py --config ./config/nturgbd-cross-subject/default.yaml --phase test --save-score True --weights weight/CS_joint.pt --model model.dynamic_ctrgcn_scheme2_test.Model
```

- To ensemble the results of different modalities, run:
```
# Example: ensemble four modalities on NTU RGB+D 60 cross subject
python ensemble.py --datasets ntu/xsub --joint-dir work_dir/ntu/xsub/ctrgcn --bone-dir work_dir/ntu/xsub/ctrgcn_bone --joint-motion-dir work_dir/ntu/xsub/ctrgcn_motion --bone-motion-dir work_dir/ntu/xsub/ctrgcn_bone_motion
```

### Pretrained Models

- Pretrained Models are placed in the folder ./weights.


## Acknowledgements

This repo is based on [CTR-GCN](https://github.com/Uason-Chen/CTR-GCN).

Thanks original authors for their work!
