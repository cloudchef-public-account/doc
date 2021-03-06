

**工单服务管理**

工单服务场景：
工单是用户提交多种类型服务请求的方式，支持提交云资源蓝图服务工单和手工服务工单。

租户管理员可自定义和发布标准的工单服务，用户可通过服务目录进行自服务申请与通过服务请求跟踪工单处理状态。

具体工单服务场景请参照以下步骤：

1.  [设置服务团队](#设置服务团队)：租户管理员自定义关联用户。

2.  [定义手工工单服务流程](#定义手工工单服务流程)：平台提供开箱即用的默认流程（标准手工工单、标准事件管理流程），当租户管理员有额外需求可通过「服务建模」-「流程配置」-「流程设计」通过可视化的流程设计器，自定义设计服务处理的方法和策略，添加到SmartCMP中使用。

3.  [手工工单服务配置](#手工工单服务配置)：租户管理员定义服务流程和处理工单任务的服务团队角色或用户。配置完成后，发布到服务目录，使得业务组中的用户可在服务目录进行工单的申请。

4.  [申请工单和跟踪进度](#申请和处理工单)：用户申请工单完成后，根据预先配置的流程，系统根据服务团队与工单的关系，派发工单给相应的服务团队。服务团队中的指定用户或角色收到工单请求之后，可以进行转派，也可以进行线下处理，完成之后更新工单状态，系统通过邮件通知用户，用户可进行关闭操作或申请重新处理工单操作。

# 设置服务团队{#设置服务团队}


服务团队是工单服务管理过程中处理工单任务的服务人员集合，支持租户管理员自定义关联用户。

>「Note」组织架构管理已经对服务团队进行了详细的介绍，如您需要设置服务团队，请您参考[服务团队](https://cloudchef.github.io/doc/AdminDoc/04组织架构管理/服务团队.html)

# 定义手工工单服务流程{#定义手工工单服务流程}


服务团队建立完成之后，通过服务配置创建工单，将工单发布到服务目录，完成服务卡片的发布和服务目录的管理。以下内容将为您详细介绍配置手工工单服务流程、配置手工工单服务和发布手工工单服务的具体步骤。

### 自定义添加手工工单服务流程

在左侧导航栏点击「服务建模」-「服务流程管理」，点击添加，输入名称（手工工单服务流程）、描述、选择类别（手工工单服务）、上传流程配置文件。

### 内置的手工工单服务流程

平台内置的手工工单服务流程包括标准手工工单，标准事件管理流程、自动化服务流程。

+ 标准事件管理流程，用来解决出现IT资源相关的问题，例如：服务器意外关闭，网络出现中断问题等等，网络IP地址冲突等等。流程类型属于手工工单服务。
+ 标准手工工单：需要IT人工介入的服务，例如：申请重新设置密码的手工工单服务。
+ 自动化服务流程：用户申请手工工单服务，服务通过审批之后，自动化创建用户申请的资源，例如：创建项目，创建IP池，等等。

>「Note」内置的手工工单服务流程，不支持修改和删除，只支持查看和使用，用户自定义添加的手工工单服务流程支持修改和删除

# 手工工单服务配置{#手工工单服务配置}


管理员可以将设计好的工单发布为服务，管理员可以将服务与企业内部的流程集成之后发布到服务目录。服务项主要功能有：

服务与指定服务团队关联，服务请求由团队关联的用户来处理，即指定服务团队，发布工单到不同部门服务与流程配置相关联，平台支持管员自定义服务流程，同时支持使用内置的服务流程

### 添加手工工单服务配置 {#添加手工工单服务配置 .afff6}

您可以根据下面步骤添加手工工单服务配置：

1.  在左边导航栏选择「服务建模」-「服务配置」，点击「添加」

 填写服务名称、服务描述（选填）、选择业务组，服务类型为手工工单服务时，增选一项服务流程，点击「提交」，进入服务配置「概况」页面

 + 在「基本信息」标签页填入下列信息：名称，描述，logo图像，服务分组，顺序

 + 在「审批配置」页面指定审批流程，例如，申请创建新项目的手工工单服务，您可以指定租户管理员审批的审批流程。
 + 在「流程配置」页面指定服务处理阶段需要指派合适的人去完成任务，指定服务确认关闭阶段需要申请人判断问题是否得到解决，配置处理人类型并根据类型选择处理人的详细信息（例如：处理人类型选择服务团队，并进一步选择具体哪一个服务团队）

 + 在「表单配置」页面指定创建的表单，例如，申请创建新项目的手工工单服务，您可选择创建项目的表单。

2. 点击保存按钮，服务将被保存不发布，点击保存并发布按钮，服务将被发布到服务目录页面。

### 编辑、删除手工工单服务配置 {#编辑删除手工工单服务配置 .afff6}

在左侧导航栏点击「服务建模」-「服务配置」，选择一个服务配置，点击「编辑」按钮，输入需要修改的内容，点击「保存」。

在左侧导航栏点击「服务建模」-「服务配置」，选择一个服务配置，点击「删除」按钮，提示删除服务配置成功。

### 发布、取消发布手工工单服务配置 {#发布取消发布手工工单服务配置 .afff6}

在左侧导航栏点击「服务建模」-「服务配置」，选择一个服务配置，点击「发布」按钮，提示发布成功。

在左侧导航栏点击「服务建模」-「服务配置」，选择一个服务配置，点击「取消发布」按钮，提示取消发布服务配置成功。

# 申请和处理工单{#申请和处理工单} 


工单的全生命周期可以管控和记录工单全过程，包括工单服务配置、工单申请、工单处理和实时查看服务进展。

当用户在服务目录申请工单完成后，根据预先配置的流程，系统将根据工单与服务团队的关联关系，派发工单给相应的服务团队进行处理。

服务团队中的指定人员收到工单请求之后，可以进行转派，也可以进行线下处理，完成之后更新工单状态，系统自动通知用户，也支持用户查看处理进程。

用户可在服务目录申请业务组发布的、已配置好的服务和共享的服务，其中服务类型包括两种类型：其一是手工工单服务，其二是云资源蓝图服务。服务申请完成，该服务信息可进入我的请求列表页面查看，稍后为您介绍我的请求详细信息。

### 我的请求 {#我的请求}

选择某一个手工工单服务，点击进入手工工单服务信息详情页。输入服务基本信息：标题，描述，优先级，紧急程度，申请者信息必填项的手机号，点击申请即可申请服务成功。服务申请成功之后，服务申请状态变更为处理中，申请进入我的请求当中。

用户可根据以下步骤查看用户自己已经申请的工单和跟踪工单处理进程：

1.  在左侧导航栏点击「服务请求」-「我的请求」，我的请求页面显示我的请求的基本信息：请求编号，请求类型，标题，服务名称，业务组，项目，申请状态，申请时间，完成时间。

2.  选择任意手工工单服务的服务请求，点击「请求编号」链接，跳转到我的手工工单服务请求详情页面，可查看该请求的基本信息，工单信息，处理记录，审批流程，审批记录等。

3.  审批流程：审批流程图，审批层级、审批人、角色；审批记录：审批流程信息、审批流程名称、状态、审批意见、审批人、审批角色、审批时间

4.  基本信息包括请求编号，申请时间，请求类型，申请者，联系方式，邮箱，业务组，项目等。

5.  工单信息包括标题，描述，优先级，紧急程度，表单配置的字段信息。

6.  处理记录信息：流程步骤，描述，处理结果描述、处理状态和处理人、处理时间。

### 所有请求 {#所有请求}

租户管理员还可以根据以下步骤查看所有用户的服务工单：

1.  在左侧导航栏点击「服务请求」-「所有请求」，所有请求页面显示所有请求的基本信息：请求编号，请求类型，部署名称、申请者、业务组，项目，申请状态，申请时间，完成时间、审批者。

2.  请求类型包括手工工单请求、云资源蓝图部署、Day2操作，不同请求类型展示的详情页面稍显不同，具体您参考：[我的请求](#我的请求)。

3.  在服务请求列表页面，支持您快速定位到您需要查看的服务请求，您可以通过状态（服务请求的审批状态：审批未开始、审批中、审批通过、拒绝、退回、错误、撤回），业务组、起止时间（服务请求的起止时间）或关键字搜索框快速定位。

### 待处理 {#待处理}

此处显示等待服务团队处理的服务请求

1.  在左侧导航栏点击「服务请求」-「待处理」，待处理页面显示发起的所有处理请求其中待处理部分，其中显示处理请求的基本信息：请求编号，服务名称，请求类型，标题，业务组，项目，申请状态，申请时间，完成时间。

2.  选择一个待处理的服务请求，点击「请求编号」链接，跳转到请求详情页面，查看该请求的基本信息，工单信息，处理记录，流程步骤，服务处理信息等。

3.  基本信息包括申请编号，申请时间，申请类型，申请者，联系方式，邮箱，业务组，项目等。工单信息包括名称，描述，优先级，紧急程度和表单配置的字段信息。

4.  处理记录包括流程步骤、描述、处理结果描述、状态、处理人、处理时间。

5.  流程步骤：

 + 发起申请：服务申请者通过服务目录发起手工工单服务，等待服务团队处理

 + 服务处理：需要指派合适的人去完成这项工单任务

 + 重新处理：申请人判断问题没有得到圆满的解决，选择将服务返回给服务人员进行处理

 + 确认关闭：申请人判断问题已经得到圆满的解决，则关闭服务

6.  处理方式：直接处理和转派处理

 + 选择直接处理方式，点击直接处理，填上处理结果描述，即可点击提交处理，点击页面下方提交按钮即可处理完成此次服务请求，邮件通知服务申请者，申请者进行工单关闭操作，则服务请求状态变更为「已处理」。

 + 选择转派处理方式，点击转派，选择服务团队，处理人和转派说明，点击页面下方提交按钮即可处理完成此次服务请求，服务请求状态「处理中」。

### 已处理 {#已处理}

此处显示服务团队已经处理完成并且申请人已经确认关闭服务的请求。

1.  在左侧导航栏点击「服务请求」-「已处理」，页面显示发起的所有处理请求其中已处理部分

2.  显示处理请求的基本信息：请求编号，请求类型，服务名称，标题，申请者，业务组，项目，申请状态，申请时间，完成时间

3.  选择一个请求，点击「请求编号」链接，跳转到我的请求详情页面，可查看该请求的基本信息，工单信息，处理记录。
