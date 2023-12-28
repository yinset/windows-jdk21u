# windows-jdk21u-compile
windows平台使用cygwin进行编译</br></br>
编译准备：</br>
Cygwin安装时软件包添加：</br>
autoconf</br>
make</br>
zip</br>
unzip</br>
软件包名严格对应（版本选择不影响）</br>

Windows 10软件安装:</br>
vs2019 安装C++环境（2019及以上均可）</br>
jdk21    （源码版本的N-1及以上即可）</br>
git</br>

jdk源码配置文件更改（中文系统必须做）：</br>
源码文件夹/make/autoconf/toolchain.m4</br>
搜索Target CPU</br>
找到其中含有x64的if语句（非x64系统按需更改）</br>
把AC_MSG_ERROR改成AC_MSG_RESULT</br>
-
<img width="913" alt="批注 2023-12-28 201548" src="https://github.com/yinset/windows-jdk21u-compile/assets/80797110/fe663e45-6495-4c4b-aae1-b33a3d8ec729"></br>


</br></br>

编译步骤：</br>
打开cygwin</br>
cd到源码目录</br>
执行 bash configure --disable-warnings-as-errors （此选项可避免C2220+C4819编码错误，是中文系统原因，目前无解决办法。添加此选项对编译出的jdk无影响）</br>
执行 make 后等待完成</br>
</br>
完成后，</br>
源码文件夹进入build，进入编译版本文件夹
其中jdk文件夹为成品</br>
祝一遍过~</br>
<img width="537" alt="嗨嗨！" src="https://github.com/yinset/windows-jdk21u-compile/assets/80797110/f099534e-dcd3-4351-9ee0-8559a2d14a7c">

