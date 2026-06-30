## 1.测试框架
### 测试框架是什么
根据大量的测试时间，抽象出来的一个常用工具集合，包含大量组件或功能，以及经过验证的方法论

### 常用工具和组件
- 用例发现：自动从各目录、各文件中收集测试用例
- 用例管理：根据需求对用例进行筛选、忽略、跳过等操作
- 环境管理：用例执行前后，自动完成某些擦着，构造合适的执行条件按
- 用例执行：执行用例中的测试步骤
- 断言：执行用例时，判定执行结果是否符合预期

### 经过验证的方法论：
- 用例之间相互隔离
- 使用**断言**宣告结果
- 为每个用例单独收集IO和日志
- 数据驱动测试、行为驱动测试、关键字驱动测试 等
- 冒烟测试、步进测试、回归测试、增量测试 等

## 2.pytest基本用法
### 用例规则
1. 目录、文件和类

跟目录没关系，文件名是test_开头或_test结尾，类名是Test

类不属于测试用例，是容器

函数和方法才是用例，因为有返回值

2. 函数（方法）名

方法是定义在类中的函数

3. 参数和返回值

无参数（方法里的）和返回值

> python文件中，函数（方法）才是用例！！！

### 断言方式
python内置关键字：assert

```python
def test_web():
    a = 'abc'
    b = 'bbc'
    assert a == b
```

## 3.pytest进阶技巧
### 标记：mark

让用例与众不同

1. 自定义标记


2. 内置标记

- skip
- xfail
- **parametrize**

    参数化测试
    > 数据驱动测试：根据数据的数量和内容，决定用例的数量和内容
    
```python
import pytest
import requests

def add(a, b):
    return a + b

@pytest.mark.parametrize("a, b", [(1, 2), (3, 4), ("a", "b"), (["a"], [4])],)
def test_add(a, b):
    c = a + b
    assert c == a + b


@pytest.mark.parametrize(
        ["accounts", "pwd", "code"], 
        [["admin", "123456", "200"], 
         ["admin", "123456789", "0"],
         ["admin", "", "1"]]
                         )
def test_login(accounts, pwd, code):
    s = requests.Session()
    method = 'post'
    url = 'http://shop-xo.hctestedu.com/index.php?s=/index/user/logininfo.html'
    json = {
        'accounts': accounts,
        'pwd': pwd
    }
    resp = s.request(method,url,json=json)
    assert resp.status_code == int(code)
```
> 如何创作高质量的数据：AI！！！！！

- usefixtures

### 夹具：fixture

如何使用：

1. 通过标记调用
```@pytest.mark.usefixtures('f')```

2. 通过参数调用


作用：

1. 实现setup/teardown机制
2. 实现注入机制

作用域：

- 在同一作用域内的用例，复用注入结果

conftest：

- 跨文件共享fixture

    
    
