---
title: 安装升级顾问 |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- Setup [Upgrade Advisor]
- Upgrade Advisor [SQL Server], installing
ms.assetid: 1b7d6eca-1df1-47df-bbba-0fc485706a95
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 82db1c6f36d8b03d2a603c0a616090ec9d3544af
ms.sourcegitcommit: 334cae1925fa5ac6c140e0b2c38c844c477e3ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2018
ms.locfileid: "53353992"
---
# <a name="installing-upgrade-advisor"></a>安装升级顾问
  安装 SQL Server 2014 升级顾问的位置取决于你将分析的内容。 升级顾问支持对除 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 之外的所有 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]组件进行远程分析。 如果您不打算扫描的实例[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]，可以在任何可以连接到的计算机上安装升级顾问[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]，且满足[升级顾问的前提条件](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md)。 如果要扫描 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]实例，则必须在报表服务器上安装升级顾问。  
  
 运行 **SQLUA.msi** 文件以安装升级顾问。 对于无人参与的安装和自动安装，你可以从命令提示符进行安装。 有关语法和示例，请参阅 [Installing Upgrade Advisor from the Command Prompt](../../../2014/sql-server/install/installing-upgrade-advisor-from-the-command-prompt.md) 。  
  
 获取 SQLUA.msi：  
  
-   在 **产品媒体的** redist [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 文件夹中。  
  
-   作为 [SQL 2014 功能包下载](https://www.microsoft.com/download/details.aspx?id=42295)的一部分。  
  
## <a name="uninstalling-upgrade-advisor"></a>卸载升级顾问  
 您可以使用 **“添加或删除程序”** 来卸载升级顾问。 命令提示符语法还支持删除/卸载。  
  
  
