# heavenke_luci
luci for [heavenke_luci](https://github.com/heavenke/heavenke_luci)

## 使用方法

### 增加feed源

```shell
echo >> feeds.conf.default
echo 'src-git heavenke_luci https://github.com/heavenke/heavenke_luci.git;main' >> feeds.conf.default
./scripts/feeds update heavenke_luci
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
<*> luci-app-ddnsto.................................. LuCI support for ddnsto
<*> luci-app-linkease.................................. LuCI support for linkease
```

### 构建固件
```shell
make
```