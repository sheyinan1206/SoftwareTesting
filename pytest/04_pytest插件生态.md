# 所有插件
```
https://pytest.cn/en/stable/reference/plugin_list.html
```
# 常用插件

## pytest-html

1. 用途

    生成html测试报告

2. 参数

    --html=report.html

## pytest-xdist

1. 用途

    分布式执行用例

2. 参数

    -n{0,1,2,3,4,.....auto}

## pytest-order

1. 用途

    自定义用例的顺序

2. 标记

    @pytest.mark.order(1)

## pytest-rerunfailures

1. 用途

    当用例失败，重跑

2. 参数

    -rerun 5
