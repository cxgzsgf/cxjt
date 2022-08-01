
--程序启动时会执行的事件
--渐变色主题控制

[远程代码]
import "android.graphics.drawable.GradientDrawable"
function 渐变(left_jb,right_jb,id)
  drawable = GradientDrawable(GradientDrawable.Orientation.TR_BL,{
    right_jb,--右色
    left_jb,--左色
  });
  id.setBackgroundDrawable(drawable)
end
-- -----------调用渐变函数
渐变(0xff020100,0xff666666,toolbarParent)
--By: 银弹GCell
--修改顶栏字体颜色
--先删除Fapp里的顶栏标题
titleTvw=loadlayout{
  TextView,
  textSize="18sp",
  textColor="#FFFFFFFF",
  text="",
}
toolbar.addView(titleTvw,1)
--由小六制作整合
function CircleButton(view,InsideColor,radiu)
  import "android.graphics.drawable.GradientDrawable"
  drawable = GradientDrawable() 
  drawable.setShape(GradientDrawable.RECTANGLE) 
  drawable.setColor(InsideColor)
  drawable.setCornerRadii({radiu,radiu,radiu,radiu,radiu,radiu,radiu,radiu});
  view.setBackgroundDrawable(drawable)
end
角度=30
控件id=sidebar
控件颜色=0xFFFFFFFF
CircleButton(控件id,控件颜色,角度)

flt=sidebar.getLayoutParams( )
flt.setMargins(200, 225, 800, 360)
sidebar.setLayoutParams(flt)

--程序启动会执行的事件
require "chl"
require "dlbj"

import "global_string"--圆角对话框
if(activity.getApplicationContext().getSystemService(Context.CONNECTIVITY_SERVICE).getActiveNetworkInfo() == nil) then
  local u=AlertDialog.Builder(this)
  .setCancelable(false)
  u.setTitle("你没有网络哦→_→")
  u.setPositiveButton("退出软件",function()
    退出程序()
  end)
  u.setNegativeButton("",function()
  end)
  u.setNeutralButton("",function()--中立按钮
  end)
  u.setMessage([[世界上最痛苦的事情莫过于没有网络😂😂😂
  -来自互联网]])
  u=u.show()
  --      u.setView(loadlayout(输入对话框))--布局ID
  setDialogButtonColor(u,0,0xFF00B3FF)
  圆角(u.getWindow(),0xFFFAFAFA,{30,30,30,30,30,30,30,30})
end


--activity进入动画
activity.overridePendingTransition(android.R.anim.slide_in_left,android.R.anim.fade_out)
import "android.content.Intent"--导入包
import "android.view.animation.*"
import "android.view.animation.TranslateAnimation"
import "android.view.animation.Animation"
import "android.view.animation.LayoutAnimationController"
import "android.view.animation.AnimationSet"
import "android.view.animation.AlphaAnimation"




