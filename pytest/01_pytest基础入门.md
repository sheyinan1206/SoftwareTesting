# pytest基础入门
## 环境准备
## 安装pytest 
```
pip install pytest
```
   
## 创建用例
    - 文件：test_开头
    - 函数：test_开头
    - 内容：拥有断言
    - 返回值：必须是none
  
## 执行用例
    - pytest命令（推荐）
    - pytest启动函数（main）
    - IDE按钮（随着编辑器不同结果也不同--不推荐）
      
## 执行结果
    - 执行环境
    - 用例的收集情况
    - 用例的执行情况
      |||
      | :--- | :--- |
      |成功|passed|
      ||.|
      |失败|failed|
      ||F|
      |跳过|skipped|
      ||s|
      |出错|error|
      ||E|
      |预期失败|X:预期外成功|
      ||x:预期内的失败|
    - 用例失败的详情
    - 测试活动的结果摘要

```
import pytest

def test_web():
    assert 1 == 1
    return None

def test_api():
    assert 1 == 2

def test__pass():
    assert 1 == 1

def test__fail():
    assert 1 == 2

@pytest.fixture()
def f():
    assert 1==2

def test_error(f):
    assert 1 == 3

@pytest.mark.skip
def test_skip():
    assert 1==2

@pytest.mark.xfail
def test_xpass():
    pass

@pytest.mark.xfail
def test_xfail():
    assert 1==2
```

## 用例发现规则
1. 遍历所有目录

    venv和.开头的除外 venv是Python虚拟环境，本身就有很多测试用例，.开头是隐藏文件
   
2. 遍历所有py文件 **（test_开头 或者 _test 结尾）**
3. 遍历所有Test开头的类 **（不得拥有__init__方法）**
4. 收集复用要求的**函数，方法** **（test_开头，没有参数，没有返回值）**
