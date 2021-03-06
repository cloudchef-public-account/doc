**云服务使用指南**


云资源蓝图服务基于蓝图建模来定义标准的服务框架与组件，提供丰富的开箱即用的软件组件，以可视化的形式编排蓝图，将服务发布成服务卡片，用户通过服务目录申请云资源蓝图服务。
例如：申请一项vSphere单节点虚拟机服务是云资源蓝图服务使用的典型场景。
下文为您介绍服务申请、服务部署的具体操作。 
# 服务申请

## 服务快速申请
平台内置了常用的服务卡片，例如申请数据库、申请云资源，支持用户可在服务目录选择快速申请，无需服务配置，选择所需蓝图，直接申请服务进行自动化部署。
例如：
+ 进入服务目录您可查看到申请数据库的服务卡片，数据库服务绑定了多个蓝图包括：所有纯数据库的蓝图，Oracle（包括群集的），MySQL（包括群集的），MongoDB，DB2，SQL Server
+ 点击「申请数据库」选择需要的蓝图，即可快速申请自动化部署。

 

## 服务目录申请

用户可在服务目录申请已配置完成的服务服务，具体申请步骤：

 在左侧导航栏点击「服务目录」，选择某一服务，点击将进入服务申请页面

服务申请页面显示该服务的详细信息：

服务申请 -服务详情   
 
 +  描述                 该服务的描述信息
 +   基本信息             服务配置/业务组配置的服务租用时间、保留时间
 +   服务拓扑             服务所用的拓扑图
 +   组件配置             服务拓扑图中的所有组件，展开后可查看各个组件的配置信息
 +   流程控制             服务配置/业务组上设置的部署/卸除前/后序操作，及是否需要审批以及邮件通知

  服务申请页面填写相关申请参数：


+ 组织信息
业务组	若该服务为全部业务组，即共享服务，需选择业务组（该业务组需有相关资源池，否则将不允许申请）；若服务配置时该服务已指定业务组，则无需填写
项目	若该业务组下划分了项目，则可以选择项目
所有者	选择该服务的所有者，所有者需为业务组成员

+ 部署信息
名称	若业务组已配置 “服务部署名命名规则”，则服务部署名无需填写，将根据业务组规则自动生成；
若业务组未配置“服务部署名命名规则”，需手动填写
数量	填写部署的数量，默认为1
执行时间	可指定时间开始服务部署，精确到分钟

+ 其他信息
键值标签	默认勾选，所有server节点使用相同的键值标签
若不勾选，将列出该服务部署下的所有server节点，可为每个server节点单独设置键值标签
所有Server节点	若勾选键值标签，可为所有server节点设置键值标签
备注信息	选填
申请附件	选择文件作为附件
表单配置的字段信息	填写在「服务建模」-「表单配置」界面额外自定义的字段

+ 申请参数
申请参数	若服务配置时，勾选了 “允许申请时改变”，将出现申请参数栏，可根据需要配置相关参数
软件配置	若在服务配置时勾选了“允许申请时添加软件”，将出现软件配置栏，可为该服务的计算节点/软件组件添加软件，点击「添加软件」
	选择要安装的软件，将列出所有的软件组件
	选择关系：“安装到”或“依赖于”
	选择要安装到或依赖于的节点


 填写完成后点击「申请」，将根据业务组流程控制直接部署或等待审批，可至「我的部署」-「服务部署」中查看部署情况（也可在右上角「操作历史」中查看部署情况），或至「服务审批」-「我的申请」中查看审批流程。

 ### 自动加载

 用户进行服务申请时，未能一次性填写完相关参数，点击「保存」能够对已填写参数进行保存，并且在下次申请的时候，点击「加载」可以重新加载，自动填充上次已经填写好的参数。

 ### 预估费用

 在您进行服务申请时，平台可以显示此次申请的费用（按月计算）。
	针对私有云，管理员在「计量计费」-「计费规则」配置私有云的计费规则之后，用户在申请服务时，直接使用计费的API进行计费。
	针对公有云需要缓存公有云的单价API结构，然后计算费用。


# 服务请求


+ 用户申请服务的操作完成之后，如果该服务提前配置有审批流程，则该服务进入待审批状态，等待审批人执行审批操作。

+ 如果没有审批流程，服务请求信息进入「我的请求」信息列表，云资源服务直接进入准备部署状态，则进入「我的部署」查看部署信息。

## 我的请求

此处显示当前用户发起的服务请求。查看服务详情的步骤如下：

1.  点击左侧菜单栏的「服务请求」-「我的请求」，可查看用户申请服务的列表。

2.  该页面显示请求编号、服务名称、请求类型、标题、业务组、项目、申请状态、申请时间以及完成时间。可点击「请求编号」可查看申请的详细信息。

## 待审批

服务申请完成后，该服务提前配置有审批流程时，该服务进入待审批状态，「待审批」模块显示该服务的详情。