Http.get("http://blog.guaqb.cn/tool/toux/api.php?qq=1509377931",nil,nil,nil,function(code,content)
  mingc=content:match('<br/ >昵称：(.-)<br/>')
  toux=content:match('<img src="(.-)">')
  qqh=content:match('QQ号：(.-)<br')

  Http.get("http://www.iyuji.cn/iyuji/s/dEVqcjR4bTRxbmJOc2dVU3hKWUFwUT09/1583110189275773",nil,nil,nil,function(code,content)
    --过滤网页
    content=content:gsub('<br>',"") or content;
    content=content:gsub('</p>',"") or content;
    content=content:gsub('</div>',"") or content;
    content=content:gsub('&nbsp;',"") or content;
    content=content:gsub('<div id(.-)#555555;">',"") or content;
    content=content:gsub('<p dir(.-)#555555;">',"") or content;
    解析一图标=content:match("【解析一图标】(.-)【解析一图标】")
    解析一文字=content:match("【解析一文字】(.-)【解析一文字】")
    解析网址一=content:match("【解析网址一】(.-)【解析网址一】")

    解析二图标=content:match("【解析二图标】(.-)【解析二图标】")
    解析二文字=content:match("【解析二文字】(.-)【解析二文字】")
    解析网址二=content:match("【解析网址二】(.-)【解析网址二】")

    解析三图标=content:match("【解析三图标】(.-)【解析三图标】")
    解析三文字=content:match("【解析三文字】(.-)【解析三文字】")
    解析网址三=content:match("【解析网址三】(.-)【解析网址三】")

    解析四图标=content:match("【解析四图标】(.-)【解析四图标】")
    解析四文字=content:match("【解析四文字】(.-)【解析四文字】")
    解析网址四=content:match("【解析网址四】(.-)【解析网址四】")

    解析五图标=content:match("【解析五图标】(.-)【解析五图标】")
    解析五文字=content:match("【解析五文字】(.-)【解析五文字】")
    解析网址五=content:match("【解析网址五】(.-)【解析网址五】")

    解析六图标=content:match("【解析六图标】(.-)【解析六图标】")
    解析六文字=content:match("【解析六文字】(.-)【解析六文字】")
    解析网址六=content:match("【解析网址六】(.-)【解析网址六】")

    解析七图标=content:match("【解析七图标】(.-)【解析七图标】")
    解析七文字=content:match("【解析七文字】(.-)【解析七文字】")
    解析网址七=content:match("【解析网址七】(.-)【解析网址七】")

    解析八图标=content:match("【解析八图标】(.-)【解析八图标】")
    解析八文字=content:match("【解析八文字】(.-)【解析八文字】")
    解析网址八=content:match("【解析网址八】(.-)【解析网址八】")

    解析九图标=content:match("【解析九图标】(.-)【解析九图标】")
    解析九文字=content:match("【解析九文字】(.-)【解析九文字】")
    解析网址九=content:match("【解析网址九】(.-)【解析网址九】")

    解析十图标=content:match("【解析十图标】(.-)【解析十图标】")
    解析十文字=content:match("【解析十文字】(.-)【解析十文字】")
    解析网址十=content:match("【解析网址十】(.-)【解析网址十】")

    一展图=content:match("【一展图】(.-)【一展图】")
    网站一=content:match("【网站一】(.-)【网站一】") 
    一展名=content:match("【一展名】(.-)【一展名】")
    二展图=content:match("【二展图】(.-)【二展图】")
    网站二=content:match("【网站二】(.-)【网站二】")
    二展名=content:match("【二展名】(.-)【二展名】")
    三展图=content:match("【三展图】(.-)【三展图】")
    网站三=content:match("【网站三】(.-)【网站三】")
    三展名=content:match("【三展名】(.-)【三展名】")
    四展图=content:match("【四展图】(.-)【四展图】")
    网站四=content:match("【网站四】(.-)【网站四】")
    四展名=content:match("【四展名】(.-)【四展名】")
    五展图=content:match("【五展图】(.-)【五展图】")
    网站五=content:match("【网站五】(.-)【网站五】")
    五展名=content:match("【五展名】(.-)【五展名】")
    六展图=content:match("【六展图】(.-)【六展图】")
    网站六=content:match("【网站六】(.-)【网站六】")
    六展名=content:match("【六展名】(.-)【六展名】")
    公告=content:match("【公告内容】(.-)【公告内容】")
    背景图=content:match("【背景图】(.-)【背景图】")
    QQ等级1=content:match("【QQ等级1】(.-)【QQ等级1】")
    QQ等级2=content:match("【QQ等级2】(.-)【QQ等级2】")
    QQ等级3=content:match("【QQ等级3】(.-)【QQ等级3】")
    QQ等级4=content:match("【QQ等级4】(.-)【QQ等级4】")
    QQ等级5=content:match("【QQ等级5】(.-)【QQ等级5】")
    QQ等级6=content:match("【QQ等级6】(.-)【QQ等级6】")
    QQ等级7=content:match("【QQ等级7】(.-)【QQ等级7】")
    QQ等级8=content:match("【QQ等级8】(.-)【QQ等级8】")
    QQ等级9=content:match("【QQ等级9】(.-)【QQ等级9】")

    --低栏布局支持布局
    shamrock=
    {
      LinearLayout;
      orientation="vertical";
      layout_width="fill";
      layout_height="fill";
      background=背景图; 
      {
        PageView;
        layout_height="-2";
        layout_width="-1";
        layout_weight="1.0";
        id="under";
        pages={
          --第一页的布局开始
          {

            LinearLayout;
            id="dhjz";
            orientation='vertical';--重力属性
            layout_width='fill';--布局宽度
            layout_height='fill';--布局高度
            {
              ScrollView,--纵向滚动
              layout_width='fill';--宽
              layout_height='fill';--高
              verticalScrollBarEnabled=false;--隐藏纵向滚动条
              {
                LinearLayout,
                orientation="vertical",
                id="mainlay",
                {
                  TextView,
                  text="早上好",
                  layout_margin="7.5%w",
                  layout_marginTop="4.5%h",
                  layout_marginBottom="5%w",
                  layout_width="fill",
                  layout_height="wrap",
                  textSize="31sp",
                  layout_gravity="center|left",
                },
                {
                  TextView,
                  text="欢迎使用 小狗恢复包刷入模式\n正在获取一言...",
                  layout_marginLeft="7.5%w",
                  layout_marginRight="7.5%w",
                  layout_width="fill",
                  textSize="18sp",
                  onTouchListener=点击监听,
                  onClick=function ()
                    print("长按可以复制一言哦✺◟(∗❛ัᴗ❛ั∗)◞✺")

                  end,
                  layout_height="wrap",
                  layout_gravity="center|left",
                  layout_marginBottom="20%h",
                },

                {
                  LinearLayout;
                  layout_height='fill';
                  layout_width='100%w';
                  Orientation='horizontal';
                  gravity='center';--重力属性      
                  {
                    CardView;
                    layout_height='95dp';
                    layout_width='41%w';
                    Elevation='6dp';
                    id="an";
                    onTouchListener=点击监听;
                    cardBackgroundColor='#ff90c4e3';
                    layout_margin='18dp';
                    Radius='18dp';

                    {
                      ImageView;--图片控件
                      layout_width='fill';--图片宽度
                      layout_height='fill';--图片高度
                      scaleType='fitXY';
                      ColorFilter='#ff4e92d5';--图片滤色器 --这是个很神奇的属性
                      src='tubiao/4.png';
                    },
                    {
                      ImageView;
                      layout_width='3%h';
                      ColorFilter='#ffa7a7a7';
                      src='tubiao/ys.png';
                      layout_marginTop='12dp';
                      layout_marginRight='5%w';
                      ColorFilter='#ffffffff';
                      layout_gravity="right";
                      layout_height='3%h';
                      scaleType='fitXY';
                    },
                    {--文字
                      TextView;
                      textSize='18sp';
                      layout_height='wrap_content';
                      layout_width='match_parent';
                      textColor="#ffffffff";
                      layout_gravity="bottom";
                      layout_marginLeft='8%w';
                      layout_marginBottom="5%w";
                      text='自动安装';
                      textStyle="bold";
                    },
                  },
                  {
                    CardView;
                    layout_height='95dp';
                    layout_width='41%w';
                    Elevation='6dp';
                    id="an2";
                    onTouchListener=点击监听;
                    cardBackgroundColor='#ff8f98ff';
                    layout_margin='18dp';
                    Radius='18dp';
                    {
                      ImageView;--图片控件
                      layout_width='fill';--图片宽度
                      layout_height='fill';--图片高度
                      scaleType='fitXY';
                      ColorFilter='#FF172A88';--图片滤色器
                      src='tubiao/5.png';
                    },
                    {
                      ImageView;
                      layout_width='3%h';
                      ColorFilter='#ffa7a7a7';
                      src='tubiao/ys.png';
                      layout_marginTop='12dp';
                      layout_marginRight='5%w';
                      ColorFilter='#ffffffff'; --滤色器 可以给卡片内右上角图片替换颜色
                      layout_gravity="right";
                      layout_height='3%h';
                      scaleType='fitXY';
                    },
                    {
                      TextView;
                      textSize='18sp';
                      layout_height='wrap_content';
                      layout_width='match_parent';
                      textColor="#ffffffff";
                      layout_gravity="bottom";
                      layout_marginLeft='8%w';
                      layout_marginBottom="5%w";
                      text='手动下载';
                      textStyle="bold";
                    },
                  },
                },
                --第二排卡片
                {
                  LinearLayout;
                  layout_height='fill';
                  layout_width='100%w';
                  Orientation='horizontal';
                  gravity='center';--重力属性      
                  {
                    CardView;
                    layout_height='95dp';
                    layout_width='41%w';
                    id="an3";
                    onTouchListener=点击监听;
                    Elevation='6dp';
                    cardBackgroundColor='#ffff8574';
                    layout_margin='18dp';
                    Radius='18dp';

                    {
                      ImageView;--图片控件
                      layout_width='fill';--图片宽度
                      layout_height='fill';--图片高度
                      scaleType='fitXY';
                      ColorFilter='#ffffa874';--图片滤色器
                      src='tubiao/6.png';
                    },
                    {
                      ImageView;
                      layout_width='3%h';
                      ColorFilter='#ffa7a7a7';
                      src='tubiao/ys.png';
                      layout_marginTop='12dp';
                      layout_marginRight='5%w';
                      ColorFilter='#ffffffff';
                      layout_gravity="right";
                      layout_height='3%h';
                      scaleType='fitXY';
                    },
                    {
                      TextView;
                      textSize='18sp';
                      layout_height='wrap_content';
                      layout_width='match_parent';
                      textColor="#ffffffff";
                      layout_gravity="bottom";
                      layout_marginLeft='8%w';
                      layout_marginBottom="5%w";
                      text='解压文件';
                      textStyle="bold";
                    },
                  },
                  {
                    CardView;
                    layout_height='95dp';
                    layout_width='41%w';
                    Elevation='6dp';
                    id="an4";
                    onTouchListener=点击监听;
                    cardBackgroundColor='#ffffa2ae';
                    layout_margin='18dp';
                    Radius='18dp';

                    {
                      ImageView;--图片控件
                      layout_width='fill';--图片宽度
                      layout_height='fill';--图片高度
                      ColorFilter='#ffff8b8b';--图片滤色器
                      scaleType='fitXY';
                      src='tubiao/7.png';
                    },
                    {
                      ImageView;
                      layout_width='3%h';
                      ColorFilter='#ffa7a7a7';
                      src='tubiao/ys.png';
                      layout_marginTop='12dp';
                      layout_marginRight='5%w';
                      ColorFilter='#ffffffff';
                      layout_gravity="right";
                      layout_height='3%h';
                      scaleType='fitXY';
                    },
                    {
                      TextView;
                      textSize='18sp';
                      layout_height='wrap_content';
                      layout_width='match_parent';
                      textColor="#ffffffff";
                      layout_gravity="bottom";
                      layout_marginLeft='8%w';
                      layout_marginBottom="5%w";
                      text='校验文件';
                      textStyle="bold";
                    },
                  },

                },

                {
                  LinearLayout;
                  layout_height='fill';
                  layout_width='100%w';
                  Orientation='horizontal';
                  gravity='center';--重力属性      
                  {
                    CardView;
                    layout_height='95dp';
                    layout_width='41%w';
                    Elevation='6dp';
                    id="xs1";
                    onTouchListener=点击监听;
                    cardBackgroundColor='#758a99';
                    layout_margin='18dp';
                    Radius='18dp';

                    {
                      ImageView;--图片控件
                      layout_width='fill';--图片宽度
                      layout_height='fill';--图片高度
                      scaleType='fitXY';
                      ColorFilter='#50616d';--图片滤色器 --这是个很神奇的属性
                      src='tubiao/4.png';
                    },
                    {
                      ImageView;
                      layout_width='3%h';
                      ColorFilter='#ffa7a7a7';
                      src='tubiao/ys.png';
                      layout_marginTop='12dp';
                      layout_marginRight='5%w';
                      ColorFilter='#ffffffff';
                      layout_gravity="right";
                      layout_height='3%h';
                      scaleType='fitXY';
                    },
                    {--文字
                      TextView;
                      textSize='18sp';
                      layout_height='wrap_content';
                      layout_width='match_parent';
                      textColor="#ffffffff";
                      layout_gravity="bottom";
                      layout_marginLeft='8%w';
                      layout_marginBottom="5%w";
                      text='安装文件';
                      textStyle="bold";
                    },
                  },
                  {
                    CardView;
                    layout_height='95dp';
                    layout_width='41%w';
                    Elevation='6dp';
                    id="mh1";
                    onTouchListener=点击监听;
                    cardBackgroundColor='#fa8c35';
                    layout_margin='18dp';
                    Radius='18dp';
                    {
                      ImageView;--图片控件
                      layout_width='fill';--图片宽度
                      layout_height='fill';--图片高度
                      scaleType='fitXY';
                      ColorFilter='#ffa400';--图片滤色器
                      src='tubiao/5.png';
                    },
                    {
                      ImageView;
                      layout_width='3%h';
                      ColorFilter='#ffa7a7a7';
                      src='tubiao/ys.png';
                      layout_marginTop='12dp';
                      layout_marginRight='5%w';
                      ColorFilter='#ffffffff'; --滤色器 可以给卡片内右上角图片替换颜色
                      layout_gravity="right";
                      layout_height='3%h';
                      scaleType='fitXY';
                    },
                    {
                      TextView;
                      textSize='18sp';
                      layout_height='wrap_content';
                      layout_width='match_parent';
                      textColor="#ffffffff";
                      layout_gravity="bottom";
                      layout_marginLeft='8%w';
                      layout_marginBottom="5%w";
                      text='修复安装';
                      textStyle="bold";
                    },
                  },
                },
                --第三排卡片
                {
                  LinearLayout;
                  layout_height='fill';
                  layout_width='100%w';
                  Orientation='horizontal';
                  gravity='center';--重力属性      
                  {
                    CardView;
                    layout_height='95dp';
                    layout_width='41%w';
                    id="an5";
                    onTouchListener=点击监听;
                    Elevation='6dp';
                    cardBackgroundColor='#ff82ccc2';
                    layout_margin='18dp';
                    Radius='18dp';

                    {
                      ImageView;--图片控件
                      layout_width='fill';--图片宽度
                      layout_height='fill';--图片高度
                      scaleType='fitXY';
                      ColorFilter='#ff00cc99';--图片滤色器 可以给卡片内右上角图片替换颜色
                      src='tubiao/6.png';
                    },
                    {
                      ImageView;
                      layout_width='3%h';
                      ColorFilter='#ffa7a7a7';
                      src='tubiao/yige.png';
                      layout_marginTop='12dp';
                      layout_marginRight='5%w';
                      ColorFilter='#ffffffff';
                      layout_gravity="right";
                      layout_height='3%h';
                      scaleType='fitXY';
                    },
                    {
                      TextView;
                      textSize='18sp';
                      layout_height='wrap_content';
                      layout_width='match_parent';
                      textColor="#ffffffff";
                      layout_gravity="bottom";
                      layout_marginLeft='8%w';
                      layout_marginBottom="5%w";
                      text='敬请期待';
                      textStyle="bold";
                    },
                  },
                  {
                    CardView;
                    layout_height='95dp';
                    layout_width='41%w';
                    Elevation='6dp';
                    id="an6";
                    onTouchListener=点击监听;
                    cardBackgroundColor='#ffffc278';
                    layout_margin='18dp';
                    Radius='18dp';

                    {
                      ImageView;--图片控件
                      layout_width='fill';--图片宽度
                      layout_height='fill';--图片高度
                      ColorFilter='#ffff7648';--图片滤色器
                      scaleType='fitXY';
                      src='tubiao/7.png';
                    },
                    {
                      ImageView;
                      layout_width='3%h';
                      ColorFilter='#ffa7a7a7';
                      src='tubiao/baidu.png';
                      layout_marginTop='12dp';
                      layout_marginRight='5%w';
                      ColorFilter='#ffffffff';
                      layout_gravity="right";
                      layout_height='3%h';
                      scaleType='fitXY';
                    },
                    {
                      TextView;
                      textSize='18sp';
                      layout_height='wrap_content';
                      layout_width='match_parent';
                      textColor="#ffffffff";
                      layout_gravity="bottom";
                      layout_marginLeft='8%w';
                      layout_marginBottom="5%w";
                      text='敬请期待';
                      textStyle="bold";
                    },
                  },
                },

                --第四排卡片
                {
                  LinearLayout;
                  layout_height='fill';
                  layout_width='100%w';
                  Orientation='horizontal';
                  gravity='center';--重力属性      
                  {
                    CardView;
                    layout_height='95dp';
                    layout_width='41%w';
                    Elevation='6dp';
                    id="an7";
                    onTouchListener=点击监听;
                    cardBackgroundColor='#ff94b3e8';
                    layout_margin='18dp';
                    Radius='18dp';

                    {
                      ImageView;--图片控件
                      layout_width='fill';--图片宽度
                      layout_height='fill';--图片高度
                      scaleType='fitXY';
                      ColorFilter='#ff8e98df';--图片滤色器 --这是个很神奇的属性
                      src='tubiao/4.png';
                    },
                    {
                      ImageView;
                      layout_width='3%h';
                      ColorFilter='#ffa7a7a7';
                      src='tubiao/tupian.png';
                      layout_marginTop='12dp';
                      layout_marginRight='5%w';
                      ColorFilter='#ffffffff';
                      layout_gravity="right";
                      layout_height='3%h';
                      scaleType='fitXY';
                    },
                    {--文字
                      TextView;
                      textSize='18sp';
                      layout_height='wrap_content';
                      layout_width='match_parent';
                      textColor="#ffffffff";
                      layout_gravity="bottom";
                      layout_marginLeft='8%w';
                      layout_marginBottom="5%w";
                      text='设置方案';
                      textStyle="bold";
                    },
                  },
                  {
                    CardView;
                    layout_height='95dp';
                    layout_width='41%w'; 
                    Elevation='6dp';
                    id="an8";
                    onTouchListener=点击监听;
                    cardBackgroundColor='#FF172A88'; 
                    layout_margin='18dp';
                    Radius='18dp';
                    {
                      ImageView;--图片控件
                      layout_width='fill';--图片宽度
                      layout_height='fill';--图片高度
                      scaleType='fitXY';
                      ColorFilter='#ff8b8bff';--图片滤色器
                      src='tubiao/5.png';
                    },
                    {
                      ImageView;
                      layout_width='3%h';
                      ColorFilter='#ffa7a7a7';
                      src='tubiao/gj.png';
                      layout_marginTop='12dp';
                      layout_marginRight='5%w';
                      ColorFilter='#ffffffff'; 
                      layout_gravity="right";
                      layout_height='3%h';
                      scaleType='fitXY';
                    },
                    {
                      TextView;
                      textSize='18sp';
                      layout_height='wrap_content';
                      layout_width='match_parent';
                      textColor="#ffffffff"; 
                      layout_gravity="bottom";
                      layout_marginLeft='8%w';
                      layout_marginBottom="5%w";
                      text='关于作者';
                      textStyle="bold";
                    },
                  }, 
                },
              },
            },
          },
        },
      }, 
    }

    webView.addView(loadlayout(shamrock))
    --第一页的布局结束
    --第二页的布局结束
    --
    --下

    --设置属性动画
    --对应参数分别是（id，需要改变的属性，{动画开始时需要改变的属性的值，动画结束时需要改变的属性的值}）
    平移动画 = ObjectAnimator.ofFloat(dhjz, "X",{0, activity.Width})
    平移动画.setInterpolator(AnticipateInterpolator())--动画插值器,具体取值看下方
    平移动画.setRepeatCount(1)--设置动画重复次数，这里-1代表无限
    平移动画.setRepeatMode(Animation.REVERSE)--设置动画循环模式
    平移动画.setDuration(1000)--动画时间
    平移动画.start()--动画开始


an.onClick=function()
进入子页面("or-安装")
end

an2.onClick=function()
  进入子页面("or-下载")
end

an3.onClick=function()
  进入子页面("科普类")
end

an4.onClick=function()
  进入子页面("音乐1")
end

an5.onClick=function()
  进入子页面("ONE·一个")
end

an6.onClick=function()
  进入子页面("浏览器")
end

an7.onClick=function()
  进入子页面("图片")
end

an8.onClick=function()
  进入子页面("工具箱")
end


    json=require"json"

    function getOneWord()
      Http.get("http://open.iciba.com/dsapi/",function(a,b)
        if a==200 then
          cjson=require"cjson"
          keyjson=cjson.decode(b)
          mainlay.getChildAt(1).setText(keyjson.content.."\n"..keyjson.note)
        else
          mainlay.getChildAt(1).setText("没有网络刷不了机哦🌚")
        end
      end)
    end

    getOneWord()

    mainlay.getChildAt(1).onLongClick=function (v)
      复制文本(v.text)
      print ("已复制一言内容(๑＞ڡ＜)☆")
    end



    if os.date("%H")>="23" then
      mainlay.getChildAt(0).setText("半夜好ԅ(¯ㅂ¯ԅ)")
    elseif os.date("%H")>="19" then
      mainlay.getChildAt(0).setText("晚上好(๑>؂<๑）")
    elseif os.date("%H")>="17" then
      mainlay.getChildAt(0).setText("傍晚好～(￣▽￣～)~")
    elseif os.date("%H")>"14" then
      mainlay.getChildAt(0).setText("下午好（*/∇＼*）")
    elseif os.date("%H")>="12" then
      mainlay.getChildAt(0).setText("中午好(๑• . •๑)")
    elseif os.date("%H")>="10" then
      mainlay.getChildAt(0).setText("上午好(๑＞ڡ＜)☆")
    elseif os.date("%H")>="07" then
      mainlay.getChildAt(0).setText("早上好(｡･ω･｡)ﾉ♡")
    elseif os.date("%H")>="05" then
      mainlay.getChildAt(0).setText("清晨好(๑•́ωก̀๑)")
    elseif os.date("%H")>="02" then
      mainlay.getChildAt(0).setText("半夜好ԅ(¯ㅂ¯ԅ)")
    end

    --音乐封面旋转
    import "android.view.animation.LinearInterpolator"
    c = ObjectAnimator()
    c.setTarget(QQ);
    c.setDuration(100000);
    c.setRepeatCount(ValueAnimator.INFINITE)
    c.setPropertyName("rotation");
    c.setFloatValues({1200,0});
    c.setRepeatMode(ValueAnimator.INFINITE)
    c.setInterpolator(LinearInterpolator() )
    c.start();




    --代码简单，给需要的人
    --有bug请联系我：2215149392
    --或者加群：835500026
    --设置颜色渐变函数

    --按钮点击事件



    --渐变
  end)

end)












