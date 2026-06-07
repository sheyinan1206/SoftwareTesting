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

    当用例失败，重跑(因为网络原因失败的情况下好用）

2. 参数

    --reruns 5

## pytest-result-log

1. 用途

    日志中记录用例的结果

2. 配置文件

```
log_file = ./logs/pytest.log
log_file_level = INFO
log_file_format = %(asctime)s %(levelname)s %(message)s
log_file_date_format = %Y-%m-%d %H:%M:%S

result_log_enable = true
result_log_separator = 1
result_log_level_separator = warning
result_log_level_verbose = info
```

## allure-pytest

1. 用途

    生成allure结果文件

2. 参数


   