审批人可按照以下步骤查看待审批服务的详情：

1.  在左侧导航栏点击「服务请求」-「待审批」，待审批页面显示用户待审批的服务详情，

2.  显示审批请求的基本信息：申请编号，请求类型，服务部署名称，申请者，业务组，项目，申请状态，申请时间。

## 已审批

「已审批」模块显示审批人已经执行完成审批操作的服务请求。

查看审批完成的服务请求的具体步骤：

1.  在左侧导航栏点击「服务请求」-「已审批」，已审批页面显示你发起的所有审批请求其中已经审批通过的部分

2.  显示审批请求的基本信息：申请编号，请求类型，服务部署名称，申请者，业务组，项目，申请状态，申请时间。

# 服务部署


## 概述

服务部署页面可查看服务部署的状态、详情、监控等。用户在「服务目录」选择服务目录申请后，若该部署有审批流程，则服务部署进入待审批状态，审批通过才能执行部署操作；若无审批，则服务部署开始进行，点击服务部署名称，可查看该部署详情信息。

1.  在左侧导航栏选择「我的部署」-「服务部署」后，用户将会看到服务部署列表，点击高级搜索，可根据业务组、阶段（运行、操作进行中、关闭、操作失败、已取消、部署审批中
    ）、状态（正常、异常）、所有者、项目进行筛选，也可直接进行搜索操作

2.  在服务部署列表中，用户可以选中一个或者多个服务部署快速进行一些操作，包括「停止服务部署」「安装软件」「复制服务部署」「延长过期时间」「卸除服务部署」「删除管理信息」「更改所有者」，更多操作如：「更改项目」「更改业务组」和「伸缩」

3.  点击服务部署名称，可查看该服务部署的详细信息。服务部署详情信息界面包括「基本信息」「服务部署拓扑」「操作历史」「监控」（对云主机和应用组件的监控）以及顶部的运维操作

4.  「基本信息」包括服务部署的名称、业务组、项目、蓝图、资源池、云平台，以及费用、状态、时间等相关信息。还包括该服务部署的输入参数列表以及输出结果信息。服务部署失败后，某些场景可线下修复，修复成功后支持更改服务部署状态，将操作失败更改为运行

5.  「服务部署拓扑」包括服务部署的蓝图、详情和流程信息。鼠标悬停至服务拓扑图中，将显示该节点的关键信息，如Server节点将显示云主机名称、客户操作系统、IP地址、内存、磁盘总空间、vCPU数量、CPU使用率、内存使用率等

6.  「操作历史」显示该服务部署的操作历史记录

7.  「监控」显示对该部署中有的组件应用的监控信息

### 服务部署运维操作

在服务部署列表界面或点击服务部署名称进入服务部署详情界面，均可对服务部署做运维操作。

>「Note」服务部署的运维操作的权限由业务组和服务配置进行控制，此处默认该用户拥有运维操作的权限。为了方便您进行运维操作，平台对运维操作进行了分组

#### 更改组织信息 
更改所有者 

更改服务部署的所有者，将会同时改变该服务部署下的所有虚机的所有者。现在目标所有者，该所有者为该业务组下的成员。

更改项目 

更改服务部署的所属项目，将会同时改变该服务部署下的所有虚机的所属项目。选择目标项目，并选择该项目下的用户。

更改业务组 

将会把该服务部署下的所有虚机同时更改到新业务组中，并修改所有者等相关信息。选择目标业务组，项目（可选），所有者（该业务组下的成员），资源池（该业务组下的资源池）。如果资源池列表为空，表示该业务组上没有可用的资源。

#### 启动服务部署 {#启动服务部署 .afff6}

若服务部署处于关闭状态，则「启动服务部署」操作可用。可以通过设置「启用定时」，从而定时（将来某一时刻）触发此项任务。

#### 停止服务部署 {#停止服务部署 .afff6}

若服务部署处于正在运行的状态，则可以「停止服务部署」，该操作将对该服务部署下的所有虚机进行关机操作。可以通过设置「启用定时」，从而定时（将来某一时刻）触发此项任务。

#### 卸除服务部署 {#卸除服务部署 .afff6}

服务部署后，可卸除该服务部署下的云资源。卸除服务部署将删除在SmartCMP中新建的所有资源。若该服务部署中包含共享资源，将不删除共享资源；若该服务部署包含已有资源，如LoadBalance"使用已有资源"，将不删除已有资源；若导入资源后，您是该资源的Owner，可删除导入资源。



#### 重新执行部署 {#重新执行部署 .afff6}

可在服务部署后针对部署节点进行重新执行部署的操作。

操作步骤：

1.  点击「重新执行部署」，将展示该服务部署名称、该部署下的所有计算节点/存储节点/软件组件节点以及部署状态

2.  可单选或多选节点进行重新执行；可启用定时，指定时间进行操作

