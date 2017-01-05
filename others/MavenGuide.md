# Maven Guide

## 目录

[TOC]


## 下载并安装maven

   * 在maven官网上下载maven安装包安装。
   * 将maven的 `bin` 目录添加到 `PATH` 中。
   * 使用以下命令查看maven的相关属性。
   
   ```
   mvn --version
   ```

## 创建项目
	
	输入下面的命令新建一个maven项目。

	```
	mvn archetype:generate -DgroupId=org.wanpengniu.maventest -DartifactId=maventest -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false DarchetypeCatalog=local
	```


