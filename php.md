| 问题                                                       | 地址                                                         |
| ---------------------------------------------------------- | :----------------------------------------------------------- |
| mysql命令行thinkphp中的foreach和volist对比和详解及常用方法 | [链接](https://blog.csdn.net/Dailoge/article/details/70792633) |
| phpstorm误删除的文件或文档找回方式                         | [链接](https://blog.csdn.net/well2049/article/details/78670159) |
| phpstorm的撤销和反撤销快捷键                               | [1](https://imshusheng.com/php/120.html)                     |
| ThinkPHP搭建百度Ueditor富文本编辑器                        | [1](https://blog.csdn.net/C_jian/article/details/76692851)   |
| DIV层的大小和位置的设置                                    | [1](https://blog.csdn.net/Hampton_Chen/article/details/52817236) |
| ThinkPHP5.1 图片上传修改反斜线替换为斜线\                  | [1](https://blog.csdn.net/u011415782/article/details/88576727) |
| 修改数据库SQL表中id，怎样让它从1开始呢？                   | [1](https://zhidao.baidu.com/question/552566287.html)        |
| phpstorm 配置 FTP                                          | [1](https://blog.csdn.net/qq_35616854/article/details/77877493) |
|                                                            |                                                              |

##### tp5中渲染页面将时间戳转换显示为日期时间格式

```
 {$vo.create_time|date="Y-m-d H:i:s"}
```

##### Thinkphp5 日期与时间戳相互转换

```
日期转换为时间戳
$date="2013-10-01 12:23:14";
dump(strtotime($date)); //=>1380601394

```

##### 三目运算符

```
(expr1) ? (expr2) : (expr3) 
对 expr1 求值为 TRUE 时的值为 expr2，在 expr1 求值为 FALSE 时的值为 expr3。
PHP 5.3 起，可以省略三元运算符中间那部分。表达式 expr1 ?: expr3 在 expr1 求值为 TRUE 时返回 expr1，否则返回 expr3。
```

##### html中使用if

```
{if condition="$item.type == 1"}
	选择题
{else /}
	判断题
{/if}


{if condition="$vo['department'] eq null"}
	<span>未填写</span>
{else /}
	{$vo['department']}
{/if}
```

##### tp5常用代码块

```
foreach($res as $k=>$v){

}

setInc('integral',20) 字段自增20 setDec 字段自减

// 分页加数据操作
$res = Db::name('xy_education')->where('status',1)->paginate(5)
            ->each(function ($item) use ($uid){
                $where = [
                    'education_id' => $item['id'],
                    'uid' => $uid
                ];
                $res1 = Db::name('xy_education_praise')->where($where)->find();
                if($res1){
                    $item['praise_status'] = 1;
                }
                else{
                    $item['praise_status'] = 2;
                }
                $image = rand(1, 9);
                $item['image'] = "public/static/images/education/" . $image . ".png";
                return $item;
            });
            
config('wx.app_id') 读取config文件夹下的wx.php的app_id
$mpUrl = $_GET["mpUrl"]; 获取地址问号后面传过来的值

拼接字符串
$url = sprintf(config('wx.get_code'), $this->wxAppID, $redirect_uri);
'get_code' => 'https://open.weixin.qq.com/connect/oauth2/authorize?appid=%s&redirect_uri=%s&response_type=code&scope=snsapi_userinfo&state=123#wechat_redirect'

重定向
$this->redirect($url);

在一个地址获取内容
file_get_contents($url)

请求 $url 返回一个json  json_decode不加 true 会将json转为对象，加true转为数组
json_decode(file_get_contents($url),true);

生成令牌
public function generateToken()
{
    $randChar = getRandChar(32);
    $timestamp = $_SERVER['REQUEST_TIME_FLOAT'];
    $tokenSalt = config('wx.token_salt');
    return md5($randChar . $timestamp . $tokenSalt);
}

请求head头的信息
$token = Request::header('token');

往本地写数据
file_put_contents('1.txt',$media_id);

路径写法
$savepath = 'public' . DS . 'uploads'. DS .'opinion'. '/'.$filename;


表格分页HTML
{$field->render()|raw()}

删除的同时，删除图片
$path = $res['image'];
if(file_exists($path)){
	unlink($path);
}

显示富文本的内容
{$activity['introduction']|raw}

表单显示图片及样式
<img src="{$vo['head_img_url']}" height="30px" width="30px">
```

##### CSS布局

```
上左下右 间隔
<div style="padding: 0px 10px 0px 10px;"></div>
```

##### php判断数组中是否存在指定键(key)的方法

```
array_key_exists($key, $array)
```

##### url生成器

```
href="{:url('houtai/activity/add')}"
```

##### 数组合并

array_merge() 函数把一个或多个数组合并为一个数组。

##### TP5正序和倒序

如果没有指定`desc`或者`asc`排序规则的话，默认为`asc`。正序

##### 三目运算符

```

$if_summary = $row['IF_SUMMARY']==2?'是':'否';

等价于

if($row['IF_SUMMARY']==2){

$if_summary="是";

}else{

$if_summary="否"；

}


```

##### phpstrom黄色警告

Settings > editor > Inspections > PHP > Composer > Extension is missing in composer,json



##### switch

```
switch (n)
{
case label1:
    如果 n=label1，此处代码将执行;
    break;
case label2:
    如果 n=label2，此处代码将执行;
    break;
default:
    如果 n 既不等于 label1 也不等于 label2，此处代码将执行;
}
```

