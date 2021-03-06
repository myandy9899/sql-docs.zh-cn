---
title: sys.pdw_nodes_columns (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: ''
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 268c77b7-1d71-4197-a2ed-5e2b2b8fc260
author: ronortloff
ms.author: rortloff
manager: craigg
monikerRange: '>= aps-pdw-2016 || = azure-sqldw-latest || = sqlallproducts-allversions'
ms.openlocfilehash: 949d8a90892e1954ee0a96f0025cb623569fbe55
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "56024418"
---
# <a name="syspdwnodescolumns-transact-sql"></a>sys.pdw_nodes_columns (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md.md)]

  显示用户定义表和用户定义视图的列。  
  
|列名|数据类型|Description|范围|  
|-----------------|---------------|-----------------|-----------|  
|object_id|**int**|此列所属对象的 ID。||  
|NAME|**sysname**|列的名称。 对象中是唯一的。||  
|column_id|**int**|列的 ID。 对象中是唯一的。||  
|system_type_id|**tinyint**|系统类型的列的 ID。||  
|user_type_id|**int**|用户定义的列类型的 ID。||  
|max_length|**smallint**|列的最大长度（字节）。|包括对不受支持的列类型 （无效）-1。|  
|精度|**tinyint**|如果基于数值; 列的精度否则为为 0。||  
|小数位数|**tinyint**|如果基于数值，则为列的小数位数；否则为 0。||  
|collation_name|**sysname**|如果基于字符的; 的列的排序规则名称否则，为 NULL。||  
|is_nullable|**bit**|1 = 列可为空。||  
|is_ansi_padded|**bit**|1 = 如果列为字符、二进制或变量类型，则该列使用 ANSI_PADDING ON 行为。|始终为 0。|  
|is_rowguidcol|**bit**|1 = 列为声明的 ROWGUIDCOL。|始终为 0。|  
|is_identity|**bit**|1 = 列具有标识值。|始终为 0。|  
|is_computed|**bit**|1 = 列为计算列。|始终为 0。|  
|is_filestream|**bit**|1 = 列为 FILESTREAM 列。|始终为 0。|  
|is_replicated|**bit**|1 = 列已复制。|始终为 0。|  
|is_non_sql_subscribed|**bit**|1 = 列具有非 SQL 订阅服务器。|始终为 0。|  
|is_merge_published|**bit**|1 = 列已合并发布。|始终为 0。|  
|is_dts_replicated|**bit**|1 = 列通过使用 SSIS 进行复制。|始终为 0。|  
|is_xml_document|**bit**|1 = 内容为完整的 XML 文档。|始终为 0。|  
|xml_collection_id|**int**|0 = 没有 XML 架构集合。|始终为 0。|  
|default_object_id|**int**|默认对象; ID0 = 无默认值。|始终为 0。|  
|rule_object_id|**int**|绑定到列的独立规则的 ID。 <br />0 = 无独立规则。|始终为 0。|  
|is_sparse|**bit**|1 = 列为稀疏列。|始终为 0。|  
|is_column_set|**bit**|1 = 列为列集。|始终为 0。|  
|pdw_node_id|**int**|唯一标识符[!INCLUDE[ssSDW](../../includes/sssdw-md.md)]节点。|NOT NULL|  
  
## <a name="permissions"></a>权限  
 需要 CONTROL SERVER 权限。  
  
## <a name="see-also"></a>请参阅  
 [SQL 数据仓库和并行数据仓库目录视图](../../relational-databases/system-catalog-views/sql-data-warehouse-and-parallel-data-warehouse-catalog-views.md)   
 [sys.all_columns &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-all-columns-transact-sql.md)  
  
  
