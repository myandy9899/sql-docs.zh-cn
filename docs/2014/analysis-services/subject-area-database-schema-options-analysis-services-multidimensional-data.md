---
title: 主题区域数据库架构选项 （架构生成向导） (Analysis Services-多维数据) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.schemagenwizard.subjectareaschemaopts.f1
ms.assetid: 4c109bb8-e19d-412b-908f-bfdd7f872439
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: e608f6ca210f1d86a58b469145a9840f7c25ba2b
ms.sourcegitcommit: f7fced330b64d6616aeb8766747295807c92dd41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62758497"
---
# <a name="subject-area-database-schema-options-schema-generation-wizard-analysis-services---multidimensional-data"></a>主题区域数据库架构选项（架构生成向导）（Analysis Services - 多维数据）
  可以使用 **“主题区域数据库架构选项”** 页，控制如何生成架构以及定义如何保留数据。  
  
## <a name="options"></a>选项  
 **所属架构**  
 指定新主题区域数据库中的架构的名称。  
  
 **维度表创建主键**  
 在生成的架构中为维度表创建主键。 如果不选择此选项，则不会生成任何索引。  
  
> [!NOTE]  
>  如果不选择此选项，将强制引用完整性。  
  
 **创建索引**  
 在生成的架构中为外键列创建索引。  
  
 **强制实施引用完整性**  
 在生成的架构中强制引用完整性。 如果不选择此选项，将创建关系但不会强制执行。  
  
 **保留上重新生成的数据**  
 向导完成时，在主题区域数据库中保留数据。 如果不选择此选项，则可能在无警告的情况下清除主题区域数据库中的所有数据。  
  
 **填充时间表**  
 指定向导如何填充时间表。 下表对此选项的可能值进行了说明：  
  
> [!NOTE]  
>  只有在项目模式下使用 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] 从 [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] 项目调用架构生成向导时，才会启用此选项。  
  
|ReplTest1|Description|  
|-----------|-----------------|  
|填充|填充主题区域时间表。|  
|不填充|不填充主题区域时间表。|  
|为空时才填充|只有当主题区域时间表为空时才进行填充。|  
  
## <a name="see-also"></a>请参阅  
 [架构生成向导的 F1 帮助&#40;Analysis Services-多维数据&#41;](schema-generation-wizard-f1-help-analysis-services-multidimensional-data.md)  
  
  
