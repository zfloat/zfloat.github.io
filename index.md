# <center>基于网络编程语言在异构网络中实现意图智能配置的方法</center>

## 系统模块介绍

 <p style="text-indent: 2em;">意图网络架构下的智能配置模块如下图所示，包括四层结构：应用层包含意图解析引擎，向上为用户及网络管理人员提供服务，收集用户表达的意图并将提取意图关键词；抽象层包含业务编排器，根据网络资源状态及意图关键词生成网络策略；控制层包含全局SDN控制器及其下管的支持OpenFlow协议的域控制器与支持NETCONF协议的域控制器；数据层包含支持OpenFlow协议的底层网元设备与支持NETCONF协议的底层网元设备，这些设备分别受对应的域控制器的管控。

<img align="center" src="resources\Architecture.png" style="  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 35%;" />


<script type="text/javascript">
        function myFunction() {
            // 这里写入要执行的代码逻辑
            // alert("Hello World!");
            var table = document.getElementById("mytab1");
            var td1=table.getElementsByTagName("tr").item(1).getElementsByTagName("td").item(0)

            
            code1 = 'import frenetic\nfrom frenetic.syntax import *\n \nclass MyApp(frenetic.App):\n    p1 = IP4DstEq(106.11.226.158, 32)\n    p2 = IP4DstEq(211.144.27.126, 32)\n    p3 = IP4DstEq(218.2.112.234, 32)\n    selectPacket = Or([p1, p2, p3])\n    Drop(selectPacket)\n    \napp = MyApp()\napp.start_event_loop()'
            code2 =  'print("hello world2")'
            defined_content = '<pre style="text-align: left;">' + code1 + '\n' + code2 + '</pre>';
            td1.innerHTML = defined_content
        }

        function myFunction2() {
            var table = document.getElementById("mytab2");
            var td1=table.getElementsByTagName("tr").item(1).getElementsByTagName("td").item(0)

            // XML数据（这里只作为示例）
            var xmlString = "<access-lists><access-list><name>BlockEntertainment</name><aces><ace><name>DenyEntertainmentSite1</name><matches><ipv4><destination-ip-address>220.181.38.148</destination-ip-address></ipv4></matches><actions><forwarding>drop</forwarding></actions></ace><!-- Add more ACEs for other entertainment sites --></aces></access-list></access-lists>";

            xmlString = "&lt;access-lists&gt;\n\t&lt;access-list&gt;\n\t\t&lt;name&gt;BlockEntertainment&lt;/name&gt;\n\t\t&lt;aces&gt;\n\t\t\t&lt;ace&gt;\n\t\t\t\t&lt;name&gt;DenyEntertainmentSite1&lt;/name&gt;\n\t\t\t\t&lt;matches&gt;\n\t\t\t\t\t&lt;ipv4&gt;\n\t\t\t\t\t\t&lt;destination-ip-address&gt;220.181.38.148&lt;/destination-ip-address&gt;\n\t\t\t\t\t&lt;/ipv4&gt;\n\t\t\t\t&lt;/matches&gt;\n\t\t\t\t&lt;actions&gt;\n\t\t\t\t\t&lt;forwarding&gt;drop&lt;/forwarding&gt;\n\t\t\t\t&lt;/actions&gt;\n\t\t\t&lt;/ace&gt;\n\t\t\t&lt;!-- Add more ACEs for other entertainment sites --&gt;\n\t\t&lt;/aces&gt;\n\t&lt;/access-list&gt;\n&lt;/access-lists&gt;";

            <!-- xmlString = "&lt;access-lists&gt;\n&lt;access-list&gt;\n&lt;name&gt;BlockEntertainment&lt;/name&gt;\n&lt;aces&gt;\n&lt;ace&gt;\n&lt;name&gt;DenyEntertainmentSite1&lt;/name&gt;\n&lt;matches&gt;\n&lt;ipv4&gt;\n&lt;destination-ip-address&gt;220.181.38.148&lt;/destination-ip-address&gt;\n&lt;/ipv4&gt;\n&lt;/matches&gt;\n&lt;actions&gt;\n&lt;forwarding&gt;drop&lt;/forwarding&gt;\n&lt;/actions&gt;\n&lt;/ace&gt;\n&lt;!-- Add more ACEs for other entertainment sites --&gt;\n&lt;/aces&gt;\n&lt;/access-list&gt;\n&lt;/access-lists&gt;"; -->
            
           
            
            defined_content = '<pre><code>' + xmlString + '</code></pre>'
            td1.innerHTML = defined_content
        }
        
        function progress() {
            var bar = document.getElementById("progress1");
            var width = 0;
            var id = setInterval(frame, 10);
            function frame() {
                if (width >= 100) {
                    clearInterval(id);
                    myFunction();
                }
                else {
                    width++;
                    bar.style.width = width + '%';
                }
            }
        }

        function progress2() {
            var bar = document.getElementById("progress2");
            var width = 0;
            var id = setInterval(frame, 10);
            function frame() {
                if (width >= 100) {
                    clearInterval(id);
                    myFunction2();
                }
                else {
                    width++;
                    bar.style.width = width + '%';
                }
            }
        }
        
  
</script>


<h2>意图接口</h2>
<form  method="get">
  <p><input type="text" name="fname" value="请输入业务意图..." style="width: 600px;height:100px; margin-left:100px" />   <button style="width:100px; height:50px; border: none; border-radius: 10px; font-family: sans-serif; margin-left:50px" type="button" onclick='progress()' >确认业务</button></p>
 
  <!-- <input type="submit" value="Submit" /> -->
</form>


<div class="progress-bar" style="margin-top:10px; margin-bottom:20px; margin-left:100px">
  <div class="progress" id="progress1"></div>
</div>

<div style="margin-left:100px">
    <table style='width: 100%;' id='mytab1'>
        <thead>
        <tr>
            <th width="800px">Frenetic网络策略输出</th>
            <!-- <th width="400px">模型输出-2</th>
            <th width="400px">实际答案</th> -->
        </tr>
        </thead>
        <tbody>
        <tr>
            <td width="800px" height="400px"></td>
            <!-- <td width="400px" height="400px"></td>
            <td width="400px" height="400px"></td> -->

        </tr>
    </tbody>
    </table>
</div>



 <button style="width:800px; height:50px; border: none; border-radius: 10px; font-family: sans-serif;margin-left:100px" type="button" onclick='progress2()' >配置生成</button>

 <div class="progress-bar" style="margin-top:10px; margin-bottom:20px; margin-left:100px">
  <div class="progress" id="progress2"></div>
</div>

<div style="margin-left:100px;margin-bottom:100px">
    <table style='width: 100%;' id='mytab2'>
        <thead>
        <tr>
            <th width="800px">设备配置输出</th>
            <!-- <th width="400px">模型输出-2</th>
            <th width="400px">实际答案</th> -->
        </tr>
        </thead>
        <tbody>
        <tr>
            <td width="800px" height="400px" style="text-align:left"></td>
            <!-- <td width="400px" height="400px"></td>
            <td width="400px" height="400px"></td> -->

        </tr>
    </tbody>
    </table>
</div>

