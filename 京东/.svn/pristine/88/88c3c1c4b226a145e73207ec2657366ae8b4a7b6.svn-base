window.onload=function () {
	//通过ID寻找所有ClassName
	function byClass(el,oClass){
	var aEl=el.getElementsByTagName("*");
	var arr=[];
	for (var i=0; i<aEl.length; i++){
		if (aEl[i].className==oClass){
			arr.push(aEl[i]);
		}
	}
	return arr;
	}
	//通过父级ID寻找子级ClassName
	function getclass(parentID,className) {
		var parent=document.getElementById(parentID);
		var tags=parent.all ? parent.all : parent.getElementsByTagName('*');
		var arr=new Array();

		for (var i = 0; i < tags.length; i++) {
		if(tags[i].className.indexOf(className)!=-1){
			arr.push(tags[i]);
		};
		};
		return arr;
	};

	// 右侧悬浮
	$(function () {
        $('#go-box li').hover(
            function () {
                 // alert(1);
                var i=$(this).index();
                $('.tab-text').eq(i).show().stop().delay(400).animate({left:'-67px',width:'70px'})
            },
            function () {
                 // alert(1);
                var i=$(this).index();
                $('.tab-text').eq(i).stop().delay(400).animate({left:'2px',width:'0'},function(){$('.tab-text').eq(i).hide()})
            }

            )
        }
    );
    $(function(){
    	$('#goup .go-up').click(
        	function () {
    			$('body,html').animate({scrollTop:0},200);
    		}
    	)
    }
    	)
	
//下拉
xiala ();
function xiala () {
	
	var topw =document.getElementById('top-w');
	// var liovers =topw.getElementsByClassName('liover');
	var liovers =getclass('top-w','live')
		// alert(liovers.length)
	for (var i = 0; i < liovers.length; i++) {
		liovers[i].onmouseover=function () {
			for (var i = 0; i < liovers.length; i++) {
				if (liovers[i]==this) {
					var s = liovers[i].getElementsByTagName('s')[0];
					// var selects = liovers[i].getElementsByClassName('liover-s')[0];
					// var dd = liovers[i].getElementsByClassName('dd')[0];
					// var selects =getclass('w-dh','liover-s')[0];
					// var dd =getclass('w-dh','dd')[0];
					var selects = liovers[i].getElementsByTagName('div')[1];
					var dd = liovers[i].getElementsByTagName('div')[0];
					s.style.top = -2+'px';
					dd.style.background = '#fff';
					dd.style.border = '1px solid #DFDFDF';
					dd.style.borderTop = ''
					dd.style.borderBottom ='1px solid #fff';
					dd.style.paddingLeft = '9px';
					dd.style.paddingRight = '22px';
					selects.style.display = 'block';
				}
			}
		}
		liovers[i].onmouseout=function () {
			for (var i = 0; i < liovers.length; i++) {
				if (liovers[i]==this) {
					var s = liovers[i].getElementsByTagName('s')[0];
					// var selects = liovers[i].getElementsByClassName('liover-s')[0];
					// var dd = liovers[i].getElementsByClassName('dd')[0];
					// var selects =getclass(liovers[i],'liover-s')[0];
					// var dd =getclass(liovers[i],'dd')[0];
					var selects = liovers[i].getElementsByTagName('div')[1];
					var dd = liovers[i].getElementsByTagName('div')[0];
					s.style.top = -8+'px';
					selects.style.display = 'none';
					dd.style.background = '';
					dd.style.border = '';
					dd.style.paddingLeft = '10px';
					dd.style.paddingRight = '23px';
				}
			}
		}
	}

	var select = document.getElementById('select');
	var lis =select.getElementsByTagName('li');
	var ultext =document.getElementById('ultext')

	for (var i = 0; i < lis.length; i++) {
		lis[i].onclick =function(){
			for (var i = 0; i < lis.length; i++) {
				if (lis[i]==this) {
					var as =lis[i].getElementsByTagName('a')[0];
					var selects = lis[i].parentNode.parentNode
					as.style.background ='red';
					as.style.color ='#fff';
					ultext.innerText = lis[i].innerText;
					selects.style.display = 'none';
				}else{
					var as =lis[i].getElementsByTagName('a')[0];
					as.style.background ='';
					as.style.color ='';
				}
			};
		}
	};
};	
//获取焦点
 	var wss = document.getElementById('w-ss');
 	var ss  = wss.getElementsByTagName('input');
 	ss[0].onfocus = function () {
 		ss[0].value = ''
 	}
 	ss[0].onblur = function () {
 		ss[0].value = '平板电脑'
 	}

	//左侧导航
	leftdh();
	function  leftdh() {
			var focusleft = document.getElementById('focus-left');
			var lis = focusleft.getElementsByTagName('li')
			for (var i = 0; i < lis.length; i++) {
				lis[i].onmouseover =function () {
					for (var i = 0; i < lis.length; i++) {
						if (lis[i]==this) {
							var selectbox = lis[i].getElementsByTagName('div');
							selectbox[1].style.display ='block';
							selectbox[1].style.top = -i*31-1+ 'px'
							
						}
					}
				}
				lis[i].onmouseout =function () {
					for (var i = 0; i < lis.length; i++) {
						if (lis[i]==this) {
							var selectbox = lis[i].getElementsByTagName('div');
							selectbox[1].style.display ='none';
						}
					}
				}
			};
		}
	//大图滚动
	bigimgscroll();
	function bigimgscroll () {
		var main =document.getElementById('focus-main')
		var mnum = document.getElementById('m-num');
		var imgnav =getclass('m-num','imgnav');
		var numlis =imgnav[0].children;
		var mimgbox =document.getElementById('m-imgbox');
		var imglis =mimgbox.children;
		var mbotton =document.getElementById('m-botton');
		var ps =mbotton.children;
		var time1 = null;
		var time2 = null;
		var num = 0;
		function move(num) {
			clearInterval(time1);
			for (var i = 0; i < imglis.length; i++) {
				imglis[i].style.opacity = 0;
				numlis[i].style.backgroundColor = '#3e3e3e';
			}
			numlis[num].style.backgroundColor = '#b61b1f';
			var ind = 0;
			time1 =setInterval(function () {
				ind+=0.1;
				if (ind>=1) {
					ind=1;
					clearInterval(time1);
				}
				imglis[num].style.opacity = ind;
			},25)
		}

		function automove (){
			num++;
			if (num>=imglis.length) {
				num = 0
				move(num);
			};
			move(num);
		};
		time2 =setInterval(automove,2000);//进入页面执行
		for (var i = 0; i < numlis.length; i++) {
			numlis[i].index =i;
			numlis[i].onmouseover = function () {
				clearInterval(time2);
				num = this.index;//同步下标
				move(num);
			}
			numlis[i].onmouseout=function () {
				time2= setInterval(automove,2000);
			}
		};
		ps[0].onclick = function () {
			clearInterval(time2);
			num--;
			if (num<0) {
				num =imglis.length - 1;
			};
			move(num);
			time2 =setInterval(automove,2000);
		}
		ps[1].onclick = function () {
			clearInterval(time2);
			num++;
			if (num>=imglis.length) {
				num =0;
			};
			move(num);
			time2 =setInterval(automove,2000);
		}
		main.onmouseover=function () {
			ps[0].style.display='block'
			ps[1].style.display='block'
		}
		main.onmouseout=function () {
			ps[0].style.display=''
			ps[1].style.display=''
		}
	}
	//大图滚动面向对象
	$.fn.extend({
	imgRoll:function (){
		var $_this=$(this);
		var x=1;
		var anm=true;
		var n=0;
		var timer1=null;
		var imgW=$_this.find('.left-slider li').width();
		$_this.scrollLeft(imgW);//初始位置

		//第五步：复制插入节点
		var fir=$_this.find('.left-slider li:first').clone();
		var las=$_this.find('.left-slider li:last').clone();
		$_this.find('.left-slider').append(fir);
		$_this.find('.left-slider').prepend(las);
		
		//第一步：点击左
		$_this.find('.slider-left').click(function (){
			clearInterval(timer1);
			if (anm) {
				anm=false;
				x--;
				if (x<0) {
					x=$_this.find('.left-slider li').length-3;
					$_this.scrollLeft(imgW*(x+1));
				};
				n--;
				if (n<0) {
					n=$_this.find('.dian li').length-1;
				};
				move();
			};
			autoMove();
		});

		//第二步：点击右
		$_this.find('.slider-right').click(function (){
			clearInterval(timer1);
			if (anm) {
				anm=false;
				x++;
				if (x>=$_this.find('.left-slider li').length) {
					x=2;
					$_this.scrollLeft(imgW);
				};
				n++;
				if (n>=$_this.find('.dian li').length) {
					n=0;
				};
				move();
			};
			autoMove();
		});

		//第三步：点击数字
		$_this.find('.dian li').click(function (){
			clearInterval(timer1);
			n=$_this.find('.dian li').index(this);
			x=n+1;
			move();
			autoMove();
		})

		//第四步：自动走
		function autoMove(){
			timer1=setInterval(function (){
				x++;
				if (x>=$_this.find('.left-slider li').length) {
					x=2;
					$_this.scrollLeft(imgW);
				};
				n++;
				if (n>=$_this.find('.dian li').length) {
					n=0;
				};
				move();
			},2000)
		}
		autoMove();//进入页面执行

		//第六步：提取公用部分
		function move(){
			$_this.find('.dian li').eq(n).addClass('slider-selected').siblings().removeClass('slider-selected');
			$_this.stop().animate({scrollLeft:imgW*x},function (){
				anm=true;
			});
		}
	}
})
$(function (){
	$('#F1 .F-r-box').imgRoll();
	$('#F2 .F-r-box').imgRoll();
	$('#F3 .F-r-box').imgRoll();
	$('#F4 .F-r-box').imgRoll();
	$('#F5 .F-r-box').imgRoll();
	$('#F6 .F-r-box').imgRoll();
	$('#F7 .F-r-box').imgRoll();
	$('#F8 .F-r-box').imgRoll();
	$('#F9 .F-r-box').imgRoll();
	$('#F10 .F-r-box').imgRoll();

})
//生活服务
	lifes ()
	function lifes () {
		var lifes = document.getElementById('lifes');
		var lis =lifes.getElementsByTagName('li');
		// var cicons =lifes.getElementsByTagName('i');
		for (var i = 0; i<lis.length; i++) {
			lis[i].onmouseover =function () {
				for (var i = 0; i < lis.length; i++) {
					if (lis[i]==this) {
						var cicons =lis[i].getElementsByTagName('i')[0];
						var y=cicons.getAttribute("ind");
						cicons.style.backgroundPosition='-25px '+y+'px';
					};
				};
			}
			lis[i].onmouseout =function () {
				for (var i = 0; i < lis.length; i++) {
					if (lis[i]==this) {
						var cicons =lis[i].getElementsByTagName('i')[0];
						var y=cicons.getAttribute("ind");
						cicons.style.backgroundPosition='0 '+y+'px';
					};
				};
			}
		};
	}

	//今日推荐
	jrtj()
	function jrtj () {
		var bottonbox = document.getElementById('bottonbox');
		var simgbox = document.getElementById('simgbox');
		var outer = document.getElementById('outer');
		var outul =document.getElementById('outul');
		var boxlis = outer.getElementsByTagName('li');
		var left =bottonbox.children[0];
		var right =bottonbox.children[1];
		var time = null;
		var time1 = null;
		var time2 = null;
		simgbox.onmouseover=function () {
			bottonbox.style.display='block';
		}
		simgbox.onmouseout=function () {
			bottonbox.style.display='none';
		}
		outul.innerHTML+=outul.innerHTML
			function moveleft(){
				time =setInterval(function () {
					if (outer.scrollLeft<=0) {
						outer.scrollLeft = outul.offsetWidth/2;	
					}
					outer.scrollLeft-=10;
					if (outer.scrollLeft%boxlis[0].offsetWidth==0) {
						clearInterval(time)
					}
				},1)
				
			}
			function moveright(){
				time =setInterval(function () {
					if (outer.scrollLeft>=outul.offsetWidth/2) {
						outer.scrollLeft = 0;
					}
					outer.scrollLeft+=10;
					if (outer.scrollLeft%boxlis[0].offsetWidth==0) {
						clearInterval(time)
					}
				},1)
				
			}
			left.onclick=function(){
				clearInterval(time)
				moveleft()
			}
			right.onclick=function(){
				clearInterval(time)
				moveright()
			}
	}
//猜你喜欢
	$(function(){
		var x = 0;
		$('#guessyou .extra').click(function(){
			x++;
			if (x>$('#maban ul').length-1) {
				x=0;
			}
			$('#maban ul').eq(x).fadeIn().siblings().hide();
		})
//spacer
	$('#maban').mouseenter(function () {
		setTimeout(function () {
			$('.spacer i').stop().css({right:'1200px'});
			$('.spacer i').stop().animate({right:'0'},600);
		},500)
		return false;	
	})
	
	
//tab
	//原装JQ
	// $(function(){
	// 	$('.tab .tab-item').mouseover(function(){
	// 		// alert(1)
	// 		var i=$(this).index();
	// 		// alert(i)
	// 		$('.tab .tab-item').find('a').each(function(x){
	// 			$('.tab .tab-item').eq(x).find('a').removeClass('select');
	// 		})
	// 		$('.tab .tab-item').eq(i).find('a').addClass('select');
	// 		$('#center .main').eq(i).addClass('block').siblings().removeClass('block');
	// 	})
	// })

	// 封装tab JQ
	function tab(item,con,i) {
		$(item).find('a').each(function(x){
			$(item).eq(x).find('a').removeClass('select');
		})
		$(item).eq(i).find('a').addClass('select');
		$(con).eq(i).addClass('block').siblings().removeClass('block');

	}
	//调用1F
	$('#F1 .tab .tab-item').mouseover(function(){
		var i=$(this).index();
		tab('#F1 .tab .tab-item','#F1 .main',i);
	})
	//调用2F
	$('#F2 .tab .tab-item').mouseover(function(){
		var i=$(this).index();
		tab('#F2 .tab .tab-item','#F2 .F-right',i);
	})
	//调用3F
	$('#F3 .tab .tab-item').mouseover(function(){
		var i=$(this).index();
		tab('#F3 .tab .tab-item','#F3 .F-right',i);
	})
	//调用4F
	$('#F4 .tab .tab-item').mouseover(function(){
		var i=$(this).index();
		tab('#F4 .tab .tab-item','#F4 .F-right',i);
	})
	//调用5F
	$('#F5 .tab .tab-item').mouseover(function(){
		var i=$(this).index();
		tab('#F5 .tab .tab-item','#F5 .F-right',i);
	})
	//调用6F
	$('#F6 .tab .tab-item').mouseover(function(){
		var i=$(this).index();
		tab('#F6 .tab .tab-item','#F6 .F-right',i);
	})
	//调用7F
	$('#F7 .tab .tab-item').mouseover(function(){
		var i=$(this).index();
		tab('#F7 .tab .tab-item','#F7 .F-right',i);
	})
	//调用8F
	$('#F8 .tab .tab-item').mouseover(function(){
		var i=$(this).index();
		tab('#F8 .tab .tab-item','#F8 .F-right',i);
	})
	//调用9F
	$('#F9 .tab .tab-item').mouseover(function(){
		var i=$(this).index();
		tab('#F9 .tab .tab-item','#F9 .F-right',i);
	})
	//调用10F
	$('#F10 .tab .tab-item').mouseover(function(){
		var i=$(this).index();
		tab('#F10 .tab .tab-item','#F10 .F-right',i);
	})				
		
	//滚动条
	if ($(window).scrollTop()>=($('#F1').offset().top-$('#F1').height())&&($(window).scrollTop()<($('#F11').offset().top+$('#F11').height()))) {
		$('#Stairsfix').show();
	};
	$(window).scroll(function(){
		// console.log($(window).scrollTop())
    	if($(window).scrollTop()>=($('#F1').offset().top-$('#F1').height())&&($(window).scrollTop()<($('#F11').offset().top+$('#F11').height()))){
    		$('#Stairsfix').show();
 		}else{
 			$('#Stairsfix').hide();
 		}
	})
	//楼层点击
	$('#Stairsfix li').click(function () {
		var i = $(this).index();
		$('#Stairsfix li').find('a').each(function(x){
			$('#Stairsfix li').eq(x).find('.handler').show();
			$('#Stairsfix li').eq(x).find('.handler').removeClass('etitle-red');
		})
		$('#Stairsfix li').eq(i).find('.handler').hide();
		$('#Stairsfix li').eq(i).find('.etitle').addClass('etitle-red')
		$('body').animate({scrollTop:$('#F'+(i+1)).offset().top})

	})


	// 今日抄底left
	$('#c-left .mc li').mouseover(function () {
		var i = $(this).index();
		$('#c-left .mc li ').eq(i).find('img').stop().animate({left:'-6%'});
	})
	$('#c-left .mc li').mouseout(function () {
		var i = $(this).index();
		$('#c-left .mc li ').eq(i).find('img').stop().animate({left:''});
	})
	// 今日抄底晒单
	$(function () {
		var time = null;
		var lih = $('#c-right .sd li').height()+20;
		var las1=$('#c-right .sd li:last').clone();
		var las2=$('#c-right .sd li').eq($('#c-right .sd li').length-2).clone();
		$('#c-right .sd ul').prepend(las1);
		$('#c-right .sd ul').prepend(las2);
		var i = $('#c-right .sd li').length-2;
		$('#c-right .sd').scrollTop($('#c-right .sd ul').height()-$('#c-right .sd').height())
		time = setInterval(function () {
			i--;
			// console.log(i)
			if (i<0) {
				i=$('#c-right .sd li').length-3;
				$('#c-right .sd').scrollTop(lih*(i+1))
			}
			$('#c-right .sd').animate({scrollTop:lih*i})
		},2000)
		
	})
	
























	});

}
	