---
title: sp_query_store_remove_plan (这 SQL) |Microsoft Docs
ms.custom: ''
ms.date: 03/29/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- SYS.SP_QUERY_STORE_REMOVE_PLAN_TSQL
- SP_QUERY_STORE_REMOVE_PLAN_TSQL
- SP_QUERY_STORE_REMOVE_PLAN
- SYS.SP_QUERY_STORE_REMOVE_PLAN
dev_langs:
- TSQL
helpviewer_keywords:
- sys.sp_query_store_remove_plan
- sp_query_store_remove_plan
ms.assetid: 88734726-135b-4b61-9f3f-f568c1fbece6
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 1b4920df9ba9ae43ed2ff0a8f163810f3271c6bc
ms.sourcegitcommit: c44014af4d3f821e5d7923c69e8b9fb27aeb1afd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "58533269"
---
# <a name="spquerystoreremoveplan-transct-sql"></a>sp_query_store_remove_plan (Transct-SQL)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  从查询存储中删除单个计划。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
sp_query_store_remove_plan [ @plan_id = ] plan_id [;]  
```  
  
## <a name="arguments"></a>参数  
`[ @plan_id = ] plan_id` 是要删除的查询计划的 id。 *plan_id*是**bigint**，无默认值。  
  
## <a name="return-code-values"></a>返回代码值  
 0（成功）或 1（失败）  
  
## <a name="remarks"></a>备注  
  
## <a name="permissions"></a>权限  
 需要**EXECUTE**上，对数据库的权限和**删除**查询存储目录视图的权限。  
  
## <a name="examples"></a>示例  
 下面的示例返回在查询存储中查询的信息。  
  
```  
SELECT Txt.query_text_id, Txt.query_sql_text, Pl.plan_id, Qry.*  
FROM sys.query_store_plan AS Pl  
JOIN sys.query_store_query AS Qry  
    ON Pl.query_id = Qry.query_id  
JOIN sys.query_store_query_text AS Txt  
    ON Qry.query_text_id = Txt.query_text_id ;  
```  
  
 确定要删除 plan_id 后，使用下面的示例删除查询计划。  
  
```  
EXEC sp_query_store_remove_plan 3;  
```  
  
## <a name="see-also"></a>请参阅  
 [sp_query_store_force_plan &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-query-store-force-plan-transact-sql.md)   
 [sp_query_store_remove_query &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-query-store-remove-query-transact-sql.md)   
 [sp_query_store_unforce_plan &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-query-store-unforce-plan-transact-sql.md)   
 [sp_query_store_reset_exec_stats &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-query-store-reset-exec-stats-transact-sql.md)   
 [sp_query_store_flush_db &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-query-store-flush-db-transact-sql.md)   
 [查询存储目录视图 (Transact-SQL)](../../relational-databases/system-catalog-views/query-store-catalog-views-transact-sql.md)   
 [使用查询存储来监视性能](../../relational-databases/performance/monitoring-performance-by-using-the-query-store.md)  
  
  