3.  点击「提交」，等待执行

#### 删除

删除管理信息 

删除该服务部署以及所属虚拟机在SmartCMP上的相关信息，在相关云平台中仍然保留，不进行删除。

删除节点

可在服务部署后删除计算节点、存储和软件组件。点击「删除节点」，将展示该服务部署名称、该部署下的所有计算节点、存储和软件组件节点以及部署状态，可单选或多选节点进行删除，可启用定时指定时间进行操作。

#### 扩展与伸缩
伸缩 

扩展当前部署下的实例，静态IP部署的Server不支持伸缩。至少伸缩1个实例，最多6个。可以通过设置「启用定时」，从而定时（将来某一时刻）触发此项任务。

 延长过期时间

延长服务部署的租用到期时间，点击将显示业务组中设置的最大可延期次数以及已延期次数，选择延长到哪一时间到期，精确到分钟。


复制服务部署
服务部署成功后，可将该服务部署整体的应用环境复制至其他云平台或克隆至当前云平台。如vSphere至阿里云，vSphere至vSphere，阿里云至阿里专有云

操作步骤：

1.  选择目标服务：选择目标业务组、项目（可选）、所有者以及服务，选择当前实例节点作为模板来复制/新建到所选的服务拓扑图中的目标节点

2.  配置参数：填写服务部署名称（若业务组有规则将根据业务组规则自动生成）、服务部署租用到期时间，以及配置该服务拓扑图中的其他节点参数（若是跨云复制，则需要第三方支持）

3.  点击「提交」，等待执行

#### 安装软件

选择服务部署下的云主机，并选择需要安装的软件。该软件列表来源于「软件组件」，可对软件的属性键值进行更改。


# 云主机


## 概述

用户可以根据下面的步骤来查看云主机列表来对其进行管理和操作。

具体操作步骤：

1.  在左侧导航栏选择「我的部署」-「云主机」后，用户将会看到云主机的列表。可在该列表界面查看云主机所属云平台、操作系统、是否安装监控代理、是否属于导入、云主机状态（已启动、遗失、停止等）、健康状态等，其他展示列可通过点击「展示列」，可以勾选或者不选某些列进行展示。根据业务组，项目，标签可以进行筛选

2.  在云主机列表中，用户可以选中一个或者多个云主机快速进行一些操作，包括「启动」「重新启动」「挂起」「停止」「执行脚本」「设置标签」「启用/切换监控」「更新监控代理」「更新自动化代理」，具体操作介绍会在下文展开

3.  您也可以单击某一个云主机进入其详情界面进行管理和操作，虚拟机详情界面包括「基本信息」「操作历史」「快照信息」「监控」「应用列表」和顶部的运维操作列表

4.  「基本信息」包括了虚拟机及其相关主机的一些信息，该虚拟机在平台中的组织信息以及该虚拟机的CPU、内存、存储的运行状态、VNC连接信息等

5.  「操作历史」包括了该虚拟机进行过的操作的历史记录

6.  「快照信息」显示当前的快照信息（快照名称、创建时间等），点击「添加」可以创建快照

7.  「监控」包括了该虚拟机CPU、内存、磁盘、网络的监控数据（可以按照需要调整时间跨度或者平均时间来查看历史监控数据）

>「Note」只有在虚拟机模板中配置安装监控的虚拟机在部署生成后，才可以在监控中看到数据，如何配置安装监控请参看「虚拟机模板管理」章节。

8.  「应用列表」显示当前虚机已安装的应用列表

9.  Day2的操作列表包括了该虚拟机可执行的操作列表，具体操作介绍会在下文展开

### 云主机运维操作

在云主机列表界面或点击云主机名称进入云主机详情页面，均可对云主机进行下列运维操作，运维操作的启用与否由业务组/服务部署进行控制。

可以实时启动（关机状态的）虚拟机，也可以通过设置「启用定时」，定时（在将来某一时刻）触发此项任务。

#### 挂起（vSphere） {#挂起vsphere .afff6}

挂起（开机状态的）虚拟机，可以通过设置「启用定时」，定时（在将来某一时刻）触发此项任务。

挂起多个（开机状态的）虚拟机，可以通过设置「启用定时」，从而定时（将来某一时刻）触发此项任务。

>「Note」只有vSphere的虚拟机才会有此操作选项。

#### 停止 {#停止 .afff6}

停止（即关机）（开机状态的）虚拟机，可以通过设置「启用定时」，定时（在将来某一时刻）触发此项任务。

#### 重新启动 {#重新启动 .afff6}

重启（开机状态的）虚拟机，可以通过设置「启用定时」，定时（在将来某一时刻）触发此项任务。

重启多个（开机状态的）虚拟机，可以通过设置「启用定时」，定时（在将来某一时刻）触发此项任务。

