---
title: ATOM 设备信息设置 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- reporting-services-native
ms.topic: conceptual
ms.assetid: fe4a56a4-5552-423c-85c1-895e2e212fee
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 815eff4ba68cb35a5f38b98514cc5359347a42e3
ms.sourcegitcommit: f7fced330b64d6616aeb8766747295807c92dd41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "63237699"
---
# <a name="atom-device-information-settings"></a>ATOM 设备信息设置
  用于 Atom 呈现扩展插件的设备信息设置支持要使用的 Atom 馈送和字符编码的名称的提交。  
  
 下表列出了用于向数据服务文档呈现的设备信息设置。  
  
|设置|ReplTest1|  
|-------------|-----------|  
|`DataFeed`|如果指定，则呈现与在此设置中提供的馈送名称相对应的 Atom 馈送。 如果未指定，则呈现报表的 Atom 服务文档。 数据馈送的唯一自动生成的标识符。 该值在内部使用，而且不应更改它。|  
|**编码**|.NET Framework 支持的字符编码的 Internet 编号分配机构 (IANA) 名称。 默认值是 `UTF-8`。 其他值的示例包括 ASCII、UTF-7 和 UTF-16。|  
  
## <a name="see-also"></a>请参阅  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 [将设备信息设置传递给呈现扩展插件](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md)   
 [在 RSReportServer.Config 中自定义呈现扩展插件参数](customize-rendering-extension-parameters-in-rsreportserver-config.md)   
 [技术参考 (SSRS)](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
