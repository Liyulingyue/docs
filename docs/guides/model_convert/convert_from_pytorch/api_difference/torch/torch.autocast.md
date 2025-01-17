## [torch 参数更多]torch.autocast

### [torch.autocast](https://pytorch.org/docs/stable/amp.html?highlight=autocast#torch.autocast)

```python
torch.autocast(device_type, dtype=None, enabled=True, cache_enabled=None)
```

### [paddle.amp.auto_cast](https://www.paddlepaddle.org.cn/documentation/docs/zh/develop/api/paddle/amp/auto_cast_cn.html)

```python
paddle.amp.auto_cast(enable=True, custom_white_list=None, custom_black_list=None, level='O1', dtype='float16', use_promote=True)
```

其中 PyTorch 相比 Paddle 支持更多其他参数，具体如下：

### 参数映射

| PyTorch       | PaddlePaddle      | 备注                                                                                                                                                                                  |
| ------------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| device_type   | -                 | 设备类型，Paddle 不区分设备，可直接删除。                                                                                                                                                  |
| enabled       | enable            | 是否开启自动混合精度。                                                                                                                                                                |
| dtype         | dtype             | 使用的数据类型。                                                                                                                                                                      |
| cache_enabled | -                 | 是否启用权重缓存，Paddle 无此参数，一般对网络训练结果影响不大，可直接删除。                                                                                                           |
| -             | custom_white_list | 自定义算子白名单，PyTorch 无此参数，Paddle 保持默认即可。                                                                                                                             |
| -             | custom_black_list | 自定义算子黑名单，PyTorch 无此参数，Paddle 保持默认即可。                                                                                                                             |
| -             | level             | 混合精度训练模式，PyTorch 无此参数，Paddle 保持默认即可。                                                                                                                             |
| -             | use_promote       | 当一个算子存在 float32 类型的输入时，按照 Promote to the Widest 原则，选择 float32 数据类型进行计算。仅在 AMP-O2 训练时可配置。默认为 True。PyTorch 无此参数，Paddle 保持默认即可。 |
