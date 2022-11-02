# Home Assistant 自定义集成下载脚本

<a name="shell_command"></a>
## 通过HA服务安装/更新插件

1. 复制下面的代码到HA配置文件`configuration.yaml`
    ```yaml
    shell_command:

      # 更新HACS极速版
      update_hacs_china: |-
        wget -O - https://hacs.vip/get | HUB_DOMAIN=ghproxy.com/github.com DOMAIN=hacs REPO_PATH=hacs-china/integration ARCHIVE_TAG=latest bash -

      # 更新Xiaomi Miot Auto
      update_xiaomi_miot: |-
        wget -O - https://hacs.vip/get | HUB_DOMAIN=ghproxy.com/github.com DOMAIN=xiaomi_miot REPO_PATH=al-one/hass-xiaomi-miot ARCHIVE_TAG=latest bash -

      # 更新XiaomiGateway3
      update_xiaomi_gateway3: |-
        wget -O - https://hacs.vip/get | HUB_DOMAIN=ghproxy.com/github.com DOMAIN=xiaomi_gateway3 REPO_PATH=AlexxIT/XiaomiGateway3 ARCHIVE_TAG=master bash -

      # 更新文件管理器
      update_file_explorer: |-
        wget -O - https://hacs.vip/get | HUB_DOMAIN=ghproxy.com/github.com DOMAIN=ha_file_explorer REPO_PATH=shaonianzhentan/ha_file_explorer ARCHIVE_TAG=master bash -

      # 更新Edge TTS
      update_edge_tts: |-
        wget -O - https://hacs.vip/get | HUB_DOMAIN=ghproxy.com/github.com DOMAIN=edge_tts REPO_PATH=hasscc/hass-edge-tts ARCHIVE_TAG=main bash -
    ```
2. 重启HA
3. 在HA开发者工具中调用服务
   - [`service: shell_command.update_hacs_china`](https://my.home-assistant.io/redirect/developer_call_service/?service=shell_command.update_hacs_china)
   - [`service: shell_command.update_xiaomi_miot`](https://my.home-assistant.io/redirect/developer_call_service/?service=shell_command.update_xiaomi_miot)
   - [`service: shell_command.update_xiaomi_gateway3`](https://my.home-assistant.io/redirect/developer_call_service/?service=shell_command.update_xiaomi_gateway3)
   - [`service: shell_command.update_file_explorer`](https://my.home-assistant.io/redirect/developer_call_service/?service=shell_command.update_file_explorer)
   - [`service: shell_command.update_edge_tts`](https://my.home-assistant.io/redirect/developer_call_service/?service=shell_command.update_edge_tts)

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
wget -O - https://ghproxy.com/raw.githubusercontent.com/hasscc/get/main/get | HUB_DOMAIN=ghproxy.com/github.com DOMAIN=hacs REPO_PATH=hacs-china/integration ARCHIVE_TAG=china bash -
wget -O - https://raw.githubusercontents.com/hasscc/get/main/get | HUB_DOMAIN=hub.fastgit.xyz DOMAIN=hacs REPO_PATH=hacs-china/integration bash -
```

## 选项说明

```yaml
DOMAIN:      自定义插件域，下载后在`custom_components`目录下的文件夹名
REPO_PATH:   插件的Github仓库路径
ARCHIVE_TAG: 插件的版本/分支，默认为`master`，部分插件支持`latest`
HUB_DOMAIN:  指定Github镜像
```
