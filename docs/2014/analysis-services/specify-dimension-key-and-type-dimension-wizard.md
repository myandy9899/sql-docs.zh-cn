---
title: 指定维度键和类型 （维度向导） |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionkeyandtype.f1
ms.assetid: d7d5db55-36c3-45f6-ade3-29aa516589c1
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 94e34c092b833f6740562e56c3ebbe713ffc2572
ms.sourcegitcommit: f7fced330b64d6616aeb8766747295807c92dd41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62746200"
---
# <a name="specify-dimension-key-and-type-dimension-wizard"></a>指定维度键和类型（维度向导）
  可以使用“指定维度键和类型”页定义维度的键属性，并指示维度是否为渐变维度 (SCD)。  
  
> [!NOTE]  
>  只有在“选择生成方法”页上选择了“不使用数据源生成维度”，并在“选择维度类型”页上选择了“标准维度”时，才会显示此页。  
  
## <a name="options"></a>选项  
 **键属性**  
 选择要作为维度键属性的属性。  
  
> [!NOTE]  
>  如果尚未为维度定义任何属性，则对于此选项唯一可用的值为 **“自动创建键属性”** 。如果为维度定义了任何属性，则此值不可用。  
  
 **这是变化的维度**  
 选择此选项可以指示维度为渐变维度。 选择此选项将创建其他列和属性，这些列和属性可以用来跟踪在一段时间后成员在维度的层次结构中的移动情况。  
  
## <a name="see-also"></a>请参阅  
 [维度向导的 F1 帮助](dimension-wizard-f1-help.md)   
 [维度&#40;Analysis Services-多维数据&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md)   
 [多维模型中的维度](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
