# Home Assistant 自定义集成下载脚本

## 指定集成

```bash
wget -O - https://raw.githubusercontent.com/hasscc/get/main/get | DOMAIN=hacs REPO_PATH=hacs-china/integration ARCHIVE_TAG=china bash -
wget -O - https://raw.githubusercontents.com/hasscc/get/main/get | DOMAIN=hacs REPO_PATH=hacs-china/integration ARCHIVE_TAG=china bash -
wget -O - https://ghproxy.com/raw.githubusercontent.com/hasscc/get/main/get | DOMAIN=hacs REPO_PATH=hacs-china/integration ARCHIVE_TAG=china bash -
```

## 指定版本

```bash
wget -O - https://raw.githubusercontents.com/hasscc/get/main/get | DOMAIN=hacs REPO_PATH=hacs-china/integration ARCHIVE_TAG=v1.0.0 bash -
wget -O - https://raw.githubusercontents.com/hasscc/get/main/get | DOMAIN=xiaomi_miot REPO_PATH=al-one/hass-xiaomi-miot ARCHIVE_TAG=master bash -
```

## 指定镜像

```bash
wget -O - https://ghproxy.com/raw.githubusercontent.com/hasscc/get/main/get | HUB_DOMAIN=ghproxy.com/github.com DOMAIN=hacs REPO_PATH=hacs-china/integration bash -
wget -O - https://raw.githubusercontents.com/hasscc/get/main/get | HUB_DOMAIN=hub.fastgit.xyz DOMAIN=hacs REPO_PATH=hacs-china/integration bash -
```

## 选项说明

```yaml
DOMAIN:      自定义插件域，下载后在`custom_components`目录下的文件夹名
REPO_PATH:   插件的Github仓库路径
ARCHIVE_TAG: 插件的版本/分支，默认为`master`
HUB_DOMAIN:  指定Github镜像
```