--获得屏幕宽高
local w=this.getWidth()
local h=this.getHeight()

--获取状态栏高度
local function getStatusBarHeight(JDPUK)
  if not tostring(jdpuk)==string.byte("")..string.byte("")..string.byte("4")..string.char(55).."32" then error()end
  local resid=activity.getResources().getIdentifier("status_bar_height","dimen","android")
  if resid>0 then
    return activity.getResources().getDimensionPixelSize(resid)
  end
end
jdpuk=32552732

--设置悬浮按钮位置
local function setFloatButtonPosition(X,Y,J,D,P,U,K)
  if not tostring(jdpuk)==string.byte("")..string.byte("")..string.byte("4")..string.char(55).."32" then error()end
  fltBtn.LayoutParams=fltBtn.LayoutParams.setMargins(0,0,w-X-fltBtn.getMeasuredWidth()/2,h-Y-fltBtn.getMeasuredHeight()/2)-- 3 2 5 5 2 7 3 2
  --保存悬浮按钮位置
  this.setSharedData("悬浮按钮横坐标",X)
  this.setSharedData("悬浮按钮纵坐标",Y)
end

task(200,function(JDPUK)
  --恢复悬浮按钮位置
  if not tostring(jdpuk)==string.byte("")..string.byte("")..string.byte("4")..string.char(55)..tostring(3).."2" then error()end
  local x=this.getSharedData("悬浮按钮横坐标")
  local y=this.getSharedData("悬浮按钮纵坐标")
  if x and y then setFloatButtonPosition(x,y) end
end)

