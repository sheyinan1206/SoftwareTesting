# YAML数据驱动测试

## 数据文件类型

1. 二维表格

    csv、excel

2. 多维对象

    json、yaml

## 安装YAML库

```
pip install pyyaml
```

1. 序列化

    把程序内的数据转为文件

2. 反序列化

    把文件内的数据转为程序变量

## 手写yaml

1. 标量

2. 数组

3. 对象

4. 注释

5. 完全兼容json

## 封装DDT装饰器（数据驱动测试）门槛

# Web自动化实战

## 插件

1. pytest-selenium

```
pip install pytest-selenium
```

2. 配置

```
--driver=chrome
```

3. fixtures

    - 启动浏览器
    - 关闭浏览器
    - 访问被测页面

4. 测试用例

    - 浏览器操作
    - 元素定位
    - 元素操作
    - 断言

```
# 测试网站
http://116.62.63.211/shop/?s=user/loginInfo.html

#日志，截图，其他信息
selenium_capture_debug = always
```

5. yaml文件

    - 测试数据
    - 预期结果

```
allure-pytest=2.16.0
allure-python-commons=2.16.0
attrs=26.1.0
certifi=2026.5.20
cffi=2.0.0
charset-normalizer=3.4.7
colorama=0.4.6
h11=0.16.0
idna=3.16
iniconfig=2.3.0
Jinja2=3.1.6
MarkupSafe=3.0.3
outcome=1.3.0.post0
packaging=26.2
pip=25.0.1
pluggy=1.6.0
pycparser=3.0
Pygments=2.20.0
PySocks=1.7.1
pytest=9.0.3
pytest-base-url=2.1.0
pytest-html=4.2.0
pytest-metadata=3.1.1
pytest-order=1.4.0
pytest-rerunfailures=16.3
pytest-result-log=1.2.2
pytest-selenium=4.1.0
pytest-variables=3.1.0
PyYAML=6.0.3
requests=2.34.2
selenium=4.44.0
sniffio=1.3.1
sortedcontainers=2.4.0
tenacity=9.1.4
trio=0.33.0
trio-websocket=0.12.2
typing_extensions=4.15.0
urllib3=2.7.0
websocket-client=1.9.0
wsproto=1.3.2
```

# API框架封装

## 分析测试步骤

1. 发送请求

2. 断言结果

3. 提取变量
  
## 设计框架结构

1. 目录关系

    - 源码
    - 测试用例
    - 日志
    - 报告
    - 依赖
    - 启动
    - 配置文件
  
2. 用例结构

    - 名字
    - 步骤（N个步骤）
    - 支持数据驱动


3. 实现框架封装

    - 实现各个步骤
    - 记录日志
    - 定制报告
    - 高级功能
  
          - 接口关联
          - 函数调用
      
