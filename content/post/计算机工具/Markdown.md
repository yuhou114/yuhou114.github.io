---
title: "Markdown"
description: ""
date: 2026-05-16T09:20:55+08:00
lastmod: 2026-05-16T09:20:55+08:00
categories:
    - 计算机工具
tags:
    - Markdown
draft: false
---


## 1. **工具准备**

使用 Markdown 目前主流的工具有：

Visual Studio Code：微软开发的免费编辑器。
VScode 支持 Markdown 的扩展包括：
- Markdown All in One：提供快捷键、目录生成、数学公式支持。
- Markdown Preview Enhanced：增强的预览功能，支持图表和演示模式。
- markdownlint：语法检查和格式规范。

Obsidian ：本地 Markdown 笔记系统，用文件夹和纯文本驱动知识结构，
使用教程参考： https://www.runoob.com/markdown/obsidian-tutorial.html。

typora : Typora 是目前公认体验最好的桌面端 Markdown 编辑器。
下载地址： https://typoraio.cn/releases/stable.html


## 2. **标题**
   
 - 使用 # 号标记

     使用 # 号可表示 1-6 级标题，一级标题对应一个 # 号，二级标题对应两个 # 号，以此类推。

     > #一级标题  
     > ##二级标题  
     > ###三级标题  
     > ####四级标题  
     > #####五级标题  
     > ######六级标题  

     > # 一级标题  
     > ## 二级标题  
     > ### 三级标题  
     > #### 四级标题  
     > ##### 五级标题  
     > ###### 六级标题

##  3. **引用**  

 - 在段落前使用 > 符号进行引用
  
     > 例如这样

 - 也可以在多个段落前连续使用 >
     > 像是  
     > 这样  
     > 。

 - 还可以使用 >> 进行嵌套
     > 像是
     >> 这样

