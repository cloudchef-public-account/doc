**SmartCMP5.1功能更新说明**
+ 全新设计的UI
    + SmartCMP界面进行了全新升级，UI更美观，信息布局更加合理，优化交互和用户体验。

+ 云平台管理
    + Azure的新增功能：支持按需创建新的Azure安全组NSG，配置安全组规则。
    + Hyper-V的新增功能：自动化部署Hyper-V虚拟机，支持通过IP池进行IP分配；支持为Hyper-V虚拟机创建和配置多个网卡；支持更多的Hyper-V虚拟机Day2运维操作，包括：调整配置，虚拟机或存储迁移，以及重置虚拟机的OS主机名。
    + 针对青云的新增功能：向青云公有云和私有云部署虚拟机，支持通过IP池进行IP地址分配。能够为青云公有云和私有云的虚拟机创建快照，从快照进行恢复，并对快照进行管理。支持远程终端连接青云私有云的虚拟机。

+ 资源池管理
    + 创建新资源：支持按需创建Azure资源组（包括新建虚拟网络VNET，子网，以及诊断存储账户）。

+ IP地址管理
    + 支持IP地址池目录结构管理，可以创建多级目录，定义不同层级的网络环境和IP地址段，以树形结构进行展示。
    + 支持IP池中设置主备DNS，网段路由信息，在给虚拟机分发IP地址的时候同时进行设置。

+ 审批流程管理
    + 提供内置审批流程引擎，使用可视化的流程设计器创建和修改流程。
    + 支持并行审批、条件审批。

+ 工单服务管理
    + 支持事件处理流程，解决用户IT资源相关的问题，例如：VM出现故障，数据库性能问题等。

+ 计费管理
    + 价格预估:支持在申请服务时，展示预估的费用。

+ 服务编排与发布
    + 应用组件建模 :导入蓝图时支持同时导入组件。
    + 工单服务: 支持创建和发布IT故障单，用户汇报问题，IT支持团队进行解决。支持可视化的流程设计器设计工单服务流程。支持为手工工单服务关联审批流程。
    + 新增一键部署Oracle RAC。

+ 自定义表单
    + 支持表单设计器，创建和配置自定义表单，定义用户申请服务时所需要填写的字段信息。
    + 支持将创建的表单与云资源部署服务或工单服务进行关联，从而使得用户在申请服务时填写服务所需的字段信息。 

+ 自助服务
    + 自助申请：支持在申请服务的时候，能够对已填写参数进行保存，在下次申请的时候，可以重新加载，自动填充上次已经填写好的参数。
    + 已部署虚拟机的自助管理：可设置定时循环任务，定期执行操作，并能够查看定时任务，进行取消。
+ 系统管理
    + 菜单配置：支持接入第三方系统的页面，并可以配置菜单所处的位置，指定能够访问的角色。





























































































































