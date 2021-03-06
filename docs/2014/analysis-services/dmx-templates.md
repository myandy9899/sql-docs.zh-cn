---
title: DMX 模板 |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
ms.assetid: 2a577e52-821d-4bd3-ba35-075a6be285c9
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 7e3bee7fa85c98e50fdb940d2dfb23f76f3a462c
ms.sourcegitcommit: f7fced330b64d6616aeb8766747295807c92dd41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62731754"
---
# <a name="dmx-templates"></a>DMX 模板
  数据挖掘模板可帮助您快速生成复杂的查询。 虽然 DMX 查询的常规语法具有详细说明，但借助于这些模板，可通过单击并且指向参数和数据源，更轻松地生成查询。  
  
## <a name="using-the-templates"></a>使用模板  
  
1.  数据挖掘 Excel 客户端中，单击**查询**。  
  
2.  在向导上**启动**页上，单击**下一步**。  
  
3.  在页上，**选择模型**，单击**高级**。  
  
     **提示：** 如果要针对模型创建预测查询，您可以首先，选择该模型，然后单击**高级**、 预先填充该模板使用的模型名称。  
  
4.  在中**数据挖掘高级查询编辑器**，单击**DMX 模板**，然后选择一个模板。  
  
5.  按 Enter 将模板加载到“DMX 查询”窗格中。  
  
6.  继续单击模板中的链接，在对话框出现后，选择相应的输出、模型或参数。  
  
     对于预测查询，请首先选择输入数据集，然后映射列。  
  
7.  单击**编辑查询**切换到文本编辑器视图并手动更改查询。  
  
     但要注意，如果在使用查询编辑器时切换视图，则上一视图中的所有信息都将被清除。 更改视图前，请将 DMX 语句复制并粘贴到一个单独的文件中，保存好您的工作结果。  
  
8.  单击 **“完成”**。 在中**选择目标**对话框框中，指定要保存的结果。 [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
> [!NOTE]  
>  如果已成功执行语句，发送到服务器的 DMX 语句也会记录在**跟踪**窗口。 有关如何使用跟踪功能的详细信息，请参阅[Trace &#40;Excel 数据挖掘客户端&#41;](trace-data-mining-client-for-excel.md)。  
  
 有关如何使用数据挖掘高级查询编辑器的详细信息，请参阅[查询&#40;SQL Server 数据挖掘外接程序&#41;](query-sql-server-data-mining-add-ins.md)并[高级数据挖掘查询编辑器](advanced-data-mining-query-editor.md)。  
  
## <a name="list-of-dmx-templates"></a>DMX 模板的列表  
 以下 DMX 模板包含在 Excel 数据挖掘客户端中。  
  
 **预测**  
  
 使用这些模板可创建高级预测查询，包括外接程序中向导不支持的查询，例如使用嵌套表或外部数据源的查询。  
  
-   筛选的预测  
  
-   筛选的嵌套预测  
  
-   嵌套的预测  
  
-   单独预测  
  
-   标准预测  
  
-   时序预测  
  
-   TOP 预测查询  
  
-   嵌套表的 TOP 预测查询  
  
 **创建**  
  
 使用这些模板可生成自定义模型或数据结构。 您并不局限于向导支持的模型-可以使用的实例支持的任何数据挖掘算法[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]您连接到，包括插件算法。  
  
-   挖掘模型  
  
-   挖掘结构  
  
-   具有维持的挖掘结构  
  
-   临时模型  
  
-   临时结构  
  
 **模型属性**  
  
 使用这些模板可创建获取有关模型和定型集的元数据的查询。 还可以从模型内容中检索详细信息，或者获取定型数据的统计配置文件。  
  
-   挖掘模型内容  
  
-   最小和最大列值  
  
-   挖掘结构测试/定型事例  
  
-   离散列值  
  
 **管理**  
  
 使用这些模板可执行 DMX 支持的任何管理任务，包括导入和导出模型、删除模型以及清除模型或数据结构。  
  
-   清除挖掘模型  
  
-   清除结构和模型  
  
-   清除挖掘结构  
  
-   删除挖掘模型  
  
-   删除挖掘结构  
  
-   重命名挖掘模型  
  
-   重命名挖掘结构  
  
-   为挖掘模型定型  
  
-   为嵌套挖掘结构定型  
  
-   为挖掘结构定型  
  
### <a name="requirements"></a>要求  
 根据使用的模板，您可能需要具有管理权限才能访问 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] 服务器和执行查询。  
  
## <a name="see-also"></a>请参阅  
 [创建数据挖掘模型](creating-a-data-mining-model.md)  
  
  
