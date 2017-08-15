# 四种情形
## A、父View都不拦截,子View onTouchEvent返回false
## B、父View都不拦截,子View onTouchEvent返回true
## C、父View只不拦截down,子View onTouchEvent返回true
## D、父View拦截了down
# 结果
## A、所有方法走一遍，都只会处理down事件
## B、onTouchEvent正常执行，会出现down,move,cancel等ACTION
## C、子View第一次出现down事件，第二次出现cancel，接下来在抬起前收不到事件，父View会继续执行
## D、父View拦截了down，子View无法收到事件