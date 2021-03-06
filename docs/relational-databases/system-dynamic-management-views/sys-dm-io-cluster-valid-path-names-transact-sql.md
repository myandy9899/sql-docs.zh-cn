---
title: sys.dm_io_cluster_valid_path_names (TRANSACT-SQL) |Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.dm_io_cluster_valid_path_names
- dm_io_cluster_valid_path_names_TSQL
- sys.dm_io_cluster_valid_path_names_TSQL
- dm_io_cluster_valid_path_names
dev_langs:
- TSQL
helpviewer_keywords:
- dm_io_cluster_valid_path_names
- sys.dm_io_cluster_valid_path_names
- cluster valid path names
- csv name
- cluster shared volume names
ms.assetid: 5bc8a0e5-6c72-425b-8c58-f276eb9add2c
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 9ea5453465fe27cfe4456f7da1fdb2690c6953c3
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "47645231"
---
# <a name="sysdmioclustervalidpathnames-transact-sql"></a>sys.dm_io_cluster_valid_path_names (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2014-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2014-xxxx-xxxx-xxx-md.md)]

  返回有关 SQL Server 故障转移群集实例的所有有效共享磁盘的信息（包括群集共享卷）。 如果实例未实现群集，则返回空行集。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**path_name**|**Nvarchar(512)**|可以用作数据库和日志文件的根目录的卷装入点或驱动器路径。 不可为 null。|  
|**cluster_owner_node**|**Nvarchar(64)**|驱动器的当前所有者。 对于群集共享卷 (CSV)，所有者是承载元数据服务器的节点。 不可为 null。|  
|**is_cluster_shared_volume**|**Bit**|如果此路径所在的驱动器是群集共享卷，则返回 1；否则，返回 0。|  
  
## <a name="remarks"></a>备注  
 SQL Server 故障转移群集实例 (FCI) 必须在 FCI 的所有节点之间使用共享存储，以便进行数据和日志文件存储。 此视图中列出的磁盘是处于与实例关联的群集资源组中的磁盘，并且是可以用于数据或日志文件存储的唯一一组磁盘。  
  
> [!NOTE]  
>  该视图将替换[sys.dm_io_cluster_shared_drives &#40;TRANSACT-SQL&#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-io-cluster-shared-drives-transact-sql.md)未来版本中。  
  
## <a name="permissions"></a>Permissions  
 用户必须对 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例拥有 VIEW SERVER STATE 权限。  
  
## <a name="examples"></a>示例  
 以下示例使用 sys.dm_io_cluster_valid_path_names，在群集服务器实例上确定共享驱动器：  
  
```  
SELECT * FROM sys.dm_io_cluster_valid_path_names;  
```  
  
## <a name="see-also"></a>请参阅  
 [sys.dm_os_cluster_nodes &#40;TRANSACT-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-os-cluster-nodes-transact-sql.md)   
 [sys.dm_io_cluster_shared_drives &#40;TRANSACT-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-io-cluster-shared-drives-transact-sql.md)   
 [动态管理视图和函数 (Transact-SQL)](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)  
  
  

