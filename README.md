- 新建工程
- 创建需要打`jar`的 `model` `librarydemo`
- 在`librarydemo` 的 `build.gradle`中加入如下代码


    ```
    task makeJar(type: Copy) {
        //删除存在的
        delete 'build/libs/myjar.jar'
        //设置拷贝的文件
        from('build/intermediates/bundles/default/')
        //打进jar包后的文件目录
        into('build/libs/')
        include('classes.jar')
        rename('classes.jar','myjar.jar')
    }
    makeJar.dependsOn(build)
    
    ```

- 在`Terminal`中 输入`./gradlew makeJar`, 会车就看到结果了

------

**注意在新版的`as`中是`default`文件夹不是`release`**


