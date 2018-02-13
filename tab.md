###   tab切换
样式可以自己调整
####  演示代码
- css部分
``` css
<style type="text/css">
    * {
	    margin:0;
	    padding:0;
	    list-style:none;
    }
    #outer {
        margin:150px auto;
	    width:450px;
    }
    #tab {
	    overflow:hidden;
	    border:1px solid #000;
	    background:#000;
    }
    #tab li {
	    float:left;
	    padding:0 20px;
	    height:30px;
	    line-height: 30px;
	    color:#fff;
	    cursor:pointer;
    }
    #tab li.current {
	    color:#000;
	    background:#ccc;
    }
    #content {
	    border:1px solid #000;
	    border-top: none;
    }
    #content ul {
        display:none;
        padding:10px 0;
        margin:0 30px;
	    line-height:25px;	    
    }
</style>
```
- html部分
``` htmlbars
<div id="outer">
    <ul id="tab">
        <li class="current">111</li>
        <li>222</li>
        <li>333</li>
    </ul>
    <div id="content">
        <ul style="display:block;">
           <a href="#">111</a>
        </ul>
        <ul>
            <a href="#">222</a>
        </ul>
        <ul>
           <a href="#">333</a>
        </ul>
    </div>
</div>
``` 
- js部分
``` js
<script type="text/javascript" src="js/jquery-1.12.1.js"></script>
<script>
	$(function(){
		window.onload = function(){
			var $li = $('#tab li');
			var $ul = $('#content ul');
						
			$li.mouseover(function(){
				var $this = $(this);
				var $t = $this.index();
				$li.removeClass();
				$this.addClass('current');
				$ul.css('display','none');
				$ul.eq($t).css('display','block');
			});
		}
	});
</script>
```