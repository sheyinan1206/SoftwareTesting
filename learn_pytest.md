# pytest基础
1. 环境准备
2. 安装pytest 

    ```pip install pytest```
   
3. 创建用例
    - 文件：test_开头
    - 函数：test_开头
    - 内容：拥有断言
    - 返回值：必须是none
  
4. 执行用例
    - pytest命令（推荐）
    - pytest启动函数（main）
    - IDE按钮（随着编辑器不同结果也不同--不推荐）
      
5. 执行结果
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

6. 用例发现规则
    - 遍历所有目录**（venv和.开头的除外）**
  
      venv是Python虚拟环境，本身就有很多测试用例，.开头是隐藏文件
    - 
