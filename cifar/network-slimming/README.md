## Train, prune a percentage of channels, retrain with Scratch-E on VGG-16

70%
```shell
python main.py --dataset cifar10 --arch vgg --depth 16
python vggprune.py --dataset cifar10 --depth 16 --percent 0.7 --model logs/model_best.pth.tar --save logs_70/
python main_E.py --scratch logs_70/pruned.pth.tar --dataset cifar10 --arch vgg --depth 16 --save logs_70/

```

50%
```shell
python main.py --dataset cifar10 --arch vgg --depth 16
python vggprune.py --dataset cifar10 --depth 16 --percent 0.5 --model logs/model_best.pth.tar --save logs_50/
python main_E.py --scratch logs_50/pruned.pth.tar --dataset cifar10 --arch vgg --depth 16 --save logs_50/

```