#### 监控和代理
添加自动化代理
如果云主机未安装自动化代理，可通过该操作安装；输入具有SSH功能并具有管理员权限的用户名和密码/密钥对，输入完成后点击「执行」。若未输入端口，还需在云主机详情页，「云主机中配置的SSH端口」中输入端口号。

更新自动化代理 

如果云主机已安装自动化代理，可通过该操作进行更新。

启用/切换监控 

目前对vSphere云主机支持两种监控方式：内置代理监控以及云平台监控。内置代理监控包括预安装监控代理和WinRM/SSH监控代理（WinRM对于Windows操作系统的云主机，SHH对于Linux操作系统的云主机）；云平台监控是指直接从vCenter上读取虚机的监控数据而不需要安装监控代理。

对Openstack云平台只支持内置监控代理。

更新监控代理 

如果云主机安装了内置代理监控，可通过该操作进行更新。



#### 管理快照
 创建快照

给虚拟机创建一个快照，可以通过设置「启用定时」，定时（在将来某一时刻）触发此项任务。

 恢复至快照

把虚拟机恢复到之前的某一个快照，可以通过设置「启用定时」，定时（在将来某一时刻）触发此项任务

删除快照 

删除已创建的快照

####  更改配置
 调整配置

调整虚拟机或容器节点的配置（vCPU，内存），点击「提交」。

#### 管理磁盘
 添加新磁盘 

给虚拟机添加一块新的磁盘，可以通过设置「启用定时」，定时（在将来某一时刻）触发此项任务。

>「Note」在挂起状态下不能执行该操作

扩展磁盘 

给虚拟机扩展一块已有的磁盘，可以通过设置「启用定时」，定时（在将来某一时刻）触发此项任务。

>「Note」支持通过云管平台部署或在上一小节创建的磁盘进行扩展。在挂起状态下不能执行该操作

 删除磁盘 

删除虚拟机上除系统盘以外的磁盘，包括服务配置添加的磁盘或Day2新增的磁盘，均可删除。

 添加新逻辑卷

给Linux虚拟机添加一个新的逻辑卷，可以通过设置「启用定时」，定时（在将来某一时刻）触发此项任务。

>「Note」在挂起状态下不能执行该操作

扩展逻辑卷

给Linux虚拟机扩展一个已有的逻辑卷，可以通过设置「启用定时」，定时（在将来某一时刻）触发此项任务。

>「Note」支持通过云管平台部署或在上一小节创建的逻辑卷进行扩展。在挂起状态下不能执行该操作

#### vMotion迁移（vSphere） {#vmotion迁移vsphere .afff6}

支持对vSphere
的计算资源迁移和存储迁移。利用vSphere的vMotion迁移功能，使用不同的迁移方式，将虚拟机在不同主机之间进行迁移。

+ 计算资源迁移，选择目标主机，可以通过设置「启用定时」，定时（在将来某一时刻）触发此项任务。

+ 存储迁移：



+ 链接克隆：选择需要存储，将目标云主机迁移到所选的存储中去；

+ 完全克隆：选择置备模式（与源格式相同、精简置备、厚置备延迟置零、后置备置零）；选择虚拟机存储策略（保留现有虚拟机存储策略、数据存储默认值，以及其他自定义存储策略）；存储（根据所选的存储策略判定存储的兼容性，并显示各存储的空间和占比）

+ 启用定时：设置时间在将来某一时刻触发此项任务

>「Note」只有vSphere的虚拟机才会有此操作选项。

#### 远程终端 {#远程终端 .afff6}

>「Note」OpenStack虚拟机远程终端操作需要使用VNC Web Client,
您的浏览器需要支持HTML5 Canvas和HTML5 WebSockets。如果需要了解VNC Web
Client所支持的全部浏览器，可以访问<https://github.com/kanaka/noVNC/wiki/Browser-support>

#### WEB远程终端（vSphere） {#web远程终端vsphere .afff6}

vSphere的Web console client，无需浏览器特别支持。

>「Note」只有vSphere的虚拟机才会有此操作选项。

#### 设置云主机标签 {#设置云主机标签 .afff6}

>「Note」每个用户都可以为云主机设置标签，无需管理员配置操作许可。

可为云主机设置键值标签，从而为云主机分类和过滤。

云主机标签的使用方法如下：

##### 添加标签

+ 对新建的云主机添加标签：

1.  在左侧导航栏选择「我的部署」-「云主机」，在云主机的列表界面，选择一个云主机

2.  点击上方的「更多操作」，「设置标签」，出现键值标签的设置界面

3.  填写键、值，点击「创建」「执行」，标签创建成功；也可选择已有的标签，点击「执行」。在云主机列表的右侧列项，可查看添加的云主机标签

+ 对导入的云主机添加标签：

1.  在左侧菜单选择「基础设施」，点击「资源池管理」，选择一个资源池，进入编辑资源池界面

2.  进入「云主机」页面，点击「导入」

