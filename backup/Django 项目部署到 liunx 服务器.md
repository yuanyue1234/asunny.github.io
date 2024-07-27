## 一、准备工作

### 1. 检查虚拟环境目录

首先，确认虚拟环境目录是否存在，并且 `python` 可执行文件也存在：

```bash
ls /root/Django/venv/bin/
```

### 2. 激活虚拟环境

尝试手动激活虚拟环境：

```bash
source 路径/.venv/Scripts/activate
```

### 3. 虚拟环境与操作系统

通常，很多问题是由虚拟环境导致的。例如，当我在 Windows 系统上写好的文件导入到 Linux 中运行时，无法使用 Windows 中的虚拟环境，需要在 Linux 中重新建立一个虚拟环境。以下是不同系统虚拟环境的路径区别：

- `venv/bin/` 是 Linux 系统的虚拟环境
- `venv/Scripts/` 是 Windows 系统的虚拟环境

因此，建议直接使用全局的 Python 编译器。另外，有些系统的编译器只能使用 `python3` 作为命令。

## 二、环境配置

### 1. 检查 Python 版本

```bash
python3 --version
```

### 2. 移动到项目目录

```bash
cd /www/wwwroot/Top250_douban
```

### 3. 安装必要依赖

如果项目中有 `requirements.txt` 文件，可以通过以下命令安装依赖：

```bash
pip install -r requirements.txt
```

## 三、启动项目

### 1. 迁移数据库

```bash
python manage.py migrate
```

### 2. 启动 Django 开发服务器

```bash
python3 manage.py runserver 0.0.0.0:8000
```

### 3. 访问 Django 项目

打开浏览器，访问 [http://<你的服务器IP>:8000](http://<你的服务器IP>:8000)

## 四、项目后台运行

当断开 SSH 连接后，Django 项目会停止运行。可以使用多种办法解决，例如安装其他的守护进程程序。

### 使用宝塔面板中的进程守护管理器

宝塔面板中的进程守护管理器可以方便地管理 Django 项目，确保其在后台持续运行。
![image](https://github.com/user-attachments/assets/df61dfcf-2a76-41b6-9cdd-2244fe6e3b45)


## 五、处理常见错误

### 错误信息：DisallowedHost

错误信息：

```text
DisallowedHost at / Invalid HTTP_HOST header: '107.172.79.161:8000'. You may need to add '107.172.79.161' to ALLOWED_HOSTS.
```

### 解决方法

这是一个常见的 Django 错误，表示当前请求的主机不在你的 Django 项目的 `ALLOWED_HOSTS` 列表中。你需要将你的服务器 IP 地址添加到 `ALLOWED_HOSTS` 中。

编辑 `settings.py` 文件：

```python
ALLOWED_HOSTS = ['你的ip地址']
```

或使用通配符：

```python
ALLOWED_HOSTS = ['*']
```

## 六、使用宝塔面板启动 Python 项目

宝塔面板中有 Python 项目启动器，可以快捷安装对应不同版本的 Python 环境，并且运行虚拟环境。内置了 Django 项目，可以直接上传 Django 项目后使用，一键搞定。

这是对应的教程：[Python项目--Flask/Django框架项目部署 - Linux面板 - 宝塔面板论坛](https://bt.cn)
![image](https://github.com/user-attachments/assets/417745cf-95fd-47e8-b565-551a18c59ac3)
