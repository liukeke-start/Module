###   返回顶部
兼容IE以及谷歌火狐等浏览器
####  演示代码
- css部分
``` css
<style type="text/css">
    span{ 
        position:fixed; 
        right:50px; 
        bottom:50px; 
        display:none;
        cursor:pointer; 
        width:36px; 
        height:65px; 
        background-color: #ccc; 
    }
</style>
```
- js部分
``` js
<script type="text/javascript" src="js/jquery-1.12.1.js"></script>
<script type="text/javascript">
$(function(){	
	$(window).scroll(function(e) {
		//如果窗口的滚动位置大于第一屏的高度则出现火箭否则都没有
		var win_s=$(window).scrollTop();
		var win_h=$(window).height()
		
        if(win_s>win_h){
        	$('span').fadeIn()
        }else{
        	$('span').fadeOut();
        }
    });
	$('span').click(function(e) {
        //需要设置窗口的滚动位置
		$('html,body').animate({ scrollTop:0},500)
    });
})
</script>
```