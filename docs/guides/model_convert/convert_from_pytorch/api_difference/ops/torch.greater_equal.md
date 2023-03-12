## [ 仅参数名不一致 ]torch.greater_equal

### [torch.ge](https://pytorch.org/docs/1.13/generated/torch.greater_equal.html#torch.greater_equal)

```python
torch.greater_equal(input, other, *, out=None)
```

### [paddle.greater_equal](https://www.paddlepaddle.org.cn/documentation/docs/zh/api/paddle/greater_equal_cn.html#greater-equal)

```python
paddle.greater_equal(x, y, name=None)
```

其中 Pytorch 相比 Paddle 支持更多其他参数，具体如下：

### 参数映射
| PyTorch                          | PaddlePaddle                 | 备注                                                   |
|----------------------------------|------------------------------| ------------------------------------------------------ |
| <font color='red'> input </font> | <font color='red'> x </font> | 输入的 Tensor ，仅参数名不同。                                     |
| <font color='red'> other </font> | <font color='red'> y </font> | 输入的 Tensor ，仅参数名不同
| <font color='red'> out </font>   | -                            | 表示输出的 Tensor，PaddlePaddle 无此参数，需要进行转写。              |

### 转写示例

#### out：指定输出
```python
# Pytorch 写法
torch.greater_equal(torch.tensor([[1, 2], [3, 4]]), torch.tensor([[1, 1], [4, 4]]), out = y) # 同 y = torch.greater_equal(torch.tensor([[1, 2], [3, 4]]), torch.tensor([[1, 1], [4, 4]]))

# Paddle 写法
y = paddle.greater_equal(paddle.to_tensor([[1, 2], [3, 4]]), paddle.to_tensor([[1, 1], [4, 4]]))
```
