﻿<<<<<<< HEAD
﻿# trello

标签（空格分隔）： 

---

在此输入正文

###运行
- npm start
- 安装sematic-ui会出现对话框 skip然后no,let me specify就可以了。
- 通过 http://127.0.0.1:8080 访问

###技术栈
- JS框架：Vue.js
- Css框架: Semantic-ui&&Element-ui
- 脚手架：vue-cli

###小插件
- dnd.js

###功能
- [x] 添加多个列表
- [x] 列表内添加多项列表项
- [x] 列表项信息编辑
    - 快速编辑: 列表项右方小按钮
    - 详细编辑: 点击列表项弹出详情页
    - 列表头编辑： 点击表头修改
    
- [x] 删除列表/清除列表所有子项(列表右上方)
- [x] 列表项拖动
- [x] 滚动条部分
    - 内容超出页面弹出滚动条
    - 添加列表自动滚动至末端
    - 鼠标点击文档部分亦可拖动
- [ ] 复制功能
- [ ] 添加多个看板
- [ ] 附件上传

###部分截图

> - Home
![Home][1]
> - 添加
![Add][2]
> - 快速编辑
![Qucikadd][3]
> - 详细编辑
![Edit][4]
> - 卡片移动
![Move][5]
###总结
- 模块划分:
> Home
 >>1.内容模块
    >>>a.列表组件
        >>>>列表项组件

 >>2.公用弹出层模块
    >>>a.快速编辑
    >>>b.详情编辑
        >>>> 日历组件
        >>>> 标签编辑组件
        
    >>>c.列表头菜单
    
    
- 难点
    - 数据的流向
      1.根组件接受到数据
      2.渲染多个列表
      3.列表数据props到子项
      4.通过一个空的vue对象联结起子项与大小编辑面板(非父子组件通信)
   
    - 子项的拖动
      1.每一个子项添加一个阴影框,检测到拖动元素进入时显示,并且接收宽高大小
      2.拖动移出或结束时阴影框移除
      3.被拖动元素元素需要传输的数据包括
        - 容器宽高
        - 父数据与索引(用于移除)
        - 自身的数据
        
      4.放下的位置需要检测的数据包括
        - 父数据以及索引(用于决定添加的位置)
    - 滚动条部分
      1.鼠标在文档拖动的距离
      2.滚动条移动的距离
      3.内容移动需要移动的距离
      4.三者需要按相同比例关联起来

- 改进

 - [ ] Vuex管理 替代混乱的 eventBus


  [1]: https://helloforrestworld.github.io/trello/screen_shot/home.png
  [2]: https://helloforrestworld.github.io/trello/screen_shot/add.gif
  [3]: https://helloforrestworld.github.io/trello/screen_shot/quickedit.gif
  [4]: https://helloforrestworld.github.io/trello/screen_shot/edit.gif
  [5]: https://helloforrestworld.github.io/trello/screen_shot/move.gif