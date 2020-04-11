## Baseline 

The `dataset` argument specifies which dataset to use: `cifar10` or `cifar100`. The `arch` argument specifies the architecture to use: `vgg`,`resnet` or
`densenet`. The depth is chosen to be the same as the networks used in the paper.
```shell
```

## Train, prune 70% of channels, retrain with Scratch-E

```shell
python main.py --dataset cifar10 --arch vgg --depth 16
python vggprune.py --dataset cifar10 --depth 16 --percent 0.7 --model logs/model_best.pth.tar --save logs_70/
python main_E.py --scratch logs_70/pruned.pth.tar --dataset cifar10 --arch vgg --depth 16

```