---
title: SQL Server에서 쿼리 알림
description: 예를 들어 응용 프로그램 표시를 새로 고치는 SQL Server 데이터베이스에서 데이터가 변경 된 경우 쿼리 알림을 사용 하 여 응용 프로그램에 알리는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
ms.openlocfilehash: 1351c83b6cc5837115321d53e8779c0f364c3099
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286225"
---
# <a name="query-notifications-in-sql-server"></a>SQL Server에서 쿼리 알림
Service Broker 인프라를 기반으로 구축된 쿼리 알림을 통해 애플리케이션은 데이터 변경 시 알림을 받을 수 있습니다. 이 기능은 데이터베이스의 정보 캐시를 제공하며 원본 데이터 변경 시 알림을 받아야 하는 애플리케이션(예: 웹 애플리케이션)에 특히 유용합니다.  
  
 ADO.NET를 사용하여 쿼리 알림을 구현하는 방법에는 세 가지가 있습니다.  
  
1. 하위 수준 구현은 서버 쪽 기능을 노출하는 `SqlNotificationRequest` 클래스에서 제공합니다. 이를 통해 알림 요청을 사용하여 명령을 실행할 수 있습니다.  
  
2. 상위 수준 구현은 원본 애플리케이션과 SQL Server 간의 알림 기능에 대한 상위 수준 추상화를 제공하는 클래스인 `SqlDependency` 클래스에서 제공합니다. 이를 통해 종속성을 사용하여 서버의 변경 내용을 검색할 수 있습니다. 이는 일반적으로 관리 클라이언트 애플리케이션에서 .NET Framework Data Provider for SQL Server를 사용하여 SQL Server 알림 기능을 가장 간단하고 효과적으로 활용하는 방법입니다.  
  
3. 또한 ASP.NET 2.0 이상을 사용하여 작성된 웹 애플리케이션에서는 `SqlCacheDependency` 도우미 클래스를 사용할 수 있습니다.  
  
 쿼리 알림은 기본 데이터의 변경 내용에 대한 응답으로 표시 또는 캐시를 새로 고쳐야 하는 애플리케이션에 사용됩니다. .NET Framework 애플리케이션에서 Microsoft SQL Server를 사용하여 SQL Server에 명령을 보낼 수 있을 뿐 아니라 동일한 명령을 실행했을 때 처음 검색한 것과 다른 결과 집합이 나오면 알림을 생성하도록 요청할 수도 있습니다. 서버에서 생성된 알림은 나중에 처리하기 위해 큐를 통해 전송됩니다.  
  
 SELECT 및 EXECUTE 문에 대한 알림을 설정할 수 있습니다. EXECUTE 문을 사용하는 경우 SQL Server는 EXECUTE 문 자체가 아니라 실행된 명령에 대한 알림을 등록합니다. 명령은 SELECT 문의 요구 사항과 제한 사항을 따라야 합니다. 알림을 등록하는 명령에 하나 이상의 문이 포함된 경우 데이터베이스 엔진은 일괄 처리에 있는 각 문에 대한 알림을 만듭니다.  
  
 을 개발 하는 애플리케이션 데이터가 변경 되 면 신뢰할 수 있는 하위 보조 알림이 필요한 경우 섹션을 검토 **효율적인 쿼리 알림 전략을 계획** 고 **쿼리에 대 한 대안 알림을** 에 [알림에 대 한 계획](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms187528(v=sql.105)) 문서. 쿼리 알림 및 SQL Server Service Broker에 대 한 자세한 내용은 SQL Server 설명서의 다음 문서에 대 한 링크를 참조 하십시오.  
  
 **SQL Server 설명서**  
  
- [쿼리 알림 사용](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))  
  
- [알림에 대한 쿼리 만들기](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))  
  
- [개발(Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))  
  
- [Service Broker 개발자 정보 센터](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))  
  
- [개발자 가이드(Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))  
  
## <a name="in-this-section"></a>섹션 내용  
 [쿼리 알림 사용](enabling-query-notifications.md)  
 쿼리 알림을 설정하고 사용하기 위한 요구 사항을 포함하여 쿼리 알림을 사용하는 방법을 설명합니다.  
  
 [ASP.NET 애플리케이션에서 SqlDependency](sqldependency-in-an-aspnet-app.md)  
 ASP.NET 애플리케이션에서 쿼리 알림을 사용하는 방법을 설명합니다.  
  
 [SqlDependency로 변경 내용 감지](detecting-changes-with-sqldependency.md)  
 쿼리 결과가 원래 수신된 결과와 다를 때를 감지하는 방법을 보여 줍니다.  
  
 [SqlNotificationRequest를 사용하여 SqlCommand 실행](sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 쿼리 알림과 함께 작동하도록 <xref:System.Data.SqlClient.SqlCommand> 개체를 구성하는 방법을 보여 줍니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 <xref:System.Data.Sql.SqlNotificationRequest> 클래스와 모든 해당 멤버에 대해 설명합니다.  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 <xref:System.Data.SqlClient.SqlDependency> 클래스와 모든 해당 멤버에 대해 설명합니다.  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 <xref:System.Web.Caching.SqlCacheDependency> 클래스와 모든 해당 멤버에 대해 설명합니다.  
  
## <a name="see-also"></a>참고 항목

- [SQL Server 및 ADO.NET](index.md)
- [ADO.NET 개요](../ado-net-overview.md)
