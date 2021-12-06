---
title: "Vscode Snippet"
date: 2021-12-06T20:40:32+08:00
lastmod: 2021-12-06T20:40:32+08:00
draft: false
keywords: []
description: ""
tags: []
categories: []
author: ""

# You can also close(false) or open(true) something for this content.
# P.S. comment can only be closed
autoCollapseToc: false
postMetaInFooter: false
hiddenFromHomePage: false
# You can also define another contentCopyright. e.g. contentCopyright: "This is another copyright."
contentCopyright: false
reward: false
mathjax: false
mathjaxEnableSingleDollar: false
mathjaxEnableAutoNumber: false

# You unlisted posts you might want not want the header or footer to show
hideHeaderAndFooter: false

# You can enable or disable out-of-date content warning for individual post.
# Comment this out to use the global config.
#enableOutdatedInfoWarning: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

<!--more-->





只需看完官方文档第一节 <https://code.visualstudio.com/docs/editor/userdefinedsnippets>，基本就能把 snippet 用起来了



## snippet 插件安装

在插件面板中搜索：`@category:"snippets"`，即可查找各种语言的 snippet 插件。

有语言服务器支持的插件一般都自带 snippet，如`ms-vscode.cpptools`, `golang.go`, `ms-python.python`，`redhat.java`等等，如果已安装此类插件，则无需再安装 snippet 了

设置项： `Ctrl + ,` 打开设置页面，点击右上角打开 json 设置文件

```json
{
    "snippet.verbose": true,
}
```



## 配置个人 snippet

在命令面板 `Ctrl+Shift+P` 中，输入 `snippet`，选择 `Preferences: Configure User Snippets`，再选择自己想要配置 snippet 的语言即可。

C++

```jsonc
{
  // Place your snippets for cpp here. Each snippet is defined under a snippet name and has a prefix, body and 
  // description. The prefix is what is used to trigger the snippet and the body will be expanded and inserted. Possible variables are:
  // $1, $2 for tab stops, $0 for the final cursor position, and ${1:label}, ${2:another} for placeholders. Placeholders with the 
  // same ids are connected.
  "using std common": {
    "prefix": "uns",
    "body": [
    "#include <${1:string}>",
    "#include <${2:vector}>",
    "",
    "using namespace std;",
    ""
    ],
    "description": "2 basic heads"
  },
  "unordered_map": {
    "prefix": "inm",
    "body": [
    "#include <${1:unordered_map}>",
    ""
    ],
    "description": ""
  },
  "unordered_set": {
    "prefix": "ins",
    "body": [
    "#include <${1:unordered_set}>",
    ""
    ],
    "description": ""
  },
  "container": {
    "prefix": "ini",
    "body": [
    "#include <${1:iostream}>",
    ""
    ],
    "description": ""
  },
}
```

Python

```jsonc
{
    "HEADER": {
        "prefix": "header",
        "body": [
            "#!/usr/bin/python3",
            "# -*- encoding: utf-8 -*-",
            "'''",
            "@File    :   $TM_FILENAME",
            "@Time    :   $CURRENT_YEAR/$CURRENT_MONTH/$CURRENT_DATE $CURRENT_HOUR:$CURRENT_MINUTE:$CURRENT_SECOND",
            "@Author  :   younger ",
            "@Version :   1.0",
            "@Contact :   7650421@qq.com",
            "@WebSite :   younger-1.github.io",
            "'''",
            "",
            "$0"
        ],
    },
    "Deque": {
        "prefix": "fci",
        "body": [
            "from collections import ${1:deque}",
            ""
        ]
    },
    "Numpy": {
        "prefix": "inn",
        "body": [
            "import numpy as np",
            "import matplotlib.pyplot as plt",
            ""
        ]
    },
}
```
