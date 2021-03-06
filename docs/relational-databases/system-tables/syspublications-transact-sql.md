---
title: syspublications (TRANSACT-SQL) |Microsoft Docs
ms.custom: ''
ms.date: 03/17/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- syspublications
- syspublications_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- syspublications system table
ms.assetid: a86eb4f5-1f7b-493e-af55-3d15cf878228
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: ed5e46a5bfb9b4c4081eb2df7d4f93b7dd12b29f
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2018
ms.locfileid: "52822931"
---
# <a name="syspublications-transact-sql"></a>syspublications (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  数据库内定义的每个发布在表中对应一行。 该表存储在发布数据库中。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**description**|**nvarchar(255)**|发布的说明项。|  
|**名称**|**sysname**|与发布关联的唯一名称。|  
|**pubid**|**int**|为发布提供唯一 ID 的标识列。|  
|**repl_freq**|**tinyint**|复制频率：<br /><br /> **0** = 基于事务。<br /><br /> **1** = 计划表刷新。|  
|**status**|**tinyint**|状态：<br /><br /> **0** = 非活动状态。<br /><br /> **1** = 活动。|  
|**sync_method**|**tinyint**|同步方法包括：<br /><br /> **0** = 本机模式大容量复制程序实用程序 (**BCP**)。<br /><br /> **1** = 字符模式 BCP。<br /><br /> **3** = 并发，这意味着，使用本机模式 BCP，但在快照期间不锁定表。<br /><br /> **4** = Concurrent_c，表示使用字符模式 BCP，但在快照期间不锁定表。|  
|**snapshot_jobid**|**binary(16)**|预定任务 ID。|  
|**independent_agent**|**bit**|指定是否存在用于此发布的独立分发代理。<br /><br /> **0** = 发布使用共享的分发代理，并且每个发布服务器数据库/订阅服务器数据库对具有单一的共享代理。<br /><br /> **1** = 没有用于此发布的独立分发代理。|  
|**immediate_sync**|**bit**|指示同步文件是创建还是重新创建每次运行快照代理，其中**1**意味着每次运行代理时创建它们。|  
|**enabled_for_internet**|**bit**|指示是否通过文件传输协议 (FTP) 和其他服务，向 Internet 公开发布的同步文件位置**1**意味着可以从 Internet 访问它们。|  
|**allow_push**|**bit**|指示是否对该发布允许推送订阅其中**1**允许它们的方式。|  
|**allow_pull**|**bit**|指示是否对该发布允许请求订阅其中**1**允许它们的方式。|  
|**allow_anonymous**|**bit**|指示是否对该发布允许匿名订阅其中**1**允许它们的方式。|  
|**immediate_sync_ready**|**bit**|指示快照代理是否已生成快照且该快照是否准备好用于新的订阅。 仅对于立即更新发布才有意义。 **1**指示快照已准备好。|  
|**allow_sync_tran**|**bit**|指定是否对该发布允许立即更新订阅。 **1**意味着允许立即更新订阅。|  
|**autogen_sync_procs**|**bit**|指定是否在发布服务器中为立即更新订阅生成同步存储过程。 **1**表示生成在发布服务器。|  
|**保留期**|**int**|为给定发布保存的更改数量（小时）。|  
|**allowed_queued_tran**|**bit**|指定是否启用在订阅服务器上对更改进行排队，直到更改可以在发布服务器上应用为止。 如果**1**，则订阅服务器上的更改进行排队。|  
|**snapshot_in_defaultfolder**|**bit**|指定是否在默认文件夹中存储快照文件。<br /><br /> **0** = 快照文件已存储在指定的备用位置*alternate_snapshot_folder*。<br /><br /> **1** = 快照可以在默认文件夹中找到文件。|  
|**alt_snapshot_folder**|**nvarchar(255)**|指定快照的备用文件夹的位置。|  
|**pre_snapshot_script**|**nvarchar(255)**|指定一个指向 **.sql**文件位置。 在订阅服务器上应用快照时，分发代理将在运行任何复制的对象脚本之前运行快照前脚本。|  
|**post_snapshot_script**|**nvarchar(255)**|指定一个指向 **.sql**文件位置。 在初始同步过程中，分发代理将在应用所有其他复制的对象脚本和数据之后运行快照后脚本。|  
|**compress_snapshot**|**bit**|指定写入到的快照*alt_snapshot_folder*位置是将压缩成[!INCLUDE[msCoName](../../includes/msconame-md.md)]CAB 格式。**1**意味着将压缩的快照。|  
|**ftp_address**|**sysname**|分发服务器的 FTP 服务的网络地址。 指定发布快照文件所在的位置以供分发代理拾取。|  
|**ftp_port**|**int**|分发服务器的 FTP 服务的端口号。 指定供分发代理拾取的发布快照文件的位置|  
|**ftp_subdirectory**|**nvarchar(255)**|指定当发布支持使用 FTP 传播快照时的快照文件的位置以供分发代理获取。|  
|**ftp_login**|**sysname**|用于连接到 FTP 服务的用户名。|  
|**ftp_password**|**nvarchar(524)**|用于连接到 FTP 服务的用户密码。|  
|**allow_dts**|**bit**|指定发布是否允许数据转换。 **1**指定允许 DTS 转换。|  
|**allow_subscription_copy**|**bit**|指定是否已启用复制订阅该发布的订阅数据库的功能。 **1**意味着允许复制。|  
|**centralized_conflicts**|**bit**|指定冲突记录是否存储在发布服务器上：<br /><br /> **0** = 均存储的冲突记录的发布服务器和订阅服务器导致冲突。<br /><br /> **1** = 的冲突记录存储在发布服务器。|  
|**conflict_retention**|**int**|指定冲突保持期（天）。|  
|**conflict_policy**|**int**|指定使用排队更新订阅服务器选项时遵循的冲突解决策略。 可以是下列值之一：<br /><br /> **1** = 发布服务器入选冲突。<br /><br /> **2** = 订阅服务器入选冲突。<br /><br /> **3** = 重新初始化订阅。|  
|**queue_type**|**int**|指定所使用的队列类型。 可以是下列值之一：<br /><br /> **1** = msmq，使用[!INCLUDE[msCoName](../../includes/msconame-md.md)]消息队列来存储事务。<br /><br /> **2** = sql，它使用[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]来存储事务。<br /><br /> 注意：因为已不推荐使用 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 消息队列，所以此方式不再可用。|  
|**ad_guidname**|**sysname**|指定是否在 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Active Directory 中发布该发布。 有效的全局唯一标识符 (GUID) 指定 Active Directory 中发布该发布，GUID 是相应的 Active Directory 发布对象**objectGUID**。 如果为 NULL，则将不在 Active Directory 中发布该发布。|  
|**backward_comp_level**|**int**|数据库兼容性级别，可以是下列值之一：<br /><br /> **90** = [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].<br /><br /> **100** = [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].<br /><br /> **110** = [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].<br /><br /> **120** = [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].|  
|**allow_initialize_from_backup**|**bit**|指示订阅服务器是否可以从备份而不是初始快照对此发布初始化的订阅。 **1**意味着可以从备份初始化订阅并**0**表示不能。 有关详细信息，请参阅 [初始化事务订阅（不使用快照）](../../relational-databases/replication/initialize-a-transactional-subscription-without-a-snapshot.md)中手动初始化订阅。|  
|**min_autonosync_lsn**|**binary**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**replicate_ddl**|**int**|指示发布是否支持架构复制。 **1**指示复制在发布服务器上执行数据定义语言 (DDL) 语句是的并**0**指示不复制 DDL 语句。 有关详细信息，请参阅[对发布数据库进行架构更改](../../relational-databases/replication/publish/make-schema-changes-on-publication-databases.md)。|  
|**options**|**int**|指定其他发布选项的位图，其中的位选项值如下所示：<br /><br /> **0x1** -对等复制启用。<br /><br /> **0x2** -仅发布本地更改为对等复制。<br /><br /> **0x4** -对启用非-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]订阅服务器。<br /><br /> **0x8** -启用对等冲突检测。|  
|**originator_id**|**smallint**|为进行冲突检测标识对等复制拓扑中的每个节点。 有关详细信息，请参阅 [Conflict Detection in Peer-to-Peer Replication](../../relational-databases/replication/transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md)。|  
  
## <a name="see-also"></a>请参阅  
 [复制表&#40;Transact SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [复制视图&#40;Transact SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)   
 [sp_addpublication &#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addpublication-transact-sql.md)   
 [sp_changepublication (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-changepublication-transact-sql.md)   
 [sp_helppublication &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-helppublication-transact-sql.md)  
  
  
