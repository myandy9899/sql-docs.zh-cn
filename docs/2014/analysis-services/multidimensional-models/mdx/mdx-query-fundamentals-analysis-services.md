---
title: MDX 查询基础知识 (Analysis Services) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
helpviewer_keywords:
- statements [MDX]
- Multidimensional Expressions [Analysis Services], statements
- Multidimensional Expressions [Analysis Services], queries
- MDX [Analysis Services], statements
- MDX queries [Analysis Services]
- MDX [Analysis Services], queries
- queries [MDX]
ms.assetid: a560383b-bb58-472e-95f5-65d03d8ea08b
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 9287cc028357c8db8e37242153e9815398b11858
ms.sourcegitcommit: f7fced330b64d6616aeb8766747295807c92dd41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62699401"
---
# <a name="mdx-query-fundamentals-analysis-services"></a>MDX 查询基础知识 (Analysis Services)
  通过使用多维表达式 (MDX)，您可以查询多维对象（如多维数据集）并返回包含多维数据集数据的多维单元集。 本主题及其子主题提供 MDX 查询的概述。  
  
 下列主题介绍了 MDX 查询及其产生的单元集，还提供了有关基本 MDX 语法的详细信息。  
  
> [!NOTE]  
>  有关与 MDX 查询和计算相关的性能问题的详细信息，请参阅"编写有效的 MDX"一节中[SQL Server 2005 Analysis Services 性能指南](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide)。  
  
## <a name="in-this-section"></a>本节内容  
  
|主题|Description|  
|-----------|-----------------|  
|[基本 MDX 查询 (MDX)](mdx-query-the-basic-query.md)|提供 MDX SELECT 语句的基本语法信息。|  
|[用查询轴和切片器轴限定查询&#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md)|说明什么是查询轴和切片器轴，以及如何指定它们。|  
|[在查询中建立多维数据集上下文 (MDX)](establishing-cube-context-in-a-query-mdx.md)|介绍 MDX SELECT 语句中的 FROM 子句的用途。|  
|[在 MDX 中生成命名集 (MDX)](mdx-named-sets-building-named-sets.md)|介绍 MDX 中的命名集的用途，以及在 MDX 查询中创建与使用命名集所需的技术。|  
|[在 MDX 中生成计算成员 (MDX)](mdx-calculated-members-building-calculated-members.md)|提供有关 MDX 中计算成员的信息，包括在 MDX 表达式中创建和使用计算成员所需的技术。|  
|[在 MDX 中生成单元格计算 (MDX)](../../multidimensional-models-olap-logical-cube-objects/calculations.md)|详细介绍创建和使用计算单元的过程。|  
|[创建和使用属性值 (MDX)](../../creating-and-using-property-values-mdx.md)|详细介绍创建和使用维度、级别、成员和单元属性的过程。|  
|[操作数据 (MDX)](mdx-data-manipulation-manipulating-data.md)|介绍使用钻取和汇总操作数据的基础知识，还介绍了 MDX 中的传递次序和求解次序。|  
|[修改数据 (MDX)](mdx-data-modification-modifying-data.md)|介绍如何使用写回临时或永久更改多维数据。|  
|[使用变量和参数 (MDX)](using-variables-and-parameters-mdx.md)|介绍如何在 MDX 查询中使用变量和参数。|  
  
## <a name="see-also"></a>请参阅  
 [多维表达式 (MDX) 参考](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
