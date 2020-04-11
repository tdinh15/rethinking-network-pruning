## Baseline 

The `dataset` argument specifies which dataset to use: `cifar10` or `cifar100`. The `arch` argument specifies the architecture to use: `vgg`,`resnet` or
`densenet`. The depth is chosen to be the same as the networks used in the paper.
```shell
python main.py --dataset cifar10 --arch vgg --depth 16
```

## Prune

```shell
python vggprune.py --dataset cifar10 --depth 16 --percent 0.7 --model logs/model_best.pth.tar --save logs_70/
```
The pruned model will be named `pruned.pth.tar`.


## Scratch-E
```
python main_E.py --scratch logs_70/pruned.pth.tar --dataset cifar10 --arch vgg --depth 16
```
