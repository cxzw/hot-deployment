Springboot的简单创建和idea上的热部署
-------------------------------

# idea创建简单springboot项目
菜单 -> New -> Project -> Spring Initializr 然后点 Next

![此处输入图片的描述][1]

输入如图所示的两个地方的参数，其他参数不用修改，然后Next

![此处输入图片的描述][2]

接着左边选择 Web, 右边只勾选 Web 即可，然后点击Next

![此处输入图片的描述][3]

项目创建好之后，就自带一个SpringbootApplication, 其被@SpringBootApplication 所标记，表示这个是一个Springboot 应用

![此处输入图片的描述][4]

新建包 com.how2java.springboot.web， 然后在其下新建类HelloController.
这个类就是Spring MVC里的一个普通的控制器。
@RestController 是spring4里的新注解，是@ResponseBody和@Controller的缩写。
```
package com.how2java.springboot.web;
 
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;
 
@RestController
public class HelloController {
 
    @RequestMapping("/hello")
    public String hello() {
        return "Hello Spring Boot!";
    }
 
}
```
然后直接点击绿色箭头运行即可
访问地址
```
http://127.0.0.1:8080/hello
```
![此处输入图片的描述][5]


# 热部署

1. 打开build.gradle,在依赖中加入
```
compile("org.springframework.boot:spring-boot-devtools")
```
2. 打开idea设置

![此处输入图片的描述][6]

3. windows下使用ctrl+shift+alt+/

![此处输入图片的描述][7]

![此处输入图片的描述][8]

4. 开启IDEA自动编译

![此处输入图片的描述][9]


  [1]: http://stepimagewm.how2j.cn/7127.png
  [2]: http://stepimagewm.how2j.cn/7128.png
  [3]: http://stepimagewm.how2j.cn/7129.png
  [4]: http://stepimagewm.how2j.cn/7131.png
  [5]: http://stepimagewm.how2j.cn/7133.png
  [6]: https://img-blog.csdn.net/20180527220127711
  [7]: https://img-blog.csdn.net/20180527220139991
  [8]: https://img-blog.csdn.net/20180527220147887
  [9]: http://image.mamicode.com/info/201801/20180108231755200765.png