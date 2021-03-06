---
title: 断开用户连接和会话上 Analysis Services 服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
helpviewer_keywords:
- ending user activity [Analysis Services]
- connections [Analysis Services]
- sessions [Analysis Services]
ms.assetid: 3b0145a2-f21d-4dd0-a09e-83afeb2ff4a9
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 4b188554ddbfba6d70ba1d869987aa96efd42f83
ms.sourcegitcommit: f7fced330b64d6616aeb8766747295807c92dd41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62703481"
---
# <a name="disconnect-users-and-sessions-on-analysis-services-server"></a>断开 Analysis Services 服务器上用户和会话的连接
  作为工作负荷管理的一部分， [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 管理员可能需要结束用户活动。 可以通过取消会话和连接来完成这一任务。 会话可以在运行查询时隐式自动形成，也可以在创建会话时由管理员显式命名。 连接是开放的管道，可以通过连接运行查询。 会话和连接均可在处于活动状态时结束。 例如，如果会话处理时间过长，或者对正在执行的命令是否被正确写入产生了怀疑，管理员可能要结束对会话的处理。  
  
## <a name="ending-sessions-and-connections"></a>结束会话和连接  
 若要管理会话和连接，您可以使用动态管理视图 (DMV) 和 XMLA：  
  
1.  在 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]中，连接到 Analysis Services 实例。  
  
2.  将以下任一个 DMV 查询粘贴到 MDX 查询窗口中，以获取当前正在执行的所有会话、连接和命令的列表：  
  
     `Select * from $System.Discover_Sessions`  
  
     `Select * from $System.Discover_Connections`  
  
     `Select * from $System.Discover_Commands`  
  
3.  按 F5 执行该查询。  
  
     DMV 查询以易于读取和复制的表格结果集返回会话和连接信息。  
  
 保持查询窗口处于打开状态。 在下一步骤中，你将希望返回至本页以复制你要断开连接的会话的 SPID。  
  
 若要结束会话，请打开另一个 XMLA 查询窗口。  
  
1.  将以下语法粘贴到 MDX 查询窗口中，用从上一步中复制的有效值替换 ConnectionID、SessionID 或 SPID 占位符。  
  
    ```  
    <Cancel xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  
       <ConnectionID>111</ConnectionID>  
       <SessionID>222</SessionID>  
       <SPID>333</SPID>  
  
    <CancelAssociated>1</CancelAssociated>  
    </Cancel>  
  
    ```  
  
2.  按 F5 执行取消命令。  
  
 结束连接将取消所有会话和 SPID，从而结束主机会话。  
  
 结束会话将停止会话中运行的所有命令 (SPID)。  
  
 结束 SPID 将取消特殊命令。  
  
 如果 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 无法跟踪与连接关联的所有会话和 SPID（例如当 HTTP 方案中打开了多个会话时），则不会关闭连接，这种情况十分少见。  
  
 有关本主题中引用的 XMLA 的详细信息，请参阅[执行方法 (XMLA)](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) 和[取消元素 (XMLA)](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla)。  
  
## <a name="see-also"></a>请参阅  
 [管理连接和会话 (XMLA)](../multidimensional-models-scripting-language-assl-xmla/managing-connections-and-sessions-xmla.md)   
 [BeginSession 元素 (XMLA)](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/beginsession-element-xmla)   
 [EndSession 元素 (XMLA)](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/endsession-element-xmla)   
 [Session 元素 (XMLA)](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/session-element-xmla)  
  
  
