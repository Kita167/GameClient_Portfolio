# 游戏客户端——作品集展示

游戏客户端作品集主链接，包含项目演示视频，代码库链接，技术简述

## 1. UE5.7 ：基于GASP的环境感知动作匹配动画系统 2026年1月—2026年6月
- 演示视频


https://github.com/user-attachments/assets/46766a9e-46bb-4d3d-8c5d-d33aeba57309


<video src="media/UE_EMM_Overview.mp4" controls width="960">
  您的 Markdown 查看器不支持 video 标签，可直接打开文件：media/UE_EMM_Overview.mp4
</video>

### 技术要点
- 技术栈： Unreal Engine C++、引擎源码修改、插件开发、PoseSearch/Motion Matching、多线程同步（读写锁）、AnimationModifier
1. 基于 UE PoseSearch 扩展 Motion Matching 评分链路，将环境障碍信息引入候选动画选择，实现静态障碍避让与多人动态躲避。
2. 在 Editor 侧新增环境特征预处理：构建 Ellipse（水平占据）与 HeightRange（高度区间 + root Z 偏移）通道，产出运行时可检索数据。
3. 在 Runtime 侧实现 AnimNode 环境上下文注入，并在数据库评分中统一叠加环境惩罚，形成“动作相似度 + 环境可通过性”双重评分机制。
4. 开发线程安全障碍快照系统：SceneComponent 采样、WorldSubsystem 管理、动画线程只读快照；采用读写锁与动态障碍增量刷新优化并发性能。
5. 扩展 NPC Steering 协作避让能力，提升多人场景对向/交汇时的稳定绕行表现。
6. 采用每周周报 + 线上周会同步研发进展

> 由于EpicGame虚幻引擎相关隐私协议和项目保密协议，无法展示相关源代码


## 2. GameJam作品





### 2.1 GlobalGameJam（线下48h）   2026年1月
###  《拟态链》 Unity引擎  
- 2D等距俯视角潜行游戏 
- 核心玩法：扮演抱脸虫，在10秒倒计时内寻找关卡出路，并不断靠近并夺舍敌人重置计时，计时结束则死亡

- 游玩视频预览



https://github.com/user-attachments/assets/8f1dad96-6b45-4c6f-a39b-323c3bf54553


<video src="media/【GGJ2026】《拟态链》 (The Mimic Chain) 游戏作品展示—2026GlobalGameJam.mp4" controls width="960">
  您的 Markdown 查看器不支持 video 标签，可直接打开文件：media/【GGJ2026】《拟态链》 (The Mimic Chain) 游戏作品展示—2026GlobalGameJam.mp4
</video>
- b站视频链接： https://www.bilibili.com/video/BV1Bs6tB3ELM/

#### 技术要点
- 使用FSM（有限状态机）实现主角逻辑，通过更新“覆写动画控制器”实现不同动画状态机的切换
敌人有可视范围（锥形），当玩家进入视野后会逃跑（平民），保持一定距离射击（守卫）

- Github项目链接：https://github.com/Kita167/2026GlobalGameJam


### 2.2 2025Sony爱满星空（线上7天）   2025年9月
### 《融石之海》 Unity引擎
- 2D等距塔防游戏
- 核心玩法：玩家敲击键盘获取资源放置/升级设施，抵抗敌人波次进攻，击败最后boss获得游戏胜利。

- 演示视频

  https://github.com/user-attachments/assets/be30412f-13cd-4454-a756-8270d7f48388


<video src="media/【索尼2025爱满星空7天GameJam】融石之海（洪水灾难主题塔防游戏），28届首次参加GJ作品程序向展示.mp4" controls width="960">
  您的 Markdown 查看器不支持 video 标签，可直接打开文件：media/【索尼2025爱满星空7天GameJam】融石之海（洪水灾难主题塔防游戏），28届首次参加GJ作品程序向展示.mp4
</video>
- b站视频链接：https://www.bilibili.com/video/BV1mBnnzzEzy

#### 技术要点
- 设计模式（观察者模式，对象池，有限状态机），接口，ScriptableObject，升级系统
1. Boss行为AI：boss会随机的召唤小兵进攻，使用FSM管理bossAI，使用SO管理每个状态的数据
2. 敌人与建造：用枚举标记目标类型，使用Queue和哈希表构建复合型对象池，管理敌人和建筑生成。
3. 升级系统：(1.弹窗)达到阈值时跳出选择弹窗升级至指定建筑 (2.预设)在UI面板上选择对应目标，按照预设自动升级
4. UI系统：用观察者模式统一管理UI事件
- GitHub项目链接：https://github.com/Kita167/Sony2025GameJamDemo.git

## 3. Unity个人Demo 2025年7月
### 3D RPG 寻路战斗 + 存档系统

1. 实现“移动/攻击/交互/换武器/升级”核心闭环，构建可玩的 RPG 战斗流程。
2. 设计可复用存档架构：基于 ISaveable + 唯一 ID 持久化，实现跨场景对象状态恢复。
3. 使用 NavMesh 与 FSM 管理敌人巡逻/警戒/追击行为，提升模块复用性与可维护性。

- GitHub项目链接：https://github.com/Kita167/3dRpgDemo.git
