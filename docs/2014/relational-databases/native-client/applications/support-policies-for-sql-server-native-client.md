---
title: SQL Server Native client 支持策略 |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 09c80cf4-23e6-4027-a24f-cdb9c87af811
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 4e5c7a01cc2a9569dd8c05316a2aa3314959e894
ms.sourcegitcommit: f7fced330b64d6616aeb8766747295807c92dd41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "63046522"
---
# <a name="support-policies-for-sql-server-native-client"></a>SQL Server Native Client 的支持策略
  本主题讨论如何将各种数据访问组件与 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 一起使用。  
  
## <a name="server-support"></a>服务器支持  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 11.0 支持与，连接[!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)]， [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)]， [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]， [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]，和[!INCLUDE[ssSDSfull](../../../includes/sssdsfull-md.md)]。  
  
## <a name="supported-operating-system-versions"></a>支持的操作系统版本  
 下表列出了支持 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 的操作系统。  
  
|SQL Server Native Client 版本|受支持的操作系统|  
|--------------------------------------|---------------------------------|  
|SQL Server Native Client (SQL Server 2005)|Microsoft Windows 2000 Service Pack 4 或更高版本<br />Microsoft Windows Server 2003 或更高版本<br />Microsoft Windows XP Service Pack 1 或更高版本<br />Microsoft Windows Vista (需要[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Service Pack 2 或更高版本)<br />Microsoft Windows Server 2008 (需要[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Service Pack 2 或更高版本)|  
|SQL Server Native Client 10.0 ([!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)])|Microsoft Windows Server 2003 Service Pack 2，或更高版本<br />Microsoft Windows XP Service Pack 2 或更高版本<br />-   Microsoft Windows Vista<br />-   Microsoft Windows Server 2008|  
|SQL Server Native Client 10.5 ([!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)])|Microsoft Windows Server 2003 Service Pack 2，或更高版本<br />Microsoft Windows XP Service Pack 2 或更高版本<br />-   Microsoft Windows Vista<br />-   Microsoft Windows Server 2008<br />-   Microsoft Windows 7|  
|SQL Server Native Client 11.0（[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] 和 [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)]）|-   Microsoft Windows Vista<br />-   Microsoft Windows Server 2008<br />-   Microsoft Windows 7<br />-   Microsoft Windows 8<br />-   Microsoft Windows Server 2012|  
  
## <a name="ado-support-policies"></a>ADO 支持策略  
 ADO 应用程序如果不需要 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] 或更高版本的任何功能，则可以使用 Windows 附带的 SQLOLEDB OLE DB 访问接口。  
  
 ADO 应用程序可以使用的版本[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Native Client 包含在[!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]。 ADO 应用程序还可以使用 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 11.0（随 [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] 附带），但使用时必须在连接字符串中指定 `DataTypeCompatibility=80`。 如果连接字符串中包含 `DataTypeCompatibility=80`，则只能使用 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] 的功能。  
  
## <a name="bcp-support-policies"></a>BCP 支持策略  
 自 [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] 开始，bcp.exe 支持比附带 bcp.exe 的 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 版本不早于三个 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 版本的数据文件。  
  
## <a name="odbc-support-policies"></a>ODBC 支持策略  
 应用程序应当使用随 Windows 操作系统附带的 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ODBC 驱动程序。 如果应用程序经认证可与特定版本的 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 一起使用，那么可以使用 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC 驱动程序。  
  
## <a name="ole-db-support-policies"></a>OLE DB 支持策略  
 应用程序应当使用随 Windows 操作系统附带的 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB 访问接口。 如果应用程序经认证可与特定版本的 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 一起使用，那么可使用 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB 访问接口。  
  
 未经认证以与 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 一起使用的 OLE DB 应用程序，如果在其连接字符串中指定了 `DataTypeCompatibility=80`，那么也可以使用 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client。  
  
 对于使用 OLE DB 服务组件的 OLE DB 应用程序，如果在其连接字符串中指定了 `DataTypeCompatibility=80`，那么只能使用 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client。 但是之后, 增加的所有功能[!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]将这种情况下提供。  
  
## <a name="see-also"></a>请参阅  
 [使用 SQL Server Native Client 生成应用程序](building-applications-with-sql-server-native-client.md)  
  
  
