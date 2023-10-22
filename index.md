# 第一次组会内容

***通过现成的爬取+可视化分析+GPT文档解析工具，协助你快速了解一个陌生的研究领域 :]***

## 一、WOS_Spider 爬取工具介绍



<aside>
代码仓库 [https://github.com/lijinhai0804/WOS-spider-automatically-export-document-information-in-batches/invitations](https://github.com/lijinhai0804/WOS-spider-automatically-export-document-information-in-batches/invitations)

</aside>


---

## 二、 BiblioShiny 文献计量工具介绍


- 下载RStudio
1. Install R

> [https://cran.rstudio.com/bin/windows/base/R-4.3.1-win.exe](https://cran.rstudio.com/bin/windows/base/R-4.3.1-win.exe)
> 
2. Install RStudio

> [https://download1.rstudio.org/electron/windows/RStudio-2023.09.1-494.exe](https://download1.rstudio.org/electron/windows/RStudio-2023.09.1-494.exe)
> 

- BibiloShiny package install

```sh 
install.packages("bibliometrix", dependencies=TRUE) ### installs bibliometrix package and dependencies
library(bibliometrix)   ### load bibliometrix package
biblioshiny()
```

- web界面操作
1. 选择Raw File
2. 选择相应数据库（WOS/Scopus）
3. 添加档案

---

## 三、本地部署GPT_AC

视频教程（基于Anaconda）：[https://www.bilibili.com/video/BV1rc411W7Dr/?vd_source=99b15d72536a5b3886aae6b69375f5ec](https://www.bilibili.com/video/BV1rc411W7Dr/?vd_source=99b15d72536a5b3886aae6b69375f5ec)
- GPT_AC简介与优缺点
1. 优点：可以本地部署、客制化API、精美的web界面、免费的强大插件、接入各大模型
2. 缺点：部署版本要求较高、无法提供进阶文档分析


[gpt_academic](https://github.com/binary-husky/gpt_academic)：
ChatGPT/GLM提供实用化交互界面，特别优化论文阅读/润色/写作体验，模块化设计，支持自定义快捷按钮&函数插件，支持Python和C++等项目剖析&自译解功能，PDF/LaTex论文翻译&总结功能，支持并行问询多种LLM模型，支持chatglm2等本地模型。兼容文心一言, moss, llama2, rwkv, claude2, 通义千问, 书生, 讯飞星火等。



 - 本地部署过程

1. 下载项目
```sh
git clone --depth=1 https://github.com/binary-husky/gpt_academic.git
cd gpt_academic
```

2. 配置API_KEY

在`config.py`中，配置API KEY等设置，[点击查看特殊网络环境设置方法](https://github.com/binary-husky/gpt_academic/issues/1) 与[Wiki页面](https://github.com/binary-husky/gpt_academic/wiki/%E9%A1%B9%E7%9B%AE%E9%85%8D%E7%BD%AE%E8%AF%B4%E6%98%8E)。

「 程序会优先检查是否存在名为`config_private.py`的私密配置文件，并用其中的配置覆盖`config.py`的同名配置。如您能理解该读取逻辑，我们强烈建议您在`config.py`旁边创建一个名为`config_private.py`的新配置文件，并把`config.py`中的配置转移（复制）到`config_private.py`中（仅复制您修改过的配置条目即可）。 」

「 支持通过`环境变量`配置项目，环境变量的书写格式参考`docker-compose.yml`文件或者我们的[Wiki页面](https://github.com/binary-husky/gpt_academic/wiki/%E9%A1%B9%E7%9B%AE%E9%85%8D%E7%BD%AE%E8%AF%B4%E6%98%8E)。配置读取优先级: `环境变量` > `config_private.py` > `config.py`。 」

3. 安装依赖

- 3.1 选择I: 如熟悉python（python版本3.9以上，越新越好），备注：使用官方pip源或者阿里pip源,临时换源方法：python -m pip install -r requirements.txt -i https://mirrors.aliyun.com/pypi/simple/
python -m pip install -r requirements.txt

- 3.2 选择II: 使用Anaconda 步骤也是类似的 (https://www.bilibili.com/video/BV1rc411W7Dr)：

```
conda create -n gptac_venv python=3.11    # 创建anaconda环境
conda activate gptac_venv                 # 激活anaconda环境
python -m pip install -r requirements.txt # 这个步骤和pip安装一样的步骤
```



- 创建一个Python虚拟环境

1. windows CMD terminal

查看本机python版本（建议3.11版本）

```sh 
python --version
```

***下载最新3.11Python版本***

[https://www.python.org/ftp/python/3.11.0/python-3.11.0-amd64.exe](https://www.python.org/ftp/python/3.11.0/python-3.11.0-amd64.exe)


2. 创建Python虚拟环境

```sh
python -m venv <name>
```

3. 启动虚拟环境

```sh
python activate.bat
``` 

4. 退出虚拟环境

```sh
deactivate
```

- 在环境中安装pip库

```sh
python -m pip install -r requirements.txt
```

***如果延迟过高 尝试换源***

```sh 
python -m pip install --upgrade pip
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```

- 运行

```sh
python main.py
```






WiKi页面：[项目配置说明 · binary-husky/gpt_academic Wiki · GitHub](https://github.com/binary-husky/gpt_academic/wiki/%E9%A1%B9%E7%9B%AE%E9%85%8D%E7%BD%AE%E8%AF%B4%E6%98%8E)
