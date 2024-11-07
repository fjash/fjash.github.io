# 开始 Record
> 功能测试 

[toc]
1. admonition
> https://squidfunk.github.io/mkdocs-material/reference/admonitions/
!!! info "测试"
    - hhh
    - www
    - xxx
2. 可折叠的代码块

???+ summary "课程介绍"
    这是一个课程介绍的示例。在这里，你可以写一些关于课程的详细信息。

    - 课程名称：Python编程基础
    - 课程时长：10周
    - 课程内容：
        - Python语法
        - 数据结构
        - 函数与模块
        - 文件操作
        - 异常处理
        - 面向对象编程

    希望你能喜欢这个课程！
> ???+ 代表一个展开的折叠快, ???- 代表一个折叠的折叠快
3. 内嵌代码 and 代码高亮
```c++
    #include<>
    int main()
    {
        return 0;
    }
```

4. 标记文本 ?? 
   ==嘿嘿==

5. 外部代码？ 
    {{ "Leetcode_1.md" }}

6. 删除线
   ~~删除~~
7. latex 渲染
!!!  note "Latex 测试"
    Here is an inline math formula: $E=mc^2$
    And here is a block math formula:
    $$
    \int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}
    $$
8. 生成目录 

9.  选项卡式的内容展示
!!! info ""
    === "选项一"
       内容一

    === "选项二"
       内容二

    === "选项三"
       内容三
10.  图片
  ![](1.png)

11.   emoji 
    :smile:

12.   创建带有复选框的内容展示
    - [x] 把博客大致内容做好
    - [ ] 弄一些模板，快速开始

[^2]: 这个是脚注二
13. 强调效果
    *h*
    **hh**
    ***hhh***
14. 缩写提示:
    *[HTML]: HyperText Markup Language
    *[CSS]: Cascading Style Sheets
    *[JS]: JavaScript

![测试](2.png)
[^1]: 这个是脚注一