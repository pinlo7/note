# Home Assistant 米家集成 在 fnNas中的docker部署

米家集成是一个由小米官方提供支持的 Home Assistant 的集成组件，它可以让您在 Home Assistant 中使用小米 IoT 智能设备。

## 安装

> Home Assistant 版本要求：
>
> - Core $\geq$ 2024.4.4
> - Operating System $\geq$ 13.0
> - 目前fnNas应用商店已经有了Home Assistant的docker版本应用,自行下载安装
> - 安装之后需要在自己的电脑使用ssh连接nas, 需要打开ssh访问（fnnas->设置->SSH）
> - 在自己的电脑上打开 终端(开始->cmd)
> - 连接fnNas     ssh username@192.168.1.300    (用户名和ip地址换成自己的) (注意输入密码时不会有任何反馈显示!)
> - 登录完成后. 输入sudo -i提示权限(不然无法进入docker容器内部环境)
```
sudo -i
```
> - 然后我们需要进入容器内部执行安装命令
```
docker exec -it homeassistant bash
```
成功状态
![image](https://github.com/user-attachments/assets/7e02b2c9-65ca-494b-b41f-cd0829ed1a36)
然后输入命令拉取仓库
```
git clone https://github.com/XiaoMi/ha_xiaomi_home.git
```
如果没有git命令自己安装哈

> - 完了就根据官方文档的方法一执行就可以正确安装了

### 方法 1：使用 git clone 命令从 GitHub 下载

```bash
cd config
git clone https://github.com/XiaoMi/ha_xiaomi_home.git
cd ha_xiaomi_home
./install.sh /config
```

推荐使用此方法安装米家集成。当您想要更新至特定版本时，只需要切换至相应的 Tag 。

例如，更新米家集成版本至 v1.0.0

```bash
cd config/ha_xiaomi_home
git fetch
git checkout v1.0.0
./install.sh /config
```
# 应该是最方便的方式了

