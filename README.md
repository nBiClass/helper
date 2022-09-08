### 整理一些常用 PHP 函数，慎用，或者锁定版本使用


>* 不定时更新，随时新增函数，但是不会删除和修改函数名
>* 会根据实际使用情况添加参数，但不会减少参数
>* 无论怎么修改，函数返回结构不会变化


### 使用
> 安装： composer require longzy/helper

````
include __DIR__.'/../vendor/autoload.php';
use longzy\helper;

//随机生成一个知道长度的数字编码
$number=helper::make_number(12);
var_dump($number);

````
>**网络请求**

| |方法名|说明
|----|----|----
|1|`https_request($url, $data = null, $header = null)`|发起网络请求CURL
|2|`get_page_url()`|获取当前页面完整URL

>**身份证号码信息读取**

| |方法名|说明
|----|----|----
|1|`get_idcard_info($IDCard)`|身份证号码信息读取


>**文件操作**

| |方法名|说明
|----|----|----
|1|`scan_dir(&$arr_file, $directory)`|获取文件下所有文件
|2|`del_dir($path)`|删除文件或者目录，包含目录下文件
|2|`file_extension($filename)`|获取文件尾缀
|2|`file_format_size($size)`|获取文件尾缀

>**字符串操作**

| |方法名|说明
|----|----|----
|1|`make_number($lenth = '9', $pk = '')`|生成指定长度的纯数字编号
|2|`url_md5($data, $key = 'HelloWord', $expire = 0)`|url或者字符串加密
|3|`url_decrypt($data, $key = 'HelloWord')`|url或者字符串解密
|4|`str_filter($nickname)`|过滤微信昵称，颜文字，手机表情文字
|5|`str_mark($str, $star = 3, $leng = 4, $mark = '*')`|将字符串指定位置替换为知道符号，类似处理手机号中间四位 **** 代替
|6|`complete_number($num = 0, $leng = '3')`|按长度补全数字，不足的用 0  补足

>**数组操作**

| |方法名|说明
|----|----|----
|1|`array_asc($array) `|冒泡排序（数组排序） 从小到大


>**数组树形结构**

| |方法名|说明
|----|----|----
| |方法名|说明
|1|`list_to_tree($list, $pk = 'id', $pid = 'pid', $child = 'children', $root = 0)`|将数组转为树形结构
|2|`get_subs($categorys, $catId = 0, $id = 'id', $p = 'pid')`|获取树形菜单下某个分类的全部子类
|3|`get_menu_tree($arrCat = array(), $parent_id = 0, $level = 0, $all = True)`|获取指定id的所有父级ID

