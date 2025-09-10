# aptss

`aptss` is a part of [Spark APP Store](https://gitee.com/spark-store-project/spark-store). aptss is used to provide GXDE package manage ability.

This package is provided in case some user don't wan't to use Spark APP Store but still need download accelerate. 

You can customize your apt-fast conf at /etc/aptss/apt-fast.conf

```bash

# 定义默认的配置文件列表（按加载顺序排列）
CONFIG_FILES=(
    "/tmp/aptss-conf/apt-fast.conf"  # 原始配置文件位置
    "/etc/aptss/apt-fast.conf"             # 系统级配置
)


# 按顺序加载所有配置文件
for conf_file in "${CONFIG_FILES[@]}"; do
    if [ -e "$conf_file" ]; then
        source "$conf_file"
    fi
done


```

配置文件内容请参考 `/tmp/aptss-conf/apt-fast.conf`