3.  点击「标签」后的输入框，弹出键值标签创建页面，输入键值，创建新标签；也可选择已有标签

##### 修改/删除标签：

在云主机列表界面，选择一个云主机；点击「设置标签」，出现该云主机的键标签，可直接删除并重新创建。

##### 添加网卡

添加一个新网卡，针对该计算节点的所有实例生效，选择网络标签和IP分配方式，目前vSphere只支持DHCP，OpenStack和PowerVC支持DHCP和IP池两种IP分配方式。

##### 删除网卡

删除Day2新增加的网卡，该操作会影响该节点的所有云主机。

##### 挂载NFS

将一个NFS（网络文件系统）挂载到虚拟机，可以通过设置「启用定时」，定时（在将来某一时刻）触发此项任务。

>「Note」当配置NFS云平台和资源池后，此项操作才可用

##### 执行脚本

在该虚拟机中执行一个脚本库的脚本，可以通过设置「启用定时」，定时（在将来某一时刻）触发此项任务，也可选择某个IP地址。

>「Note」如果没有安装代理，执行脚本时必须输入虚机的用户名和密码

##### 更新云主机显示名

点击「更新云主机显示名」，可以重新设置云主机的显示名。

##### 重置操作系统主机名

点击「重置操作系统主机名」，可以重新设置操作系统主机名。

>「Note」windows操作系统只有安装代理的情况下才能进行该项操作

##### 提升Linux用户权限

可临时给某个Linux用户提升一段时间的Sudo权限（免密）。若该云主机已安装自动化代理，则只需输入用户名以及权限使用时间。若该云主机未安装自动化代理，将输入管理员用户名和密码（或选择密钥对）、以及选择IP地址（仅vSphere）。

##### 重置密码

点击「重置密码」，可以重新设置虚拟机的新密码。

##### 其他

云主机运维操作详细界面里，有其他标签页，里面有属于该云主机的「自定义」操作列表，例如「云主机的备份」操作。前提：管理员给当前用户配置了云资源操作许可

云资源
------

云资源菜单下统一纳管所有的云资源，展示其相关信息以及提供各云资源对应的Day2
操作。

点击左侧导航栏「我的部署」-「云资源」，将在左侧看到「存储资源」「容器服务」「网络资源」「PaaS资源」「软件资源」五个菜单。

### 存储资源

#### 云硬盘 {#云硬盘 .afff6}

支持对OpenStack/Azure/阿里云/青云的云硬盘进行统一管理。

1.  点击「存储资源」下的「云硬盘」，将看到云硬盘列表

2.  在云硬盘的列表界面，可查看云硬盘的相关信息：名称、云平台类型、状态、业务组、服务部署、项目、所有者、大小（GB）、挂载状态、挂载到的云主机以及创建时间

3.  点击名称，进入云硬盘详情页面。云硬盘详情页面包括「基本信息」「操作历史」

4.  云硬盘详情的「基本信息」页面包括：

+ 基本信息：名称、云平台类型、状态、业务组、服务部署、项目、所有者、大小挂载到的云主机、创建时间等

+ 组织信息：服务部署名称、服务名称、业务组、租户、项目等

+ 运维操作：卷分离：去除云硬盘和云主机的挂载关系。卷挂载：建立云硬盘和云主机的挂载关系。 调整大小：支持对硬盘调整大小（Azure/AWS）

 云硬盘详情的「操作历史」页面：包括了该云硬盘进行过的操作历史记录

#### 对象存储 {#对象存储 .afff6}

支持对AWS、Azure、阿里云的对象存储进行统一管理，分别是S3、Blob、OSS。

1.  点击「存储资源」下的「对象存储」，将看到对象存储列表

2.  在对象存储的列表界面，可查看对象存储的相关信息：名称、云平台类型、状态、状态、业务组、服务部署、项目、所有者、创建时间

3.  点击名称，进入对象存储详情页面。对象存储详情页面包括「基本信息」「操作历史」

4.  对象存储详情的「基本信息」页面包括： 基本信息：名称、云平台类型、状态、所有者、公共访问级别、存储账户、资源组、创建时间等。 组织信息：服务部署名称、服务名称、业务组、租户、项目等

5.  对象存储详情的「操作历史」页面：包括了该云硬盘进行过的操作历史记录

#### 容器服务 {#容器服务 .afff6}

支持在云资源中展示kubernetes
的各个组件信息，包括部署（Deployment）、容器（Container）、服务（Service）、路由（Ingress）、存储卷（PVC）、配置字典（ConfigMap）、保密字典（Secrets）等。

#### 网络资源 {#网络资源 .afff6}

支持OpenStack的防火墙（FireWall）、浮动IP（Floating
IP）的独立部署和全生命周期管理。部署完成后，可在「云资源」-「网络资源」处查看基本信息和运行状况。还支持OpenStack的负载均衡器（LoadBalance）和负载均衡监听器（Listener）,以及VMware
NSX的虚拟服务器（VirtualServer）。

