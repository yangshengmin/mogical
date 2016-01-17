!doctype html

html

head

script src={path template}jsjquery.jsscript

script src={path template}jsjquery-1.8.0.min.jsscript

script src={path template}jsjquery.jslides.jsscript

meta charset=utf-8

meta name=description content={print webinfo('web_description')}

meta name=keywords content={print webinfo('web_keywords')}

title{if webinfo('web_index_name')}{print webinfo('web_index_name')}{else}{print webinfo('web_name')}{if}title

link href={path template}cssreset.css rel=stylesheet type=textcss

link href={path template}cssstyle.css rel=stylesheet type=textcss

script type=textjavascript

function MM_preloadImages() { v3.0

  var d=document; if(d.images){ if(!d.MM_p) d.MM_p=new Array();

    var i,j=d.MM_p.length,a=MM_preloadImages.arguments; for(i=0; ia.length; i++)

    if (a[i].indexOf(#)!=0){ d.MM_p[j]=new Image; d.MM_p[j++].src=a[i];}}

}



function MM_swapImgRestore() { v3.0

  var i,x,a=document.MM_sr; for(i=0;a&&ia.length&&(x=a[i])&&x.oSrc;i++) x.src=x.oSrc;

}



function MM_findObj(n, d) { v4.01

  var p,i,x;  if(!d) d=document; if((p=n.indexOf())0&&parent.frames.length) {

    d=parent.frames[n.substring(p+1)].document; n=n.substring(0,p);}

  if(!(x=d[n])&&d.all) x=d.all[n]; for (i=0;!x&&id.forms.length;i++) x=d.forms[i][n];

  for(i=0;!x&&d.layers&&id.layers.length;i++) x=MM_findObj(n,d.layers[i].document);

  if(!x && d.getElementById) x=d.getElementById(n); return x;

}



function MM_swapImage() { v3.0

  var i,j=0,x,a=MM_swapImage.arguments; document.MM_sr=new Array; for(i=0;i(a.length-2);i+=3)

   if ((x=MM_findObj(a[i]))!=null){document.MM_sr[j++]=x; if(!x.oSrc) x.oSrc=x.src; x.src=a[i+2];}

}

script

head



body onLoad=MM_preloadImages('imagesbus.png','imagesbox1.png')



{include header}



!--通知--

div class=announce

	div class=time

		div id=localtime

        script type=textjavascript

			function showLocale(objD)

			{

			var str,colorhead,colorfoot;

			var yy = objD.getYear();

			if(yy1900) yy = yy+1900;

			var MM = objD.getMonth()+1;

			if(MM10) MM = '0' + MM;

			var dd = objD.getDate();

			if(dd10) dd = '0' + dd;

			var hh = objD.getHours();

			if(hh10) hh = '0' + hh;

			var mm = objD.getMinutes();

			if(mm10) mm = '0' + mm;

			var ss = objD.getSeconds();

			if(ss10) ss = '0' + ss;

			var ww = objD.getDay();

			if  ( ww==0 )  colorhead=font color=#666666;

			if  ( ww  0 && ww  6 )  colorhead=font color=#666666;

			if  ( ww==6 )  colorhead=font color=#666666;

			if  (ww==0)  ww=星期日;

			if  (ww==1)  ww=星期一;

			if  (ww==2)  ww=星期二;

			if  (ww==3)  ww=星期三;

			if  (ww==4)  ww=星期四;

			if  (ww==5)  ww=星期五;

			if  (ww==6)  ww=星期六;

			colorfoot=font

			str = colorhead + yy + - + MM + - + dd +   + hh +  + mm +  + ss +    + ww + colorfoot;

			return(str);

}

			function tick()

{

			var today;

			today = new Date();

			document.getElementById(localtime).innerHTML = showLocale(today);

			window.setTimeout(tick(), 1000);

}

		tick();

		script

        div

!--代码结束--

		

        div class=phone24小时服务热线：0574-82829090div

    div

    !--搜索框--

	div class=search

	form name=form1 action={path search} 

     	input type=text name=key id=key class=input1 value=请输入关键词 onFocus=if(this.value=='请输入关键词'){this.value='';} onBlur=if(this.value==''){this.value='请输入关键词'}

     	input type=submit class=input2 value=

		input type=hidden value={print get_web_param('lang')} name=lang 

		form

	div

div



!--内容--

div class=content



!--banner--

div class=banner

    div id=full-screen-slider

         ul id=slides

         

		 {loop source=get_flash($tpl_id=2,$order=desc)}

           li style=backgroundurl({print $v['pic']}) no-repeat center topli



		 {loop} 

      ul

     div

div



!--新闻中心--

div class=news

     div class=title

          p后勤新闻p

     div

	{assign source=get_tpl_cate_content($tpl_id='40',$limit='0,7',$order_type='id',$filter='',$pic='no',$order='desc',$lang='') name=index_news}

	{loop source=$index_news['contents']}

	div class=artile

          dl class=one

              dt class=spotspanspandt

              dd class=worda href={print $v['url']}

              	  span class=left-one{print cn_substr($v['title'],50)}span

                  span class=right-one{print date('Y.m.d',$v['updatetime'])}span

              add

          dl

     div

    {loop}

div



!--公告--

div class=container  

    ul class=tabs  

        li class=activea href=#tab1通知ali  

        lia href=#tab4公告栏ali  

    ul  

    div class=tab_container  

        div id=tab1 class=tab_content style=display block;   

		{assign source=get_tpl_cate_content($tpl_id='100',$limit='0,7',$order_type='id',$filter='',$pic='no',$order='desc',$lang='') name=index_news}

		{loop source=$index_news['contents']}

        div class=notice

             div class=left

                  spanspan

             div

             div class=right

                  a href={print $v['url']}

                  	div class=left-box{print cn_substr($v['title'],30)}div

				  	div class=right-box【{print date('Y.m.d',$v['updatetime'])}】div

                  a

             div

        div

         {loop}    

        div  

        div id=tab4 class=tab_content style=display none;  

		{assign source=get_tpl_cate_content($tpl_id='110',$limit='0,7',$order_type='id',$filter='',$pic='no',$order='desc',$lang='') name=index_news}

		{loop source=$index_news['contents']}

           div class=notice

             div class=left

                  spanspan

             div

             div class=right

                  a href={print $v['url']}

                  	div class=left-box{print cn_substr($v['title'],20)}div

				  	div class=right-box【{print date('Y.m.d',$v['updatetime'])}】div

                  a

             div

        div   

	      {loop}  

        div  

    div  

  

div  



script type=textjavascript  

  

$(document).ready(function() {  

  

    Default Action  

    $(.tab_content).hide(); Hide all content  

    $(ul.tabs lifirst).addClass(active).show(); Activate first tab  

    $(.tab_contentfirst).show(); Show first tab content  

      

    On Click Event  

    $(ul.tabs li).click(function() {  

        $(ul.tabs li).removeClass(active); Remove any active class  

        $(this).addClass(active); Add active class to selected tab  

        $(.tab_content).hide(); Hide all tab content  

        var activeTab = $(this).find(a).attr(href); Find the rel attribute value to identify the active tab + content  

        $(activeTab).show(); Fade in the active content  

        return false;  

    });  

  

});  

script  

!--代码部分end--



!--服务大厅--

div class=service

     div class=title2

          p服务大厅p

     div

     div class=icon

          dl class=guide

              dta href={path }alonealone.phpid=51adt

              dda href={path }alonealone.phpid=51服务指南add

          dl

          dl class=make

              dta href={path }alonealone.phpid=51adt

              dda href={path }alonealone.phpid=51服务定制add

          dl

          dl class=message

              dta href={path }alonealone.phpid=52adt

              dda href={path }alonealone.phpid=52实用信息add

          dl

          dl class=electric

              dta href={path }alonealone.phpid=54adt

              dda href={path }alonealone.phpid=54水电维修add

          dl

          dl class=canteen

              dta href={path }alonealone.phpid=56adt

              dda href={path }alonealone.phpid=56餐厅概况add

          dl

          dl class=telephone

              dta href={path }alonealone.phpid=55adt

              dda href={path }alonealone.phpid=55值班电话add

          dl

          dl class=life

              dta href={path }alonealone.phpid=56adt

              dda href={path }alonealone.phpid=56生活锦囊add

          dl

          dl class=question

              dta href={path }alonealone.phpid=57adt

              dda href={path }alonealone.phpid=57常见问题add

          dl

     div

div



!--帮帮团--

div class=help

 	 div class=title3

          p万里帮帮团p

     div

     div class=choose

     	  dl class=choose-warp

              dd class=losta href=失物招领.htmladd

              dd class=carda href=add

              dd class=mapa href=add

			  dd class=maila href=后勤信箱.htmladd

              dd class=linka href=add

              dd class=shopa href=add

          dl

     div

div



!--后勤简报--

div class=shortnews

	 div class=title4

     	  p后勤简报p

          a href=更多a

     div

     div class=newsport

	 {assign source=get_tpl_cate_content($tpl_id='43',$limit='0,7',$order_type='id',$filter='',$pic='',$order='desc',$lang='') name=index_news}

	 {loop source=$index_news['contents']}

          div class=port1

          	   a href=

               	  div class=arrowdiv

                  div class=contant{print cn_substr($v['title'],40)}div

                  div class=date{print date('Y.m.d',$v['updatetime'])}div

               a

          div

      {loop}  

     div

div



!--万里后勤系统--

div class=system

	 div class=title5万里后勤OA系统div

     div class=login

     	  div class=passort

          	p用户名：p

          	input type=text class=input3

          div

          div class=code

          	p密 &nbsp;&nbsp;码：p

            input type=password class=input4

          div

          div class=sumbit

            input type=submit value=登录 class=input5

            input type=submit value=重置 class=input6

          div

     div

div



!--图片新闻--

div class=picture

	 div class=title6

     	  p图片新闻p

     div

	 div class=subbox

     	  div id=list class= picutre_many 

        table cellspacing=0 cellpadding=0 style=width 940px; border 0px;

            tr

                td id=list1

                    table style=border 0px; cellpadding=0 cellspacing=0

                        tr id=pic

			{assign source=get_tpl_cate_content($tpl_id='41,42',$limit='0,15',$order_type='id',$filter='',$pic='yes',$order='desc',$lang='') name=pr}

			{loop source=$pr['contents']}

                            tda href={print $v['url']}img src={print $v['thumb_pic']} 

                            	p{print cn_substr($v['title'],40)}p

                            atd

                        {loop}  

                        tr

                    table

                td

                td id=list2td

            tr

        table

    div

    script type=textjavascript

        图片滚动效果

        var speedpic = 20;速度数值越大速度越慢

        document.getElementById(list2).innerHTML = document.getElementById(list1).innerHTML;

        function Marqueepic() {

            if (document.getElementById(list2).offsetWidth

                    - document.getElementById(list).scrollLeft = 0) {

                document.getElementById(list).scrollLeft -= document

                        .getElementById(list1).offsetWidth;

            } else {

                document.getElementById(list).scrollLeft++;

            }

        }

        var MyMarpic = setInterval(Marqueepic, speedpic);



        document.getElementById(list).onmouseover = function() {

            clearInterval(MyMarpic);

        }

        document.getElementById(list).onmouseout = function() {

            MyMarpic = setInterval(Marqueepic, speedpic);

        }

    script

    !--代码结束--

     div

div



!--友情链接--

div class=linkin

	 div class=title7

     	  p友情链接p

     div

     div class=show

     	  div class=show-box

              ul

              {assign source=get_tpl_cate_content($tpl_id='300',$limit='0,8',$order_type='id',$filter='',$pic='yes',$order='asc',$lang='') name=index_news}

              {loop source=$index_news['contents']}

              {if $v['thumb_pic']}

                lia href={print $v['linkadd']}

 target=_blank  onMouseOver=MM_swapImage('Image{print $v['autoindex']}','','{print $v['thumb_pic']}','Image{print $v['autoindex']}','','{path }upload{print $v['tp2']}',1) onMouseOut=MM_swapImgRestore()img id=Image{print $v['autoindex']} src={print $v['thumb_pic']} alt= width=34 height=32 span{print $v['title']}spanali

              {if}

              {loop}

              ul

          div

     div

  div



 div



{include footer}

body

html
