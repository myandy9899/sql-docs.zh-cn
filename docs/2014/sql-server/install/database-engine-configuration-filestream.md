---
title: 数据库引擎配置-Filestream |Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], about FILESTREAM
ms.assetid: 641a10a1-ae52-4d26-8f1c-a032a4aeff02
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 190a6ce588ed40ab7cc9181476ca3730eeef34b5
ms.sourcegitcommit: f7fced330b64d6616aeb8766747295807c92dd41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "63035626"
---
# <a name="database-engine-configuration---filestream"></a>数据库引擎配置 - 文件流
  使用此页可针对此 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]安装启用 FILESTREAM。 FILESTREAM 使[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]使用 NTFS 文件系统通过将存储`varbinary(max)`二进制大型对象 (BLOB) 数据作为文件系统上的文件。 [!INCLUDE[tsql](../../includes/tsql-md.md)] 语句可插入、更新、查询、搜索和备份 FILESTREAM 数据。 通过 Win32 文件系统接口可以流式方式访问数据。  
  
## <a name="uielement-list"></a>UIElement 列表  
 **针对 Transact-SQL 访问启用 FILESTREAM**  
 选中此项可针对 [!INCLUDE[tsql](../../includes/tsql-md.md)] 访问启用 FILESTREAM。 必须选中此控制选项，才能使用其他控制选项。  
  
 **针对文件 I/O 流访问启用 FILESTREAM**  
 选中此项可针对 FILESTREAM 启用 Win32 流访问。  
  
 **Windows 共享名**  
 使用此控制选项可输入将用来存储 FILESTREAM 数据的 Windows 共享的名称。  
  
 **允许远程客户端针对 FILESTREAM 数据启用流访问**  
 选中此控制选项可允许远程客户端访问此服务器上的此 FILESTREAM 数据。  
  
## <a name="see-also"></a>请参阅  
 [启用和配置 FILESTREAM](../../relational-databases/blob/enable-and-configure-filestream.md)   
 [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
