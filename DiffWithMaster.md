# 相较于主分支变更内容
- 1、Model 默认不执行Safe函数，保证链式调用不重复构建新的Model指针对象

- 2、gredis Option 构建结构调整

- 3、gdb 增加NewCounter函数

- 4、gdb 事务Rollback时判断事务是否已关闭

- 5、Redis 脚本封装:
    - 减少numKeys的传递，根据调用调用函数时传递keys自主判断。
    - Run函数运行脚本时，使用EVALSHA运行脚本，如果脚本不存在，则使用EVAL重试并尝试缓存脚本，以提升运行效率

- 6、gtime.Format 废弃标注，gtime.Format与标准库`time.Time`的 Format 方法冲突容易造成生产事故

- 7、Redis 添加 GetConfig()