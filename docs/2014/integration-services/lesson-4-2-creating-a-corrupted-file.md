---
title: 第 2 步：创建损坏的文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: cd0b18dc-66c3-4d88-86ef-8e40cb660fae
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: fa1bb23843447cc77276a34d5466d417f2a87a05
ms.sourcegitcommit: f7fced330b64d6616aeb8766747295807c92dd41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62767379"
---
# <a name="step-2-creating-a-corrupted-file"></a>第 2 步：创建损坏的文件
  为阐释如何配置和处理转换错误，必须创建一个在处理时导致组件失败的示例平面文件。  
  
 在本任务中，将创建现有示例平面文件的一个副本。 然后，用记事本打开该文件，编辑 **CurrencyID** 列，以确保该列在转换查找期间无法生成匹配项。 处理新文件时，查找失败将导致 Currency Key 查找转换失败，因此，包的剩余部分将失败。 创建了损坏的示例文件后，将运行包以查看包失败的情况。  
  
### <a name="to-create-a-corrupted-sample-flat-file"></a>创建损坏的示例平面文件  
  
1.  在记事本或任何其他文本编辑器中，打开 Currency_VEB.txt 文件。  
  
     示例数据与 SSIS 课程包一起提供。 要下载示例数据和课程包，请执行以下操作：  
  
    1.  导航到 [Integration Services 产品示例](https://go.microsoft.com/fwlink/?LinkID=267527)。  
  
    2.  单击 **“下载”** 选项卡。  
  
    3.  单击 SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip 文件。  
  
2.  使用文本编辑器的查找和替换功能，查找的所有实例`VEB`并将其替换为`BAD`。  
  
3.  在其他示例数据文件所在的文件夹，将保存已修改的文件作为`Currency_BAD.txt`。  
  
    > [!IMPORTANT]  
    >  请确保`Currency_BAD.txt`与其他示例数据文件保存在同一文件夹。  
  
4.  关闭文本编辑器。  
  
### <a name="to-verify-that-an-error-will-occur-during-run-time"></a>验证是否将在运行时发生错误  
  
1.  在 **“调试”** 菜单中，单击 **“启动调试”**。  
  
     在数据流第三次迭代时，Lookup Currency Key 转换将尝试处理 Currency_BAD.txt 文件，并且该转换将失败。 转换失败将导致整个包失败。  
  
2.  在 **“调试”** 菜单中，单击 **“停止调试”**。  
  
3.  在设计图面上，单击“执行结果”选项卡。  
  
4.  浏览日志，确认是否发生了以下未处理的错误：  
  
     `[Lookup Currency Key[27]] Error: Row yielded no match during lookup.`  
  
    > [!NOTE]  
    >  数字 27 为组件的 ID。 该值在生成数据流时进行分配，可能与包中的值不同。  
  
## <a name="next-steps"></a>后续步骤  
 [步骤 3：添加错误流重定向](lesson-4-3-adding-error-flow-redirection.md)  
  
  
