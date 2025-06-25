## 一、表格标签

1.基本语法

```
<table>
	<tr>
		<td></td>
	<tr>
</table>
1.<table>定义表格
2.<tr>定义表格中的行
3.<td>定义表格中的单元格
```

2.表头单元格标签

```
<th>表示HTML表格的表头部分
文本加粗居中表示
```

3.表格属性

```
实际开发通过CSS设置
```

```
align 对齐方式
border 是否有边框
cellpadding 单元边沿与其内容之间的空白
cellspacing 单元格之间的空白
width 表格宽度
```

4.表格结构标签

```
<thead>表示表格的头部区域，内部必须有<tr>
<tbody>表示表格主体部分
```

5.合并单元格

```
跨行合并：rowspan="合并单元格的个数"
跨列合并：colspan="合并单元格的个数"
```

```
目标单元格：
跨行：最上侧单元格为目标单元格，写合并代码
跨列：最左侧
```

## 二、列表标签

```
用来布局的标签
```

```
1.无序列表
2.有序列表
3.自定义列表
```

1.无序列表（重点）

语法格式

```
<ul>
	<li>列表项</li>
	<li>列表项</li>
	<li>列表项</li>
</ul>
```

```
ul标签中只能存放li标签
```

2.有序列表（理解）

```
<ol>
	<li>列表项</li>
	<li>列表项</li>
	<li>列表项</li>
</ol>
```

```
ol标签中只能存放li标签
```

3.自定义列表（重点）

```
用于对术语或者名词进行解释，定义列表的列表项前没有任何符号
```

```
<dl>
	<dt>名词</dt>
	<dd>名词解释1</dd>
	<dd>名词解释2</dd>
</dl>
```

```
dl中只能由dt和dd
```

## 三、表单标签

1.表单组成

```
表单域、表单控件（表单元素）、提示信息。
```

2.表单域

```
包含表单元素的区域
收集信息发送给服务器
```

```
<form action="url地址" method="提交方式" name="表单域名称">
	各种表单元素控件
</form>
```

```
action 指定接收处理表单数据的服务器url地址
method 设置表单数据的提交方式 post get
name 指定表单的名称用于区别
```

3.表单控件（元素）

3.1 <input>表单元素

```
收集用户信息
```

```
<input type="属性值">
```

```
是单标签
```

```
type属性值：（常见）
text 文本框
password 密码框
radio 单选按钮
checkbox 复选框

submit 提交按钮
reset 重置按钮

button 普通按钮（通过js启动）
file 文件域
```

```
<input>其它属性：
1.name 定义input元素名称
2.value 规定input元素的值
3.checked 规定此input元素首次加载时应当被选中
4.maxlength 规定输入字段字符的最大长度

注意：
1.name和value主要给后台人员使用
2.单选和复选框要有相同的name值
```

3.2 <label>标签

```
为input元素定义标注
绑定一个表单元素，当点击<label>标签内的文本时，浏览器自动聚焦，增加用户体验。
```

```
<label for="sex">男</label>
<input type="radio" name="sex" id="sex" />
核心：label标签的for属性应该与相关元素的id属性相同
```

3.3 select下拉表单元素

```
<select>
	<option>选项1</option>
	<option>选项2</option>
	<option>选项3</option>
	……
</select>
```

```
在<option>中定义selected="selected"时，当前项即为默认选中项。
```

3.4 textarea文本域标签

```
定义多行文本输入
```

```
<textarea rows="3" cols="20">
	文本内容
<textarea>
```

## 四、综合案例

1.页面

![image-20250625230141163](https://gitee.com/weido34/typora-image/raw/master/img/image-20250625230141163.png)

2.代码实现

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>综合案例-注册页面</title>
</head>
<body>
        <h4>青春不常在，抓紧谈恋爱</h4>
        <table width="600">
            <tr>
                <td>性别</td>
                <td>
                    <input type="radio" name="sex" id="nan" checked="checked">
                    <label for="nan">男</label>
                    <input type="radio" name="sex" id="nv">
                    <label for="nv">女</label>
                </td>
            </tr>
            <tr>
                <td>生日</td>
                <td>
                    <!-- 第一个下拉列表 -->
                    <select>
                        <option>--请选择年--</option>
                    </select>
                    <!-- 第二个下拉列表 -->
                    <select>
                        <option>--请选择月--</option>
                    </select>
                    <!-- 第三个下拉列表 -->
                    <select>
                        <option>--请选择日--</option>
                    </select>
                </td>
            </tr>
            <tr>
                <td>所在地区</td>
                <td>
                    <input type="text" value="北京思密达">
                </td>
            </tr>
            <tr>
                <td>婚姻状况</td>
                <td>
                    <input type="radio" name="hunyin" id="weihun" checked="checked">
                    <label for="weihun">未婚</label>
                    <input type="radio" name="hunyin" id="yihun">
                    <label for="yihun">已婚</label>
                    <input type="radio" name="hunyin" id="lihun">
                    <label for="lihun">离婚</label>
                </td>
            </tr>
            <tr>
                <td>学历</td>
                <td>
                    <input type="text" value="幼儿园">
                </td>
            </tr>
            <tr>
                <td>喜欢的类型</td>
                <td>
                    <input type="checkbox" name="love">妩媚的
                    <input type="checkbox" name="love">可爱的
                    <input type="checkbox" name="love">小鲜肉
                    <input type="checkbox" name="love">老腊肉
                    <input type="checkbox" name="love">都喜欢
                </td>
            </tr>
            <tr>
                <td>自我介绍</td>
                <td>
                    <textarea rows="5" cols="50">自我介绍
                    </textarea>
                </td>
            </tr>
            <tr>
                <td></td>
                <td>
                    <input type="submit" value="免费注册">
                </td>
            </tr>
            <br>
            <tr>
                <td></td>
                <td>
                    <input type="checkbox" checked="checked">我同意注册条款和会员加入标准
                </td>
            </tr>
            <br>
            <tr>
                <td></td>
                <td>
                    <a href="xxx.php">我是会员，立即登录</a>
                </td>
            </tr>
            <tr>
                <td></td>
                <td>
                <h4>我承诺</h4>
                <ul>
                    <li>年满18岁，单身</li>
                    <li>抱着严肃的态度</li>
                    <li>真诚寻找另一半</li>
                </ul>
                </td>
            </tr>
        </table>
</body>
</html>
```

