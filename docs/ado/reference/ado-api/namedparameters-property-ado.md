---
title: NamedParameters 属性 (ADO) |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _Command::NamedParameters
helpviewer_keywords:
- NamedParameters property [ADO]
ms.assetid: 42409387-026c-435f-a9b1-bf4167095875
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: c63fb598630a30fd2616722146bb6737f17b82b5
ms.sourcegitcommit: f7fced330b64d6616aeb8766747295807c92dd41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "63242403"
---
# <a name="namedparameters-property-ado"></a>NamedParameters 属性 (ADO)
指示是否应将参数名称传递给提供程序。  
  
## <a name="remarks"></a>备注  
 如果此属性为 true，ADO 将传递的值**名称**中的每个参数的属性**参数**集合[命令对象](../../../ado/reference/ado-api/command-object-ado.md)。 提供程序使用的参数名称匹配中的参数**CommandText**或**CommandStream**属性。 如果此属性为 false （默认值），将忽略参数名称和提供程序使用参数的顺序以匹配到中的参数的值**CommandText**或**CommandStream**属性。  
  
## <a name="applies-to"></a>适用范围  
 [命令对象 (ADO)](../../../ado/reference/ado-api/command-object-ado.md)  
  
## <a name="see-also"></a>请参阅  
 [CommandText 属性 (ADO)](../../../ado/reference/ado-api/commandtext-property-ado.md)   
 [CommandStream 属性 (ADO)](../../../ado/reference/ado-api/commandstream-property-ado.md)   
 [参数集合 (ADO)](../../../ado/reference/ado-api/parameters-collection-ado.md)
