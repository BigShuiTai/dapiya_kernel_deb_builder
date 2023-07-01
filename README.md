# kernel_deb_builder
利用 GitHub Actions 自动编译 Linux 内核为 deb 包。

本仓库仅供Dapiya Server编译最新版本的内核源代码及学习使用，禁止其他用途。

源仓库：[https://github.com/debuggerx01/kernel_deb_builder](https://github.com/debuggerx01/kernel_deb_builder)。

# 如何使用
如果您想要利用我的这个自动化脚本根据自己的需求编译内核，请参考如下步骤：

#### 1. Fork 仓库
访问 [https://github.com/BigShuiTai/dapiya_kernel_deb_builder](https://github.com/BigShuiTai/dapiya_kernel_deb_builder) ，点击右上角的 `Fork` 按钮，并 clone 到本地。

#### 2. 更新 config 文件
在本地将您获取的 config 文件替换根目录下的 `config`，可以从您系统的 `/boot/config*` 文件复制，或者手动编辑。

#### 3. 编写自定义修改脚本
本仓库在处理 bug 时已经删除了自定义脚本的目录。请在您 clone 过的仓库内添加 `patch.d` 目录，并放入您的自定义脚本，删除 `build_action.sh` 中 `source ../patch.d/*.sh` 前的注释符号，即可在编译内核时运行您的自定义脚本。

#### 4. 推送修改
推送后，action 自动触发，可以在您的仓库页面的 `Actions` 选项卡查看进度详情。

#### 5. 下载安装
下载 action 运行成功后生成的 `artifact.zip` 文件并将其解压，然后终端下执行 `sudo dpkg -i *.deb`，即可安装编译后的内核。