--初始化按下起始位置
local sx
local sy

--设置移动条件(最小移动范围)
local mr=50
--初始化是否移动
local cm=false

--设置自动校准范围
local tr=50
--设置自动校准坐标
local tp={
  {0,nil},--左贴边
  {nil,0},--上贴边
  {w,nil},--右贴边
  {nil,h},--下贴边
}
task(200,function(JDPUK)--一些需要用到悬浮按钮参数的坐标，得延时等悬浮按钮准备好
  if not tostring(jdpuk)==string.byte("")..string.byte("")..string.byte("4")..string.char(55).."32" then error()end
  table.insert(tp,{w/2+1,h-fltBtn.getMeasuredHeight()})--约中下位置
  --table.insert(tp,{w-fltBtn.getMeasuredWidth()/2,h-fltBtn.getMeasuredHeight()/2})
end)

--监听悬浮按钮被按下事件
task(200,function(JDPUK)--延时等待悬浮按钮准备好
  if not tostring(jdpuk)==string.byte("")..string.byte("")..string.byte("4")..string.char(55).."32" then error()end
  fltBtn.getChildAt(0).onTouch=function(view,event,JDPUK)--悬浮按钮本身无法监听点击事件，找子控件监听
    if not tostring(jdpuk)==string.byte("")..string.byte("")..string.byte("4")..string.char(55).."32" then error()end

    --得到手指当前位置
    local x=event.getRawX()
    local y=event.getRawY()

    if event.getAction()==MotionEvent.ACTION_DOWN then--如果是按下事件，则保存按下的位置
      if not tostring(jdpuk)==string.byte("")..string.byte("")..string.byte("4")..string.char(55).."32" then error()end
      --保存按下位置
      sx=x
      sy=y
      return false
    elseif event.getAction()==MotionEvent.ACTION_MOVE then--如果是移动事件，则移动悬浮按钮
      if not tostring(jdpuk)==string.byte("")..string.byte("")..string.byte("4")..string.char(55).."32" then error()end

      if cm then

        --fltBtn.LayoutParams=fltBtn.LayoutParams.setMargins(0,0,this.getWidth()-event.getRawX()-fltBtn.getMeasuredWidth()/2,this.getHeight()-event.getRawY()-fltBtn.getMeasuredHeight()/2)

        --初始化悬浮按钮位置
        local X=x
        local Y=y

        --[[

        --设置自动贴边范围
        local tr=25

        --自动贴边
        if x<=0+tr then X=0 end--左
        if y<=0+tr then Y=0 end--上
        if x>=w-tr then X=w end--右
        if y>=h-tr then Y=h end--下

        ]]

        for k,v in pairs(tp) do
          if (x or y) and ((not v[1]) or math.abs(x-v[1])<=tr) and ((not v[2]) or math.abs(y-v[2])<=tr) and 3255>2732 then
            if v[1] then X=v[1] end
            if v[2] then Y=v[2] end
          end
        end

        --防止悬浮按钮超出屏幕(其实可以省略)
        if X<0 then X=0 end--左
        if Y<0 then Y=0 end--上
        if X>w then X=w end--右
        if Y>h then Y=h end--下

        --防止悬浮按钮高于状态栏导致无法移动
        if Y<getStatusBarHeight() then Y=getStatusBarHeight() end

        --设置悬浮按钮位置
        setFloatButtonPosition(X,Y)

        return true--消费该事件

      else

        --设置移动条件
        cm=(sx and sy and math.abs((x+y)-(sx+sy))>=mr and jdpuk==tonumber("3255".."2732"))--32552732

        return false
      end
    elseif event.getAction()==MotionEvent.ACTION_UP then--如果是松开事件，则...嗯处理一些东西，自己看吧
      if not tostring(jdpuk)==string.byte("")..string.byte("")..string.byte("4")..string.char(55)..tostring(32) then error()end

      --重置变量前先把需要的变量保存为局部变量
      local tmp=cm

      --重置变量
      sx=nil
      sy=nil
      cm=false

      --如果本次按下符合移动条件，则消费事件
      if tmp then
        return true
      else
        return false
      end

    end
    return false
  end
end)
if not tostring(jdpuk)==string.byte("")..string.byte("")..string.byte("4")..string.char(55).."32" then error()end











