# PyJail

## 目录结构

```
pyjail/
├── README.md              # 本文档
├── 0/                     # Pyjail 0
│   ├── chall.py
│   ├── Dockerfile
│   ├── main.py
│   └── wrapper.sh
│   └── README.md         # 题目描述及平台提示
│
├── ...
│
└── jail-template/         # 题目模板
    ├── chall.py
    ├── Dockerfile
    ├── init.sh
    ├── Justfile
    ├── template.py
    └── wrapper.sh
```

## 题目部署方式

每个题目目录（0-6）都包含独立的 Docker 环境配置，部署方式如下：

进入对应题目目录，使用 Docker 构建并运行：

```bash
cd 0  # 以 Pyjail 0 为例
docker build -t pyjail-0 .
docker run -d -p 9000:9999 --name pyjail-0 pyjail-0
```

## 文件说明

- **chall.py**: 题目核心代码，包含沙箱限制和检查逻辑
- **main.py**: 题目入口文件
- **Dockerfile**: Docker 镜像构建配置
- **wrapper.sh**: 容器启动脚本

## 致谢

本题目中的 `jail-template` 目录并非我所写，来自 **XDSEC 22 届前辈鲤唐可可**，在此表示感谢！🙏