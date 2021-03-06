---
title: 管理事件 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- event forwarding servers [SQL Server]
- events [SQL Server], forwarding
- event-triggered jobs [SQL Server]
- forwarding events [SQL Server]
- alerts [SQL Server], forwarded events
- alerts [SQL Server], management servers
- SQL Server Agent alerts, management servers
ms.assetid: 8f4ee7f5-80df-49fd-b2b8-d020e04b6e1b
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: ed78d5ff91d09f9d8370eef31fd3a6651b301a38
ms.sourcegitcommit: f7fced330b64d6616aeb8766747295807c92dd41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "63188219"
---
# <a name="manage-events"></a>管理事件
  可以将达到或超过特定错误严重级别的所有事件消息转发到 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例。 这称为“事件转发”。 转发服务器是一台专用服务器，同时也可以是一台主服务器。 可以利用事件转发对一组服务器进行集中警报管理，从而减少负荷较重的服务器的工作负荷。  
  
 如果一台服务器收到另外一组服务器的事件，则接收事件的服务器称为“警报管理服务器”。 在多服务器环境下，可以将主服务器指定为警报管理服务器。  
  
## <a name="advantages-of-using-an-alerts-management-server"></a>使用警报管理服务器的优点  
 设置警报管理服务器的优势包括：  
  
-   **集中性**。 可以从单台服务器对多个 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例的事件进行集中控制，并获得这些事件的合并视图。  
  
-   **可伸缩性** 许多物理服务器可以作为一台逻辑服务器来管理。 可以根据需要在这个物理服务器组中添加或删除服务器。  
  
-   **高效性**。 由于只需要定义一次警报和操作员，因此减少了配置时间。  
  
## <a name="disadvantages-of-using-an-alerts-management-server"></a>使用警报管理服务器的缺点  
 设置警报管理服务器的缺点包括：  
  
-   **通信流量增加**。 向警报管理服务器转发事件会增加网络通信流量。 可以通过将事件转发限于超过指定严重级别的事件来缓解这种通信流量增加。  
  
-   **单个故障点**。 如果警报管理服务器离线，则不会为管理的一组服务器中的任何事件发出警报。  
  
-   **服务器负荷**。 处理转发事件的警报会导致警报管理服务器上的处理负荷增加。  
  
## <a name="guidelines-for-using-an-alerts-management-server"></a>警报管理服务器使用准则  
 配置警报管理服务器时，请遵循以下准则：  
  
-   为了接收转发的事件，警报管理服务器必须是 SQL Server 的默认实例。  
  
-   避免在警报管理服务器上运行非常重要或负荷较重的应用程序。  
  
-   针对配置多台服务器共享同一台警报管理服务器时涉及的网络通信流量进行仔细计划。 如果发生阻塞，应减少特定警报管理服务器管理的服务器的数目。  
  
     在 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 中注册的服务器组成一个列表，作为候选的警报转发服务器。  
  
-   对于要求有服务器特定的响应的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 本地实例，定义相应警报，而不是将警报转发给警报管理服务器。  
  
     警报管理服务器将所有向其转发事件消息的服务器当作一个逻辑整体看待。 例如，警报管理服务器响应发自服务器 A 的 605 事件的方式和发自服务器 B 的 605 事件相同。  
  
-   配置了警报系统后，定期检查 Microsoft Windows 应用程序日志中的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 代理事件。  
  
     警报引擎遇到的失败情况都使用源名称“SQL Server 代理”写入本地 Windows 应用程序日志中。 例如，如果 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 代理无法按照定义发出电子邮件通知，则应用程序日志会记录一个事件。  
  
 如果一个本地定义的警报处于禁用状态时，发生了本来会触发该警报的事件，则该事件被转发给警报管理服务器（如果它满足警报转发条件）。 这种转发允许本地站点的用户按照需要禁用和启用本地替代警报（即同时也在警报管理服务器上定义的本地定义的警报）。 您也可以要求总是转发事件，即使它们也是由本地警报处理。  
  
 以下是在多服务器环境中管理事件的常规任务：  
  
 **指定警报管理服务器**  
  
-   [SQL Server Management Studio](../sql-server-management-studio-ssms.md)  
  
 **定义对警报的响应**  
  
-   [SQL Server Management Studio](define-the-response-to-an-alert-sql-server-management-studio.md)  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql)  
  
## <a name="running-event-triggered-jobs"></a>运行事件触发的作业  
 可以定义一个响应警报时执行的作业。 例如，可以执行一个作业，对警报检测出的问题进行更正或做进一步的诊断。  
  
> [!NOTE]  
>  由于作业会导致发生事件，应注意不要创建递归的警报作业循环。  
  
## <a name="see-also"></a>请参阅  
 [sys.sysmessages &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysmessages-transact-sql)  
  
  
