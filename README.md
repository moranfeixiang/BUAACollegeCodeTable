
---

## 项目简介

本项目使用 **XeLaTeX** 用于整理和生成

- 北京航空航天大学系号—学院/书院对照表；
- 北京航空航天大学杭州国际创新研究院平台缩写参考表；
- 北航老乡群的加入方式。

表格采用 LaTeX 制作，支持高清 PDF 输出以及 PNG 图片导出。

---

## 文件说明

### LaTeX 源文件

| 文件 | 说明 |
|---|---|
| `BUAA_CollegeCode.tex` | 北航系号—学院/书院对照表 LaTeX 源文件 |
| `BUAA_Hangzhou.tex` | 杭州国新院平台缩写参考表 LaTeX 源文件 |
| `BUAA_Laoxiang.tex` | 北航老乡群的QQ群信息表 LaTeX 源文件 |

---

### 目录说明

```
BUAATable
│
├── *.tex             LaTeX 源文件
├── pdf/              复制来的编译生成的 PDF 文件
├── image/            导出的 PNG 图片及图片资源
├── build/            LaTeX 编译临时文件和 pdf
├── .vscode/
│   └── settings.json  VSCode LaTeX Workshop 配置
└── README.md
```

---

## 编译环境

推荐环境：

- 操作系统：Windows 10 / Windows 11
- LaTeX 发行版：MiKTeX
- 编译引擎：XeLaTeX
- 编辑器：Visual Studio Code
- LaTeX 插件：LaTeX Workshop
- 构建工具：latexmk

---

## 字体依赖

项目使用以下字体：

- Times New Roman
- FangSong_GB2312
- FZXiaoBiaoSong-B05S

请提前安装对应字体，否则标题及正文显示效果可能存在差异。

字体资源可以通过网络搜索或使用下方参考：

https://github.com/DoveOutland/Common-Chinese-office-fonts-font-library-


---

## 编译方法

在 VSCode 安装 LaTeX Workshop 后：

1. 使用 VS Code 打开项目；
2. 打开 `.tex` 文件；
3. 执行：

```
Ctrl + Alt + B
```

默认调用 latexmk-xelatex 生成 PDF 文件。

---

## PDF 导出 PNG

项目使用 MiKTeX 自带的 `pdftoppm` 工具进行 PDF 转图片：

```bash
pdftoppm -png -singlefile -r 300 ./build/BUAA_Laoxiang.pdf ./image/BUAA_Laoxiang
```

参数说明：

| 参数 | 作用 |
|---|---|
| `-png` | 输出 PNG 格式 |
| `-singlefile` | 单页输出，不添加页码 |
| `-r 300` | 输出分辨率 300 DPI |