#### 负载均衡器 {#负载均衡器 .afff6}

若部署中包含负载均衡器（LoadBalancer），则部署成功后可在「云资源」-「网络资源」-「负载均衡器」中查看详细信息。

1.  在负载均衡器（LoadBalancer）列表界面，显示负载均衡器的名称、云平台类型、状态、业务组、服务部署、项目、所有者、IP地址、创建时间等

2.  点击名称进入详情页面，包括「基本信息」「操作历史」

3.  运维操作（OpenStack）：

+ 绑定浮动IP：选择某一浮动IP，将该负载均衡器和浮动IP
    进行绑定，可启动定时在特定时间执行操作

+ 解绑浮动IP：若该负载均衡器已绑定浮动IP，则可进行解绑操作，可启动定时在特定时间执行操作

#### 负载均衡监听器 {#负载均衡监听器 .afff6}

支持VMWare NSX / OpenStack / Azure的负载均衡监听器，VMWare NSX
负载均衡监听器为VirtualServer，OpenStack 负载均衡监听器为Listener，Azure
负载均衡监听器为LoadBalancerRule。负载均衡器可以监听多个端口上请求，每个端口通过负载均衡监听器指定。部署成功后可在「云资源」-「网络资源」-「负载均衡监听器」中查看详细信息。

1.  在负载均衡器监听器（Listener）列表界面，显示负载均衡监听器的名称、状态、描述、业务组、项目、所有者、协议、云平台类型、创建时间等

2.  点击名称进入详情页面，包括「基本信息」「操作历史」界面，以及「添加成员」「删除成员」等Day2

3.  运维操作 -- OpenStack

+ 「添加成员」:添加成员（member），可添加内部成员和外部成员。选择要添加成员的云主机、指定IP地址、端口和权重。可启动定时在特定时间执行操作

+ 「删除成员」：点击后选择需要删除的成员，可启动定时在特定时间执行操作

#### 浮动IP {#浮动ip .afff6}

支持OpenStack的的浮动IP（FloatingIP），FloatingIP可单独部署，部署成功后可在左侧导航栏选择「云资源」-「网络资源」-「浮动IP」中查看详细信息。

1.  在选择「云资源」-「网络资源」-「浮动IP」,可查看已部署成功的浮动IP的列表界面，该界面显示浮动IP的名称、云平台类型、状态、业务组、服务部署、项目、所有者、IP地址、网络、映射地址、创建时间等

2.  点击名称，进入详情页面，包括「基本信息」「操作历史」

3.  「基本信息」页面，显示该浮动IP的的基本信息和组织信息

4.  「操作历史」页面，显示操作历史记录，点击后将在操作历史列表下方显示操作详情

5.  运维操作：

+ 「关联端口」：若当前Floating
    IP未关联任何一个端口，则在详情页上方会显示「关联端口」操作，点击后在弹框中选择需要绑定的端口，下拉框中会列出当前业务组下，OpenStack云平台中所有未被关联的端口（Port）。选择后点击「提交」

+ 「解除绑定」：若当前Floating
    IP已关联端口，则在详情页上方会显示「解除绑定」操作，点击后「提交」，也可启用定时在特定时间执行操作

#### 防火墙 {#防火墙 .afff6}

支持OpenStack防火墙即服务（Firewall as a
service），Fwaas应用于OpenStack对象，如项目，路由器和路由器端口。OpenStack防火墙的核心概念是防火墙策略和防火墙规则。策略是有序的规则集合。可在左侧导航栏选择「云资源」-「网络资源」-「防火墙」查看已部署成功的防火墙。

1.  选择「云资源」-「网络资源」-「防火墙」,可查看已部署成功的防火墙列表界面，该界面显示防火墙的名称、云平台类型、状态、业务组、服务部署、项目、所有者、策略、路由、激活状态、管理员状态、创建时间等

2.  点击名称，进入详情页面，包括「基本信息」「操作历史」

3.  「基本信息」页面：显示该防火墙的的基本信息和组织信息

4.  「操作历史」页面：显示操作历史记录，点击后将在操作历史列表下方显示操作详情

5.  运维操作：

+ 「更新防火墙」：点击后可在页面中选择已有的防火墙策略或新建防火墙策略。勾选「使用已有策略」，将列出当前业务组下，OpenStack云平台中所有可用的防火墙策略。若未勾选，则新建防火墙策略，需填写策略名称（必填），策略描述（选填），可选择是否属于已共享、已审计，还可定时，操作完成后点击「提交」

