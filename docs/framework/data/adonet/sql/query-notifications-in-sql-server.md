---
title: SQL Server 中的查询通知
ms.date: 03/30/2017
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
ms.openlocfilehash: 11d9a1a800bea4224853a57b128ca89c9f2cf781
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452365"
---
# <a name="query-notifications-in-sql-server"></a>SQL Server 中的查询通知
查询通知建立在 Service Broker 基础结构的基础上，使应用程序可以在数据更改时收到通知。 如果应用程序提供数据库中信息的缓存（例如 Web 应用程序），需要在源数据更改时接收通知，此功能特别有用。  
  
 通过三种方式可以使用 ADO.NET 实现查询通知：  
  
1. 低级实现由 `SqlNotificationRequest` 类提供，该类公开服务器端功能，使您可以对通知请求执行命令。  
  
2. 高级实现由 `SqlDependency` 类提供，该类提供源应用程序与 SQL Server 之间通知功能的高级抽象，使您可以使用相关性来检测服务器中的更改。 大多数情况下，这是托管客户端应用程序通过适用于 SQL Server 的 .NET Framework 数据提供程序利用 SQL Server 通知功能的最简单、最有效的方法。  
  
3. 此外，使用 ASP.NET 2.0（或更高版本）构建的 Web 应用程序可以使用 `SqlCacheDependency` 帮助器类。  
  
 如果应用程序需要通过刷新显示或缓存来响应基础数据中的更改，查询通知非常有用。 如果执行相同命令生成的结果集与最初检索到的结果集不同，则 Microsoft SQL Server 可允许 .NET Framework 应用程序向 SQL Server 发送命令和请求通知。 服务器上生成的通知通过队列发送，供以后处理。  
  
 您可以为 SELECT 和 EXECUTE 语句设置通知。 使用 EXECUTE 语句时，SQL Server 会为执行的命令而不是 EXECUTE 语句本身注册通知。 命令必须满足 SELECT 语句的要求和限制。 当注册通知的命令包含多个语句时，数据库引擎会为批处理中的每个语句创建一个通知。  
  
 如果正在开发的应用程序在数据更改时需要可靠的第二秒通知，请查看规划[通知](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms187528(v=sql.105))一文中的 "**规划有效的查询通知策略**" 和 "**查询通知的替代方案**" 部分。 有关查询通知和 SQL Server Service Broker 的详细信息，请参阅 SQL Server 文档中的以下文章链接。  
  
 **SQL Server 文档**  
  
- [使用查询通知](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))  
  
- [为通知创建查询](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))  
  
- [开发 (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))  
  
- [Service Broker 开发人员信息中心](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))  
  
- [开发人员指南 (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))  
  
## <a name="in-this-section"></a>本节内容  
 [启用查询通知](enabling-query-notifications.md)  
 介绍如何使用查询通知（包括启用和使用查询通知的需求）。  
  
 [ASP.NET 应用程序中的 SqlDependency](sqldependency-in-an-aspnet-app.md)  
 演示如何使用 ASP.NET 应用程序中的查询通知。  
  
 [使用 SqlDependency 检测更改](detecting-changes-with-sqldependency.md)  
 演示如何检测查询结果与最初检索到的结果是否相同。  
  
 [使用 SqlNotificationRequest 的 SqlCommand 执行](sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 演示如何将 <xref:System.Data.SqlClient.SqlCommand> 对象配置为处理查询通知。  
  
## <a name="reference"></a>参考  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 描述 <xref:System.Data.Sql.SqlNotificationRequest> 类及其所有成员。  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 描述 <xref:System.Data.SqlClient.SqlDependency> 类及其所有成员。  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 描述 <xref:System.Web.Caching.SqlCacheDependency> 类及其所有成员。  
  
## <a name="see-also"></a>另请参阅

- [SQL Server 和 ADO.NET](index.md)
- [ADO.NET 概述](../ado-net-overview.md)
