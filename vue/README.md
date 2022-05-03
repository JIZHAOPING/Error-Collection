> 安装完vue后，查询vue版本时报错**vue : 无法加载文件 C:\Users\lenovo\AppData\Roaming\npm\vue.ps1，因为在此系统上禁止运行脚本。有关详细信息，请参阅 https:/go.microsoft.com/fwlink/?LinkID=135170 中的 about_Execution_Policies。**

&emsp;&emsp;解：windows的安全原因导致不允许在power shell执行脚本，执行`Get-ExecutionPolicy -List `查看一下执行策略的列表。我的全部显示undefined。说明当前作用域中未设置执行策略。我们可以修改一下执行策略`set-ExecutionPolicy RemoteSigned`。RemoteSigned表示本地创建的脚本可以运行。但是改变执行策略的命令可以成功，但是仍然不能改变有效的执行策略。例如，为设置执行策略的命令
本地计算机可以成功，但会被当前用户的执行策略覆盖。所以直接改变当前用户的执行策略`Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`。



> 安装配置完vue-router后报错：**Uncaught TypeError: Object(...) is not a function**

&emsp;&emsp;解：因为版本不对。我用的vue是2.5.2版本的。vue-router是4版本的。应该把vue-router安装成3版本

> router-view不显示组件内容
> 
&emsp;&emsp;解：
   1. 可能是因为vuecli2要求路由集合的变量名必须是routes而不是routers
   2. 我是因为在路径设置那里加了点