+ 「更新防火墙策略」：该页面将列出当前所有可用的规则列表。支持使用已有规则和新建规则。若使用已有规则，在列表中勾选将使用的规则即可。若新建规则，将展现新建规则界面，具体操作步骤：

  填写基本信息：名称、描述、协议（必填，TCP、UDP、ICMP和任何）、动作（必填，允许、拒绝）、源IP、源端口、目的IP、目的端口、选择是否是共享的、激活

  可选择新增的规则的位置，指定当前规则在某条规则之前插入（规则前于），或指定规则在某条规则后插入（规则后于）。如果两者均被指定，前者优先级更高。

 >「Note」：一个防火墙策略可关联多个规则，但规则只能被一个策略所关联

+ 「删除防火墙规则」：删除防火墙中已关联的规则，删除后将不可恢复。可同时选择多个规则删除，也可启动定时在特定时间执行操作

#### 安全组 {#安全组 .afff6}

支持展示OpenStack、AWS、Azure、阿里云的安全组。若安全组组件部署后，将在「云资源」-「网络资源」-「安全组」中查看部署的安全组组件。

1.  在「安全组」列表界面，显示安全组名称、云平台类型、状态、所属业务组、服务部署、所属项目、所有者、创建时间等

2.  点击名称进入详情页面，包括「基本信息」「操作历史」界面

3.  「基本信息」页面，显示该安全组的的基本信息、组织信息和入站/出站安全组规则。

4.  「操作历史」页面，显示操作历史记录，点击后将在操作历史列表下方显示操作详情

#### 域名系统DNS {#域名系统dns .afff6}

支持OpenStack域名系统DNS，若DNS组件部署后，将在「云资源」-「网络资源」-「域名系统DNS」中查看部署的DNS组件。

1.  在「域名系统DNS」列表界面，显示DNS名称、状态、业务组、项目、所有者、DNS类型、DNS域、DNS服务器、DNS参数等

2.  点击名称进入详情页面，包括「基本信息」「操作历史」界面

3.  运维操作

+ 「更新DNS」：更新DNS参数，DNS类型不可更改

### PaaS资源

支持AWS、Azure、阿里云的关系型数据库（RDS）的独立部署和全生命周期管理，支持关系型数据库即服务（RDS
as a
Service）。部署完成后，可在「云资源」-「PaaS资源」处查看基本信息和运行状况。

### 软件资源

>「Note」  支持对软件资源的统一展示和管理。

#### 软件 {#软件 .afff6}

1.  选择「云资源」-「软件资源」-「软件」,可查看已部署成功的软件列表，该界面显示软件名称、云平台类型、状态、业务组、服务部署、项目、所有者、版本、系统类型、创建时间等。可通过高级搜索对业务组、状态、项目或所有者进行筛选，也可使用普通搜索进行快速定位

2.  点击名称，进入详情页面，包括「基本信息」「操作历史」

3.  「基本信息」页面：显示该软件的基本信息、组织信息、参数

4.  「操作历史」页面：显示操作历史记录，点击后将在操作历史列表下方显示操作详情

5.  运维操作：

>「Note」  运维操作根据「服务建模」-「软件组件」中对个软件的操作定义显示对应的运维操作，例如：启动、停止、删除、创建、配置等

#资源状态图


资源状态图能够显示云主机、容器的健康状态，根据性能指标的状态显示不同的颜色。若该云主机或容器未配置监控，默认显示灰色。

支持用户将鼠标移至该云主机上，将显示该云主机名称

支持用户点击服务部署名称后显示详情：

+ 基本信息：IP地址、操作系统、vCPU数量、内存、磁盘总空间

+ 组织信息：业务组、项目、所有者

+ 性能监控指标：内存使用率、CPU使用率、磁盘使用率

>「Note」若未安装监控，将不显示性能监控指标

支持用户根据需求对展示内容进行筛选，如全部或已安装监控或未安装监控、按云平台筛选、业务组筛选、项目筛选、标签筛选等。

# 监控告警


监控告警为用户提供了云主机和应用的告警配置自服务。

在左边导航选择「监控告警」，监控告警下有多个二级菜单，依次是「组件监控」「告警策略」「告警」「已触发警报」。

### 组件监控
组件监控作为单独的页面，展示对应用的监控，平台内置了常用的监控代理组件，包括 RedisExporter、 NginxExporter、MySQLExporter 等等，支持管理员添加监控代理组件。
Note	业务组普通用户仅限于查看当前业务组的监控资源。
点击左侧导航栏「监控告警」- 「组件监控」，点击菜单「组件监控」，左侧展现Export组件的树形结构，右侧显示相关的Exporter（用于描述所有的Exporter的组件, 每个组件能定义自己支持的组件类型。） 
例如：点击右侧显示的NginxExporter，进入 「NginxExporter」标签页，页面左侧显示NginxExporter关联的实例，右侧显示NginxExporter组件的相关描述信息。



### 告警策略

