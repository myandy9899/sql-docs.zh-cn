---
title: STGeometryN（geography 数据类型）| Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- STGeometryN (geography Data Type)
dev_langs:
- TSQL
helpviewer_keywords:
- STGeometryN method
ms.assetid: 53755f69-cd50-475b-b3b8-a1a9157cf03a
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 19c11e02f561919767cc9eb67b68cc863442ceb6
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "47628985"
---
# <a name="stgeometryn-geography-data-type"></a>STGeometryN（geography 数据类型）
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  返回 **GeometryCollection** 或其子类型之一中的指定 **geography** 元素。 对 **GeometryCollection** 的子类型（如 **MultiPoint** 或 **MultiLineString**）使用 STGeometryN() 时，如果使用 N=1 进行调用，此方法会返回 **geography** 实例。  
  
## <a name="syntax"></a>语法  
  
```  
  
.STGeometryN ( expression )  
```  
  
## <a name="arguments"></a>参数  
 *expression*  
 一个 **int** 表达式，其值介于 1 和 **GeometryCollection** 中的 **geography** 实例数之间。  
  
## <a name="return-types"></a>返回类型  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 返回类型：geography  
  
 CLR 返回类型：SqlGeography  
  
## <a name="remarks"></a>Remarks  
 如果参数大于 [STNumGeometries()](../../t-sql/spatial-geography/stnumgeometries-geography-data-type.md) 的结果，则此方法返回 null；如果 *expression* 参数小于 1，则将引发 **ArgumentOutOfRangeException**。  
  
## <a name="examples"></a>示例  
 以下示例创建 `MultiPoint``geography` 实例并使用 `STGeometryN()` 查找 GeometryCollection 的第二个 `geography` 实例。  
  
```  
DECLARE @g geography;  
SET @g = geography::STGeomFromText('MULTIPOINT(-122.360 47.656, -122.343 47.656)', 4326);  
SELECT @g.STGeometryN(2).ToString();  
```  
  
## <a name="see-also"></a>另请参阅  
 [地理实例上的 OGC 方法](../../t-sql/spatial-geography/ogc-methods-on-geography-instances.md)  
  
  
