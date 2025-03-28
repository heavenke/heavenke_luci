# 个人收藏的OpenWrt插件包

## 注意: 这些插件非本人原创, 系从网络收集而来, 个别插件可能作了一些改动以适配本人的设备.

## 使用方法

### 增加feed源

```shell
echo >> feeds.conf.default
echo 'src-git heavenke_packages https://github.com/heavenke/heavenke_packages.git;main' >> feeds.conf.default
echo 'src-git heavenke_luci https://github.com/heavenke/heavenke_luci.git;main' >> feeds.conf.default
./scripts/feeds update heavenke_packages heavenke_luci
./scripts/feeds install -a -p heavenke_packages
./scripts/feeds install -a -p heavenke_luci
```

### 集成软件包

```shell
make menuconfig
```

选择软件包
```plain
LuCI --->
3. Applications --->
<*> luci-app-msd_lite.................................. LuCI support for Multi stream daemon lite
<*> luci-app-socat.................................. LuCI support for Socat
<*> luci-app-systools.................................. LuCI support for SysTools
<*> luci-app-taskplan.................................. LuCI support for Task Plan setting
```

### 构建固件

多线程
```shell
make V=s -j$(nproc)
```

单线程
```shell
make V=sc -j1
```