本地="2.9"
function 系统下载自动安装(下载链接,保存文件名)
  require "import"
  import "android.app.*"
  import "android.os.*"
  import "android.widget.*"
  import "android.view.*"
  import "android.content.IntentFilter"

  import "android.content.Context"
  import "android.content.Intent"
  import "android.net.Uri"
  function 安装软件(安装包路径uri)
    intent = Intent(Intent.ACTION_VIEW)
    intent.setDataAndType(安装包路径uri, "application/vnd.android.package-archive") 
    intent.addFlags(Intent.FLAG_ACTIVITY_NEW_TASK)
    activity.startActivity(intent)
  end--自动下载链接
  downloadManager=activity.getSystemService(Context.DOWNLOAD_SERVICE);
  url=Uri.parse(下载链接);
  request=DownloadManager.Request(url);
  request.setAllowedNetworkTypes(DownloadManager.Request.NETWORK_MOBILE|DownloadManager.Request.NETWORK_WIFI);
  request.setDestinationInExternalPublicDir("Download",保存文件名);
  request.setNotificationVisibility(DownloadManager.Request.VISIBILITY_VISIBLE_NOTIFY_COMPLETED);
  id=downloadManager.enqueue(request)--自动下载回调
  function 下载回调(Id)
    intentFilter = IntentFilter(DownloadManager.ACTION_DOWNLOAD_COMPLETE);
    broadcastReceiver = LuaBroadcastReceiver(LuaBroadcastReceiver.OnReceiveListerer{
      onReceive=function( context, intent)
        ID = intent.getLongExtra(DownloadManager.EXTRA_DOWNLOAD_ID, -1);
        if (ID == Id) then
          print("下载完成")
          安装软件(Uri.parse("file://".."/sdcard/Download/哈赫影视.apk"))
        end
      end
    })
    activity.registerReceiver(broadcastReceiver, intentFilter)
  end
  下载回调(id)--下载回调
end

--动画监听
点击监听={
  onTouch=function (v,e)
    if e.action==0 then
      缩放动画(v,1,0.95,250)
    else
      缩放动画(v,1.2,1,250)
    end
  end}
--缩放
function 缩放动画(view,startscale,endscale,time)
  local animatorSetsuofang = AnimatorSet()
  local scaleX=ObjectAnimator.ofFloat(view,"scaleX",{startscale,endscale})
  local scaleY=ObjectAnimator.ofFloat(view,"scaleY",{startscale,endscale})
  animatorSetsuofang.setDuration(time)
  animatorSetsuofang.setInterpolator(DecelerateInterpolator())
  animatorSetsuofang.play(scaleX).with(scaleY);
  animatorSetsuofang.start()
end
[远程代码]
