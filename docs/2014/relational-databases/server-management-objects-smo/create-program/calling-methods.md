---
title: 调用方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- methods [SMO]
- calling methods
- SQL Server Management Objects, method calling
- SMO [SQL Server], method calling
ms.assetid: c88d5c5f-9ff0-4f84-b2b6-24c6b90fa15e
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 5c3a004d30a5edb20da77e6f93bf51a94472419b
ms.sourcegitcommit: f7fced330b64d6616aeb8766747295807c92dd41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "63192167"
---
# <a name="calling-methods"></a>调用方法
  方法执行特定任务相关的对象，例如颁发`Checkpoint`对数据库或请求的登录的实例的枚举的列表[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]。  
  
 方法针对对象执行操作。 方法可以使用参数并通常具有返回值。 返回值可以是简单数据类型、复杂对象或包含很多成员的结构。  
  
 使用异常处理检测方法是否成功。 有关详细信息，请参阅 [Handling SMO Exceptions](handling-smo-exceptions.md)。  
  
## <a name="examples"></a>示例  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="using-a-simple-smo-method-in-visual-basic"></a>在 Visual Basic 中使用简单 SMO 方法  
 在此示例中，<xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> 方法不使用参数，没有返回值。  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMethods1](SMO How to#SMO_VBMethods1)]  -->  
  
## <a name="using-a-simple-smo-method-in-visual-c"></a>在 Visual C# 中使用简单 SMO 方法  
 在此示例中，<xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> 方法不使用参数，没有返回值。  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Define a Database object variable by supplying the parent server and the database name arguments in the constructor.   
Database db;   
db = new Database(srv, "Test_SMO_Database");   
//Call the Create method to create the database on the instance of SQL Server.   
db.Create();   
```  
  
 }  
  
## <a name="using-an-smo-method-with-a-parameter-in-visual-basic"></a>在 Visual Basic 中使用带参数的 SMO 方法  
 <xref:Microsoft.SqlServer.Management.Smo.Table> 对象具有名为 <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A> 的方法。 此方法需要指定 `FillFactor`的数字参数。  
  
```  
Dim srv As Server  
srv = New Server  
Dim tb As Table  
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources")  
tb.RebuildIndexes(70)  
```  
  
## <a name="using-an-smo-method-with-a-parameter-in-visual-c"></a>在 Visual C# 中使用带参数的 SMO 方法  
 <xref:Microsoft.SqlServer.Management.Smo.Table> 对象具有名为 <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A> 的方法。 此方法需要指定 `FillFactor`的数字参数。  
  
```  
{   
Server srv = default(Server);   
srv = new Server();   
Table tb = default(Table);   
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources");   
tb.RebuildIndexes(70);   
}   
```  
  
## <a name="using-an-enumeration-method-that-returns-a-datatable-object-in-visual-basic"></a>在 Visual Basic 中使用返回 DataTable 对象的枚举方法  
 本节说明如何调用枚举方法以及如何处理返回的 <xref:System.Data.DataTable> 对象中的数据。  
  
 <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> 方法返回 <xref:System.Data.DataTable> 对象，该对象需要进一步导航以访问有关 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 实例的所有可用排序规则信息。  
  
```  
'Connect to the local, default instance of SQL Server.  
Dim srv As Server  
srv = New Server  
'Call the EnumCollations method and return collation information to DataTable variable.  
Dim d As DataTable  
'Select the returned data into an array of DataRow.  
d = srv.EnumCollations  
'Iterate through the rows and display collation details for the instance of SQL Server.  
Dim r As DataRow  
Dim c As DataColumn  
For Each r In d.Rows  
    Console.WriteLine("==")  
    For Each c In r.Table.Columns  
        Console.WriteLine(c.ColumnName + " = " + r(c).ToString)  
    Next  
Next  
```  
  
## <a name="using-an-enumeration-method-that-returns-a-datatable-object-in-visual-c"></a>在 Visual C# 中使用返回 DataTable 对象的枚举方法  
 本节说明如何调用枚举方法以及如何处理返回的 <xref:System.Data.DataTable> 对象中的数据。  
  
 <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> 方法返回系统 <xref:System.Data.DataTable> 对象。 <xref:System.Data.DataTable> 对象需要进一步导航以访问有关 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 实例的所有可用排序规则信息。  
  
```  
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
//Call the EnumCollations method and return collation information to DataTable variable.   
DataTable d = default(DataTable);   
//Select the returned data into an array of DataRow.   
d = srv.EnumCollations;   
//Iterate through the rows and display collation details for the instance of SQL Server.   
DataRow r = default(DataRow);   
DataColumn c = default(DataColumn);   
foreach ( r in d.Rows) {   
  Console.WriteLine("=========");   
  foreach ( c in r.Table.Columns) {   
    Console.WriteLine(c.ColumnName + " = " + r(c).ToString);   
  }   
}   
}   
```  
  
## <a name="constructing-an-object-in-visual-basic"></a>在 Visual Basic 中构造对象  
 可以通过使用 `New` 运算符调用任意对象的构造函数。 重载 <xref:Microsoft.SqlServer.Management.Smo.Database> 对象构造函数，本示例中使用的 <xref:Microsoft.SqlServer.Management.Smo.Database> 对象构造函数版本具有两个参数：数据库所属的父 <xref:Microsoft.SqlServer.Management.Smo.Server> 对象以及表示新数据库名称的字符串。  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMethods4](SMO How to#SMO_VBMethods4)]  -->  
  
## <a name="constructing-an-object-in-visual-c"></a>在 Visual C# 中构造对象  
 可以通过使用 `New` 运算符调用任意对象的构造函数。 重载 <xref:Microsoft.SqlServer.Management.Smo.Database> 对象构造函数，本示例中使用的 <xref:Microsoft.SqlServer.Management.Smo.Database> 对象构造函数版本具有两个参数：数据库所属的父 <xref:Microsoft.SqlServer.Management.Smo.Server> 对象以及表示新数据库名称的字符串。  
  
```  
{   
Server srv;   
srv = new Server();   
Table tb;   
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources");   
tb.RebuildIndexes(70);   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Declare and define a Database object by supplying the parent server and the database name arguments in the constructor.   
Database d;   
d = new Database(srv, "Test_SMO_Database");   
//Create the database on the instance of SQL Server.   
d.Create();   
Console.WriteLine(d.Name);   
}  
```  
  
## <a name="copying-an-smo-object-in-visual-basic"></a>在 Visual Basic 中复制 SMO 对象  
 此代码示例使用 <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> 方法来创建 <xref:Microsoft.SqlServer.Management.Smo.Server> 对象的副本。 <xref:Microsoft.SqlServer.Management.Smo.Server> 对象表示与 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 实例的一个连接。  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VCMethods6](SMO How to#SMO_VCMethods6)]  -->  
  
## <a name="copying-an-smo-object-in-visual-c"></a>在 Visual C# 中复制 SMO 对象  
 此代码示例使用 <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> 方法来创建 <xref:Microsoft.SqlServer.Management.Smo.Server> 对象的副本。 <xref:Microsoft.SqlServer.Management.Smo.Server> 对象表示与 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 实例的一个连接。  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv1;   
srv1 = new Server();   
//Modify the default database and the timeout period for the connection.   
srv1.ConnectionContext.DatabaseName = "AdventureWorks2012";   
srv1.ConnectionContext.ConnectTimeout = 30;   
//Make a second connection using a copy of the ConnectionContext property and verify settings.   
Server srv2;   
srv2 = new Server(srv1.ConnectionContext.Copy);   
Console.WriteLine(srv2.ConnectionContext.ConnectTimeout.ToString);   
}  
```  
  
