---
title: 书签 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bookmarks [OLE DB]
- SQL Server Native Client OLE DB provider, bookmarks
- rowsets [OLE DB], bookmarks
- OLE DB rowsets, bookmarks
ms.assetid: 7d9076f2-bf9c-452e-b816-70371a0c1644
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 4588780932ab408b5e35a2099767c30bcecc1375
ms.sourcegitcommit: f7fced330b64d6616aeb8766747295807c92dd41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "63183654"
---
# <a name="bookmarks"></a>书签
  书签支持使用者快速返回到某行。 利用书签，使用者可以根据书签值对行进行随机访问。 行集中的列 0 为书签列。 使用者可将绑定结构的 dwFlag 字段值设置为 DBCOLUMNSINFO_ISBOOKMARK，以指示将该列用作书签。 使用者还可将行集属性 DBPROP_BOOKMARKS 设置为 VARIANT_TRUE。 这样可使行集中包含列 0。 然后，可使用 IRowsetLocate::GetRowsAt 方法提取行（起始行的位置为书签加上一个偏移量得到的位置）。  
  
## <a name="see-also"></a>请参阅  
 [行集](rowsets.md)  
  
  