用来定义所选的对象类型（如云主机/应用/容器等）触发警报的条件。点击左侧导航「监控告警」下的二级菜单「告警策略」，显示告警策略列表，列表中包括告警策略名称、类别、类型、创建时间以及创建者等。可对告警策略进行添加、编辑、删除等操作。

#### 添加告警策略 {#添加告警策略 .afff6}

1.  在左侧导航选择「告警策略」，进入告警策略列表界面，点击「添加」，进入添加告警策略界面

2.  在添加告警策略界面，定义告警策略的基本信息。依次输入告警策略的名字，选择告警类别和告警类型。告警类别支持对云主机、应用和容器的告警。告警类型支持对云主机的宕机告警、阈值告警和预测告警，支持对应用的阈值告警和预测告警，对容器的阈值和预测告警

3.  根据选择的不同告警类型定义告警策略的触发条件

+ 宕机告警：输入时间（分钟），云主机在规定时间内失去响应后，将触发宕机警报

+ 阈值告警：选择云主机/容器的xx指标（如内存使用（百分比）、CPU使用率（百分比）、POD内存使用等）的取最大值/最小值/平均值，在过去xx时间（分钟/小时），若该值小于/小于等于/大于/大于等于xx值后，将触发警报

+ 预测告警：基于过去xx时间（分钟/小时/天）内的xx指标的值（如内存使用（百分比）、CPU使用率（百分比）等），预测未来xx时间（分钟/小时/天）内，若该指标的值小于/小于等于/大于/大于等于xx值后，将触发警报

4.  点击「保存」，提示告警策略添加成功，返回告警策略列表界面

#### 编辑告警策略 {#编辑告警策略 .afff6}

点击「告警策略」，选择一行已添加的告警策略，工具栏「编辑」按钮变成可用，点击「编辑」按钮，或者直接点击告警策略名称，进入告警策略编辑界面。

#### 删除告警策略 {#删除告警策略 .afff6}

点击「告警策略」，选择一行已添加的告警策略，工具栏「删除」按钮变成可用，点击「删除」按钮，确认删除提示后，提示告警策略删除成功。

### 告警

支持用户定义所选告警策略应用到的范围以及触发的通知和操作。

点击左侧导航「监控告警」下的二级菜单「告警」，显示告警列表，包括告警名称、警报级别、告警策略名称、范围、对象、状态、创建时间、创建者等。可对告警进行添加、编辑、启用、禁用、删除等操作。

#### 添加告警 {#添加告警 .afff6}

1.  在左侧导航选择「告警」，点击「添加」，进入添加告警界面

2.  定义告警的基本信息。输入告警的名字，选择告警策略、告警范围、告警对象以及警报级别，触发xx次后，自动升级为更高级别。告警范围支持对租户、业务组、项目、服务部署和云主机的告警；告警对象依据所选的告警范围；告警级别为警告和危险

3.  定义触发告警后，通知到的用户、角色或邮件

4.  可定义警报触发后的行为，触发行为后，可设置最多xx次操作后停止自动执行

+ 支持云主机的扩展操作：横向收缩一个节点、横向扩展一个节点、关机、重新启动、扩展5G逻辑卷、增加1G内存（vSphere）、增加1个vCPU（vSphere）

+ 支持对容器的扩展操作：减少3个副本数、增加2个副本数

 点击「保存」，返回告警列表界面

### 已触发警报

点击左侧导航「监控告警」下的二级菜单「已触发警报」，显示已触发警报列表，包括警报级别、告警名称、触发告警对象、告警类型、第一次触发时间、最后一次触发时间、已触发次数以及告警状态。告警状态分为已触发、已暂停、已解除。还可对列表中的触发警报进行恢复、暂停、解除操作。

1.  选择「已触发警报」，任意选择一条「已触发」的警报，工具栏中的「暂停」和「解除」将变为可用，点击「暂停」，将会有提示，确认后，提示操作成功

2.  点击列表中的告警名称，可查看该警报的详细信息以及历史数据。该页显示了告警触发的对象、警报的级别，触发的条件、业务组、所有者、IP地址、警报图表（可调控时间范围灵活查看各个时间段的警报数据）、以及该告警的后续操作历史

3.  告警触发的对象可链接，如服务部署链接至服务部署监控页面、云主机链接至云主机监控页面、应用链接至服务部署监控页面

#资源分析


### 报表

您可以在「资源分析」-「报表」中，查看相关的计费报表以及云主机总体情况报表或其他自定义报表。在「系统管理」-「报表配置」中，可针对不同用户角色，选择启用或禁用某一报表。支持对报表的多个维度的筛选条件以及表头的展示列选择，可导出Excel。

>「Note」报表的自定义配置请咨询骞云工程师

# 回收站


所有的服务手工卸除或者到期后自动卸除后，将放置到回收站中进行保留，支持用户需要时可进行恢复。具体操作步骤请参考：[回收站](https://cloudchef.github.io/doc/UserDoc/01快速上手/#回收站)
