# Self-Supervised Monocular Depth Hints


**Jamie Watson, [Michael Firman](http://www.michaelfirman.co.uk), [Gabriel J. Brostow](http://www0.cs.ucl.ac.uk/staff/g.brostow/) and [Daniyar Turmukhambetov](https://dantkz.github.io) – ICCV 2019**

[[Link to paper]](https://arxiv.org/abs/1909.09051)

<p align="center">
  <img src="assets/kitti.gif" alt="example input output gif" width="700" />
</p>

**We introduce *Depth Hints*, which improve monocular depth estimation algorithms trained from stereo pairs.**

We find that photometric reprojection losses used with self-supervised learning typically have multiple local minima.   
This can restrict what a regression network learns, for example causing artifacts around thin structures.

**Depth Hints are complementary depth suggestions obtained from simple off-the-shelf stereo algorithms**, e.g. Semi-Global Matching.
These hints are used during training to guide the network to learn better weights.
They require no additional data, and are assumed to be right only sometimes.

Combined with other good practices, Depth Hints gives **state-of-the-art depth predictions on the KITTI benchmark** (see images above and results table below).
We show additional monocular depth estimation results on the [sceneflow dataset](https://lmb.informatik.uni-freiburg.de/resources/datasets/SceneFlowDatasets.en.html):

<p align="center">
  <img src="assets/sceneflow.gif" alt="example input output gif" width="700" />
</p>

## ✏️ 📄 Citation


If you find our work useful or interesting, please consider citing [our paper](https://arxiv.org/abs/1909.09051):

```
@inproceedings{watson-2019-depth-hints,
  title     = {Self-Supervised Monocular Depth Hints},
  author    = {Jamie Watson and
               Michael Firman and
               Gabriel J. Brostow and
               Daniyar Turmukhambetov},
  booktitle = {ICCV},
  year      = {2019}
}
```


## 📈 KITTI Results

| Model name | Training modality | ImageNet pretrained | Resolution | Abs rel | Sq rel | 𝛿 < 1.25 |
| ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ----- |
| Ours Resnet50 | Stereo | Yes | 640 x 192 | 0.102 | 0.762 | 0.880 | 
| Ours Resnet50 no pt | Stereo | No | 640 x 192 | 0.118 | 0.941 | 0.850 |
| Ours HR Resnet50 | Stereo | Yes | 1024 x 320 | 0.096 | 0.723 | 0.890 |
| Ours HR Resnet50 no pt | Stereo | No | 1024 x 320 | 0.112 | 0.857 | 0.861 |
| Ours HR | Mono + Stereo | Yes | 1024 x 320 | 0.098 | 0.702 | 0.887 |

Please see the paper for full results.


## ⚙️ Code

Coming soon!

In the meantime check out our [monodepth2](https://github.com/nianticlabs/monodepth2) repository for depth estimation from monocular and stereo training data.
