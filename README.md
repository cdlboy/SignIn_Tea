# SignIn_Tea
## 考勤系统教师端
<br>  该软件为考勤系统教师端，采用bmob后端云和百度地图定位api。首先教师需要在设置课程（同一课程不同时间段请设置为多个课程），然后由学生选择课程
（暂时显示所有课程，只显示所在系院课程后续添加）。接着由教师发起签到，并在发起签到界面选择自己的课程并输入一个4位的签到码，该签到码将作为本节课的id，
如该签到码被使用，换一个重新输入即可。
<br>  学生端签到只需要输入这个4位签到码即可签到。教师端结束签到后，该签到码将会被回收，以便该签到码可以被重复利用，所以请教师上完课后马上结束签到，
否则学生可以在课后也进行签到。结束签到在《查看签到》栏中。
<br>该签到系统使用定位的方式，如果手机定位离教师过远的话将无法进行签到。
##界面介绍
###发起签到
<br>  点击该栏将会跳出一个对话框，其中包含4位签到码输入框和一个课程选择下拉框。如果没有显示课程，请在课程设置中设置。如果签到码未被其他教师使用，
点击确定即可发起签到。学生端输入该签到码签到即可。如果显示有签到未结束请先在查看签到中结束签到。
###签到记录
<br>教师可以通过该栏查询学生的签到记录。选择起始时间，结束时间和课程后，点击查询即可。
###缺勤记录
<br>与签到记录用法相同。
###课程设置
<br>该界面显示了教师所设置的课程，右上角的+1可以添加一个课程，输入课程名称即可。右上角的叉为删除按钮，教师选中课程后点击该按钮即可删除选中的课程。
###查看签到
<br>该界面中可以查看当前课程的签到情况，已签到：签到人数/选择该课程总人数。列表栏显示未签到学生姓名学号。
###更改密码
<br>该界面用于更改密码。找回密码，手机验证等功能可以根据bmob后端云文档自行添加。
##代码使用
<br>使用代码前请先申请bmob账号，新建一个应用后在云数据库中添加NotArrive、Course、GeoPoint、Record、StudentCourse这几张表，然后在设置中复制
Application ID，将复制的id粘帖到代码LoginActivity类的APPID中即可。注：教师端，学生端使用同一个bmob应用，因此学生端代码请同样使用该Application ID。
```Java
    public static String APPID ="";//放入自己申请的bmob后端云key
```
##后续更新
<br>添加院系设置，识别手机码使得一台手机一节课只能签到一个帐号。
<br>如有疑问或建议请联系zrw269113179@126.com