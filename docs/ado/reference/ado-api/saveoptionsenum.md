---
title: SaveOptionsEnum | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- SaveOptionsEnum
helpviewer_keywords:
- SaveOptionsEnum enumeration [ADO]
ms.assetid: 59339100-6e29-48d1-aea3-6873796d186b
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 288168b2a4b47c8a73612bd89a6f1987e2808475
ms.sourcegitcommit: f7fced330b64d6616aeb8766747295807c92dd41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "63314908"
---
# <a name="saveoptionsenum"></a>SaveOptionsEnum
指定文件是否应创建或覆盖从保存时[Stream](../../../ado/reference/ado-api/stream-object-ado.md)对象。 值可以是**adSaveCreateNotExist**或**adSaveCreateOverWrite**...  
  
|常量|ReplTest1|Description|  
|--------------|-----------|-----------------|  
|**adSaveCreateNotExist**|1|默认值。 如果指定的文件创建一个新文件*文件名*参数尚不存在。|  
|**adSaveCreateOverWrite**|2|使用来自当前打开的数据将覆盖文件**Stream**对象，如果指定的文件*Filename*参数已存在。 如果指定的文件*文件名*参数不存在，创建一个新文件。|  
  
## <a name="adowfc-equivalent"></a>ADO/WFC 等效项  
 这些常量不具有 ADO/WFC 等效项。  
  
## <a name="applies-to"></a>适用范围  
 [SaveToFile 方法](../../../ado/reference/ado-api/savetofile-method.md)
