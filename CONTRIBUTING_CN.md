maintainer-tools/CONTRIBUTING.md
OCA编码参考

本页介绍在OCA托管下项目的编码参考,这些参考旨在提高编码的质量:更好的可读性,更好的可维护性,更好的稳定性和更少的退化性

OCA编码参考大致以Odoo编码参考为基础,并进行了一些修改.这些修改改善了OCA编码参考,使它们更适合这个项目的需求.习惯使用Odoo编码参考的用户可以跳过"与Odoo编码参考的差异"这一节.


模块

* 模块的名字使用单数形式(或者使用multi),在odoo中复合模块的名字或者对象已经是复数形式的除外(例如:mrp_operations_...)
* 使用描述模板然而需要删除内容没有意义的部分
* 在__openerp__.py 清单文件
    - 避免多余的空格
    - 确保存在LICENSE信息
    - 确保Odoo Community Association (OCA)文本信息添加在author后面


版本编号

模块列表中的版本编号应该是Odoo的主版本(例如:8.0)后面添加模块的x.y.z版本编号.例如:8.0.1.0.0应该表示8.0版本模块的第一次发布

x.y.z版本编号根据的语义为breaking.feature.fix (断点.特性.修复)
    - x 在数据模型或者视图有重大改变时,数字增加.这种情况下可能需要做数据转移,或者依赖它的模块可能被影响.
    - y 在添加非突破性的新特性被添加时,数字增加.这种情况下将需要进行模块更新
    - z 在bug修复后,数字增加.这种情况下,通常需要重启服务器来确保修复的可用性.

如果版本编号发生变动,安装实移植的使用说明或者脚本应该被包含在重大改变中.


目录

模块由以下的几个目录组成:
    - controllers/: 包含控制器(http路由)
    - data/: data xml
    - demo:/ demo xml
    - models/: model 定义
    - report/: reproting models(BI/analysis), Webkit/RML 打印报表模板
    - static:/ 包含web资源,划分为 css/, js/, img/, lib/....
    - views/: 包含视图,模板和Qweb报表打印模板
    - wizards/: 向导的模型和视图
