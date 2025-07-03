```
discovery/
├── discovery.go        // 主要接口和实现
├── config.go           // 配置结构
├── node.go             // 节点结构
└── example_test.go     // 使用示例
```


# 功能特点
主动状态宣告处理：

收到包含 status=offline 的宣告立即标记节点为离线状态

收到正常宣告立即更新或添加节点为在线状态

自身下线时发送离线宣告

事件驱动架构：

提供 RegisterEventHandler 注册状态变更回调

节点上线/下线时触发事件通知

简洁的API：

NewDiscoveryManager 创建服务

Start/Stop 控制服务生命周期

GetNodes 获取当前节点状态

封装细节：

隐藏 mDNS 实现细节

自动处理网络接口选择

内置节点超时检测

日志控制：

默认关闭所有内部日志

通过事件回调提供必要信息

