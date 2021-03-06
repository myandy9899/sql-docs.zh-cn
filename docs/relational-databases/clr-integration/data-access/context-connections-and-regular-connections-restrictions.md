---
title: 对常规连接和上下文连接的限制 |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- context connections [CLR integration]
- regular connections [CLR integration]
ms.assetid: 0c6fe4cb-d846-40b5-8884-35a9c770f5e8
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 800ec59fb837b167b1bcbffc61ddf7e8ce695849
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "47641785"
---
# <a name="context-connections-and-regular-connections---restrictions"></a>上下文连接和常规连接 - 限制
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  本主题讨论中执行的代码相关的限制[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]进程通过上下文和常规连接。  
  
## <a name="restrictions-on-context-connections"></a>对上下文连接的限制  
 开发应用程序时，请考虑应用于上下文连接的以下限制：  
  
-   对于给定的连接，在给定的时间，您只能打开一个上下文连接。 如果有多个语句并发运行在单独的连接中，则其中的每个语句都可以获得自己的上下文连接。 此限制不影响来自不同连接的并发请求；它只影响对给定连接的给定请求。  
  
-   上下文连接中不支持多个活动结果集 (MARS)。  
  
-   **SqlBulkCopy**类不对上下文连接中进行操作。  
  
-   不支持上下文连接中的更新批处理  
  
-   **SqlNotificationRequest**不能用于对上下文连接执行的命令。  
  
-   不支持取消正在对上下文连接运行的命令。 **SqlCommand.Cancel**方法以无提示方式忽略请求。  
  
-   使用“context connection=true”时，不能使用任何其他连接字符串关键字。  
  
-   **SqlConnection.DataSource**属性返回的连接字符串的情况下为 null **SqlConnection**是"上下文连接 = true"，而不是实例名称[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]。  
  
-   设置**SqlCommand.CommandTimeout**属性不起作用时对上下文连接执行命令。  
  
## <a name="restrictions-on-regular-connections"></a>对常规连接的限制  
 开发应用程序时，请考虑应用于常规连接的以下限制：  
  
-   不支持对内部服务器异步执行命令。 包括"async = true"在连接字符串的命令，然后再执行该命令中，会导致**System.NotSupportedException**所引发。 将出现此消息：“在 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 进程内运行时，不支持异步处理。”  
  
-   **SqlDependency**不支持对象。  
  
## <a name="see-also"></a>请参阅  
 [上下文连接](../../../relational-databases/clr-integration/data-access/context-connection.md)  
  
  