## <a name="monitoring-server-processes-in-visual-basic"></a>在 Visual Basic 中监视服务器进程  
 可以通过枚举方法获取有关 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 实例的当前状态类型信息。 该代码示例使用 <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> 方法发现有关当前进程的信息。 它还演示如何使用返回的 <xref:System.Data.DataTable> 对象中的列和行。  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMethods5](SMO How to#SMO_VBMethods5)]  -->  
  
## <a name="monitoring-server-processes-in-visual-c"></a>在 Visual C# 中监视服务器进程  
 可以通过枚举方法获取有关 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 实例的当前状态类型信息。 该代码示例使用 <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> 方法发现有关当前进程的信息。 它还演示如何使用返回的 <xref:System.Data.DataTable> 对象中的列和行。  
  
```  
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
//Call the EnumCollations method and return collation information to DataTable variable.   
DataTable d = default(DataTable);   
//Select the returned data into an array of DataRow.   
d = srv.EnumProcesses;   
//Iterate through the rows and display collation details for the instance of SQL Server.   
DataRow r = default(DataRow);   
DataColumn c = default(DataColumn);   
foreach ( r in d.Rows) {   
  Console.WriteLine("=====");   
  foreach ( c in r.Table.Columns) {   
    Console.WriteLine(c.ColumnName + " = " + r(c).ToString);   
  }   
}   
}   
```  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.SqlServer.Management.Smo.Server>   
 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>  
  
  
