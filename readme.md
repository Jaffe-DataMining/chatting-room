 功能模块分析

   * 网络搭建
        客户端 ： udp客户端
        服务端 ： udp服务端

   * 进入聊天室
        客户端 ： * 输入姓名
                 * 向服务器发送请求
                 * 接收结果
                 * 允许则进入聊天，不允许则重写输入姓名

        服务器 ： * 接受请求，区分请求类型
                 * 判断用户是否存在
                 * 如果允许进入，将其加入存储结构
                 * 通知其他用户，告知本人可以登录
                 * 如果不允许则结束，告知用户不可以进入

   * 聊天
        客户端 ： * 创建新的进程
                * 一个进程循环的发送消息
                * 一个进程循环的接收消息

        服务端 ： * 接收请求，判断请求类型
                 * 将消息转发给其他用户
                   xxx : xxxxxxxxx

   * 退出聊天室
        客户端 ： * 输入quit 或者 ctrl-c退出
                * 发送请求给服务端
                * 结束进程
        服务端 ： * 接收请求，判断请求类型
                 * 将退出消息发送给其他人
                 * 将用户从字典删除

   * 管理员消息

5. 协议设定

     请求格式：
        登录 ：  L name
        聊天 ：  C name text
        退出 ：  Q name

     响应格式：
        登录 ： 成功（OK） 失败（失败原因）
        退出 ： 给客户端发送 EXIT 让客户端接收进程退出
