# Home Assistant 自定义集成下载脚本

<a name="shell_command"></a>
## 通过HA服务安装/更新插件

1. 复制下面的代码到HA配置文件`configuration.yaml`
    ```yaml
    shell_command:

      # HACS极速版
      update_hacs_china: |-
        wget -O - https://get.hacs.vip | bash -

      # Xiaomi Miot Auto
      update_xiaomi_miot: |-
        wget -O - https://get.hacs.vip | DOMAIN=xiaomi_miot bash -
      update_xiaomi_miot_beta: |-
        wget -O - https://get.hacs.vip | DOMAIN=xiaomi_miot ARCHIVE_TAG=master bash -

      # Xiaomi Home
      update_xiaomi_home: |-
        wget -O - https://get.hacs.vip | DOMAIN=xiaomi_home bash -

      # XiaomiGateway3
      update_xiaomi_gateway3: |-
        wget -O - https://get.hacs.vip | DOMAIN=xiaomi_gateway3 bash -

      # 文件管理器
      update_file_explorer: |-
        wget -O - https://get.hacs.vip | DOMAIN=ha_file_explorer bash -

      # 天气插件
      update_tianqi: |-
        wget -O - https://get.hacs.vip | DOMAIN=tianqi bash -

      # Edge TTS
      update_edge_tts: |-
        wget -O - https://get.hacs.vip | DOMAIN=edge_tts bash -

      # 国家电网
      update_state_grid: |-
        wget -O - https://get.hacs.vip | DOMAIN=state_grid bash -
    ```
2. 重启HA
3. 在HA开发者工具中调用服务
   - [`service: shell_command.update_hacs_china`](https://my.home-assistant.io/redirect/developer_call_service/?service=shell_command.update_hacs_china)
   - [`service: shell_command.update_xiaomi_miot`](https://my.home-assistant.io/redirect/developer_call_service/?service=shell_command.update_xiaomi_miot)
   - [`service: shell_command.update_xiaomi_gateway3`](https://my.home-assistant.io/redirect/developer_call_service/?service=shell_command.update_xiaomi_gateway3)
   - [`service: shell_command.update_file_explorer`](https://my.home-assistant.io/redirect/developer_call_service/?service=shell_command.update_file_explorer)
   - [`service: shell_command.update_tianqi`](https://my.home-assistant.io/redirect/developer_call_service/?service=shell_command.update_tianqi)
   - [`service: shell_command.update_edge_tts`](https://my.home-assistant.io/redirect/developer_call_service/?service=shell_command.update_edge_tts)
   - [`service: shell_command.update_state_grid`](https://my.home-assistant.io/redirect/developer_call_service/?service=shell_command.update_state_grid)

## 指定集成

```bash
wget -O - https://hacs.vip/get | DOMAIN=hacs REPO_PATH=hacs-china/integration ARCHIVE_TAG=china bash -
wget -O - https://hacs.vip/get | DOMAIN=xiaomi_miot REPO_PATH=al-one/hass-xiaomi-miot ARCHIVE_TAG=latest bash -
```

## 指定版本

```bash
wget -O - https://hacs.vip/get | DOMAIN=hacs REPO_PATH=hacs-china/integration ARCHIVE_TAG=v1.0.0 bash -
wget -O - https://hacs.vip/get | DOMAIN=xiaomi_miot REPO_PATH=al-one/hass-xiaomi-miot ARCHIVE_TAG=master bash -
```

## 指定镜像

```bash
wget -O - https://hacs.vip/get | HUB_DOMAIN=ghps.cc/github.com DOMAIN=hacs REPO_PATH=hacs-china/integration ARCHIVE_TAG=china bash -
wget -O - https://hacs.vip/get | HUB_DOMAIN=hub.fastgit.xyz DOMAIN=hacs REPO_PATH=hacs-china/integration bash -
```

## 选项说明

```yaml
DOMAIN:      自定义插件域，下载后在`custom_components`目录下的文件夹名
REPO_PATH:   插件的Github仓库路径
ARCHIVE_TAG: 插件的版本/分支，默认为`master`，部分插件支持`latest`
HUB_DOMAIN:  指定Github镜像
```
