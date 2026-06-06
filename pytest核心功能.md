## 功能

1. 前\后置操作

2. 内容注入

## 创建fixture

1. 创建函数

2. 添加装饰器 @pytest.fixture

3. 添加关键字 yield

## 使用fixture

1. 通过用例进行使用

2. 通过标记或者参数【请求】fixture

3. 不允许直接【调用】fixture

## 共享范围

1. function （默认、最小、不共享）

2. class

3. module

4. package

5. session （最大、全局共享）

6. conftest

    面向对象特性

- 用例寻找，只会向上寻找

- 优先使用距离近的

- 下级目录、用例文件、用例类实现fixture注入

    跨文件的共享

  ## 内容注入

  1. yield进行返回（内容，类，方法）
 
  2. 每个用例只能注入一次
