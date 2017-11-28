

- 发现找不到Tensorflow的包,需要将CUDA的路径加入环境变量中

``` bash {.line-numbers}
export PATH=/usr/local/cuda-8.0/bin:$PATH
export LD_LIBRARY_PATH=/usr/local/cuda-8.0/lib64:$LD_LIBRARY_PATH
```

- python所依赖的包都安装好以后，首次运行会报错：
```
ImportError: libcusolver.so.8.0: cannot open shared object file: No such file or directory
``` 
- 然后需要配置pycharm：

pycharm 菜单栏Run-Edit Configurations 中 Environment Variables中添加变量LD_LIBRARY_PATH，值为/usr/local/cuda-8.0/lib64。之后编译即可。
