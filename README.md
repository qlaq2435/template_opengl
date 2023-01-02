# opengl环境配置

## 安装相关包

```shell
sudo apt-get install build-essential libgl1-mesa-dev
sudo apt-get install freeglut3-dev
sudo apt-get install libglew-dev libsdl2-dev libsdl2-image-dev libglm-dev libfreetype6-dev
```

```shell
sudo apt-get install libglfw3-dev # 安装glfw3

sudo apt install mesa-utils
DISPLAY=:0 glxgears -info | grep GL_VERSION # 查看显卡对应的 opengl 版本
```

输出如下结果：

```shell
GL_VERSION    = 3.3 (Compatibility Profile) Mesa 22.0.5
```

在该[网站](https://glad.dav1d.de/) 进行选择，然后生成代码文件.

将zip文件解压后，将文件移动到指定路径下：

```
sudo mv glad/ /usr/local/include #将glad目录移动到/usr/local/include
sudo mv KHR/ /usr/local/include #将KHR目录移动到/usr/local/include
```

`glad.c` 留着，copy在自己project的路径里。

`glad.c` 复制后有的还需要修改`"glad.h"` 为 `<glad/glad.h>`

以及对glad.h要进行如下修改，注释掉error行，要不然多个文件包含glad.h头文件时老是会报错。

```text
#ifdef __gl_h_
//#error OpenGL header already included, remove this include, glad already provides it
#endif
```

glad安装完毕。