## 4. **列表**  

  1. **无序列表**  

      - 无序列表使用星号(*)、加号(+)或是减号(-)作为列表标记，这些标记后面要添加一个空格，然后再填写内容。  
          > - 例如这样

  2. **有序列表**

      - 有序列表使用数字并加上 . 号来表示。

          > 1. 例如这样

      - 数字可以不连续 Markdown 会自动修正数字顺序：

          > 1. 第一项
          > 3. 第二项（实际显示为2）
          > 7. 第三项（实际显示为3）  

          ![实际图片](https://yuhou-hugo.oss-cn-beijing.aliyuncs.com/%E6%96%87%E7%AB%A0%E5%9B%BE%E7%89%87/Markdown/markdown-1.png)

  3. **嵌套**
      - 列表可以嵌套使用，创建多层次的结构。  
      - 列表混合嵌套只需在子列表中的选项前面添加两个或四个空格即可。

          > 1. 主要任务
          >    - 子任务A
          >    -  子任务B
          >        1. 详细步骤1
          >        2. 详细步骤2
          >    - 子任务C
          > 2. 次要任务
  
  4. **任务列表（复选框列表）**
      - 任务列表是 GitHub 风格 Markdown 的扩展功能，现在被广泛支持。

          > - [ ] 未完成的任务
          > - [x] 已完成的任务
          > - [ ] 另一个未完成的任务

## 5. **表格**

 1. Markdown 制作**表格使用** | 来分隔不同的单元格，使用 - 来分隔表头和其他行。
     > |  表头   | 表头  |
     |  ----  | ----  |
     | 单元格  | 单元格 |
     | 单元格  | 单元格 |
 - 效果如下
     > |  表头   | 表头  |
     > |  ----  | ----  |
     > | 单元格  | 单元格 |
     > | 单元格  | 单元格 |
 
 2. 我们可以设置表格的**对齐方式**：
 ---: 设置内容和标题栏居右对齐。
 :--- 设置内容和标题栏居左对齐。
 :---: 设置内容和标题栏居中对齐。

     > | 左对齐 | 右对齐 | 居中对齐 |
     | :-----| ----: | :----: |
     | 单 | 元 | 格 |

 - 效果如下
     > | 左对齐 | 右对齐 | 居中对齐 |
     > | :-----| ----: | :----: |
     > | 单 | 元 | 格 |

## 6. **段落**
   
 1. **换行**
 - 段落的换行是使用两个以上空格加上回车。  
      ![实际图片](https://yuhou-hugo.oss-cn-beijing.aliyuncs.com/%E6%96%87%E7%AB%A0%E5%9B%BE%E7%89%87/Markdown/markdown-2.png) 

 2. **分割线**
 - 你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他
 东西。你也可以在星号或是减号中间插入空格。

      >   1.*** 
          2.* * *
          3.*****
          4.- - -
          5.----------
  
 - 效果如下
  ***

 3. **字体**
 - 使用以下符号包含文本可以实现对应的效果

      | 字体       | 代码         |
      | :--------: | :----------: |
      | *斜体*     | `* *`        |
      | ==高亮==   | `== ==`      |
      | **粗体**   | `** **`      |
      | ***斜粗体*** | `*** ***`    |
      | ~~删除~~   | `~~ ~~`       |
      | <u>下划线</u> | `<u> </u>`   |

 4. **脚注**
 - 在文本后面加上[^数字]来标注
      > 你冲q币吗[^1]

## 7. **代码**

 1. **代码行**
 - 如果是段落上的一个函数或片段的代码可以用反引号把它包起来（`） 
    
      `printf()` 函数

 2. **代码块**
 - 用 ``` 包裹一段代码，并指定一种语言（也可以不指定）
  
      ```javascript
      $(document).ready(function () {
      alert('RUNOOB');
      });
      ```

      ![具体图片](https://yuhou-hugo.oss-cn-beijing.aliyuncs.com/%E6%96%87%E7%AB%A0%E5%9B%BE%E7%89%87/Markdown/markdown-3.png)
    
## 8. **超链接**

 - 链接使用方法如下
      ![具体图片](https://yuhou-hugo.oss-cn-beijing.aliyuncs.com/%E6%96%87%E7%AB%A0%E5%9B%BE%E7%89%87/Markdown/markdown-4.png)

      > [链接名称](https://www.runoob.com/markdown/md-tutorial.html)
      > [链接文字](https://www.runoob.com/markdown/md-tutorial.html "可选的标题")
   
## 9.  **图片**

 - Markdown 图片语法格式如下
      ![具体图片](https://yuhou-hugo.oss-cn-beijing.aliyuncs.com/%E6%96%87%E7%AB%A0%E5%9B%BE%E7%89%87/Markdown/markdown-5.png)

      > ![替代文字](图片路径)
      > ![替代文字](图片路径 "图片标题")

## 10. **Github风格的Alert块引用（需要Hugo v0.132.0或更高版本）**

共有 NOTE，TIP，IMPORTANT，WARNING，CAUTION 五种

```Markdown
> [!NOTE]
> Useful information that users should know, even when skimming content.
```
> [!NOTE]
> Useful information that users should know, even when skimming content.

```Markdown
> [!TIP]
> Helpful advice for doing things better or more easily.
```

> [!TIP]
> Helpful advice for doing things better or more easily.

```Markdown
> [!IMPORTANT]
> Key information users need to know to achieve their goal.
```

> [!IMPORTANT]
> Key information users need to know to achieve their goal.

```Markdown
> [!WARNING]
> Urgent info that needs immediate user attention to avoid problems.
```

> [!WARNING]
> Urgent info that needs immediate user attention to avoid problems.

```Markdown
> [!CAUTION]
> Advises about risks or negative outcomes of certain actions.
```

> [!CAUTION]
> Advises about risks or negative outcomes of certain actions.


{{< gallery >}}
![image](https://picsum.photos/800/600)
![image](https://picsum.photos/600/800)
![image](https://picsum.photos/700/500)
![image](https://picsum.photos/900/600)
![image](https://picsum.photos/500/700)
![image](https://picsum.photos/800/500)
![image](https://picsum.photos/650/850)
![image](https://picsum.photos/750/550)
{{< /gallery >}} 

## 11.  **其他操作**
  - html/css语法
      - Ctrl+Shift+p 搜索 "Markdown Preview Enhanced:Customize CSS"
      style中使用css语法改标题格式等等

  - 个性化设置
      - File-Preferences-Settings 
  
## 12. **图表绘制**

  - 具体可查询[菜鸟教程](https://www.runoob.com/markdown/md-draw.html)


 

[^1]: qq出品的一种虚拟货币

    
