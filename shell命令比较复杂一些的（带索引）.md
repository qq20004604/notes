# 常见shell命令

## 01、判断目录是否存在，不存在则创建

当前目录不存在mysql-data文件夹则创建mysql-data

示例代码：

```bash
if [ ! -d "mysql-data" ]; then
  mkdir mysql-data
fi
```

## 02、shell 中获取文件真实路径（绝对路径）

获得绝对路径：

```bash
# 通过 readlink 获取绝对路径，再取出目录
work_path=$(dirname $(readlink -f $0))
```

拼接路径：

```bash
work_path="$work_path/mysql-data"
```

注意，如果拼接时候出现问题，那么可能是你在windows下创建的shell脚本，然后在linux下执行。

vi命令编辑脚本，然后输入 ``$set ff=unix`` 来修改编码；