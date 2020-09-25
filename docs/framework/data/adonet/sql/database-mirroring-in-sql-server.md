---
title: SQL Server에서 데이터베이스 미러링
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 89befaff-bb46-4290-8382-e67cdb0e3de9
ms.openlocfilehash: 7e2c1c8ea1cbc1bb22452b9ef9d1f250c96118ea
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173538"
---
# <a name="database-mirroring-in-sql-server"></a>SQL Server에서 데이터베이스 미러링

SQL Server의 데이터베이스 미러링을 사용하면 대기 서버에서 SQL Server 데이터베이스의 복사본, 즉 미러를 유지할 수 있습니다. 미러링을 사용하면 별도의 데이터 복사본 두 개가 항상 존재하여 높은 가용성과 완전한 데이터 중복성을 보장합니다. .NET Data Provider for SQL Server에서는 데이터베이스 미러링을 암시적으로 지원하므로 SQL Server 데이터베이스에 대해 미러링이 구성되고 나면 개발자가 별도의 동작을 수행하거나 코드를 작성할 필요가 없습니다. 또한 <xref:System.Data.SqlClient.SqlConnection> 개체는 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>에서의 장애 조치(failover) 파트너 서버 이름 제공을 지원합니다.  
  
 미러링용으로 구성된 데이터베이스를 대상으로 하는 <xref:System.Data.SqlClient.SqlConnection> 개체에 대하여 다음과 같은 간단한 이벤트 시퀀스가 발생합니다.  
  
1. 클라이언트 애플리케이션이 주 데이터베이스에 성공적으로 연결되고 서버에서 파트너 서버의 이름을 다시 보냅니다(클라이언트에 캐시됨).  
  
2. 주 데이터베이스가 포함된 서버가 실패하거나 연결이 중단되면 연결 및 트랜잭션 상태가 손실됩니다. 클라이언트 애플리케이션은 주 데이터베이스에 대한 연결을 다시 설정하려고 시도하고 실패합니다.  
  
3. 그런 다음 클라이언트 애플리케이션은 파트너 서버에서 미러 데이터베이스에 대한 연결을 투명하게 시도합니다. 성공하면 연결이 미러 데이터베이스로 리디렉션되고, 그러면 새로운 주 데이터베이스가 됩니다.  
  
## <a name="specifying-the-failover-partner-in-the-connection-string"></a>연결 문자열에 장애 조치 파트너 지정  

 연결 문자열에 장애 조치(failover) 파트너 서버 이름을 제공하는 경우에는 클라이언트 애플리케이션이 처음 연결될 때 주 데이터베이스를 사용할 수 없다면 클라이언트는 장애 조치(failover) 파트너와의 연결을 투명하게 시도합니다.  
  
```csharp
";Failover Partner=PartnerServerName"  
```  
  
 장애 조치(failover) 파트너 서버의 이름을 생략하고 클라이언트 애플리케이션이 처음 연결될 때 주 데이터베이스를 사용할 수 없다면 <xref:System.Data.SqlClient.SqlException>이 발생합니다.  
  
 <xref:System.Data.SqlClient.SqlConnection>이 성공적으로 열리면 서버에서 장애 조치(failover) 파트너의 이름이 반환되어 연결 문자열에 제공된 모든 값을 대체합니다.  
  
> [!NOTE]
> 데이터베이스 미러링 시나리오의 경우 연결 문자열에 초기 카탈로그 또는 데이터베이스 이름을 명시적으로 지정해야 합니다. 클라이언트에서 명시적으로 지정된 초기 카탈로그 또는 데이터베이스가 없는 연결에 대한 장애 조치 정보를 받으면 장애 조치 정보가 캐시되지 않고 주 서버가 실패해도 애플리케이션에서 장애 조치를 시도하지 않습니다. 연결 문자열에 장애 조치(failover) 파트너에 대한 값은 있지만 초기 카탈로그 또는 데이터베이스에 대한 값이 없는 경우에는 `InvalidArgumentException`이 발생합니다.  
  
## <a name="retrieving-the-current-server-name"></a>현재 서버 이름 검색  

 장애 조치(failover) 시 <xref:System.Data.SqlClient.SqlConnection> 개체의 <xref:System.Data.SqlClient.SqlConnection.DataSource%2A> 속성을 사용하여 현재 연결이 실제로 연결된 서버의 이름을 검색할 수 있습니다. 다음 코드 조각은 연결 변수가 열린 <xref:System.Data.SqlClient.SqlConnection>을 참조한다고 가정하여 활성 서버의 이름을 검색합니다.  
  
 장애 조치 이벤트가 발생하고 연결이 미러 서버로 전환되면 **DataSource** 속성이 업데이트되며 미러 이름을 반영합니다.  
  
```vb  
Dim activeServer As String = connection.DataSource  
```  
  
```csharp  
string activeServer = connection.DataSource;  
```  
  
## <a name="sqlclient-mirroring-behavior"></a>SqlClient 미러링 동작  

 클라이언트는 항상 현재 주 서버에 연결을 시도합니다. 실패하면 장애 조치(failover) 파트너로 연결을 시도합니다. 미러 데이터베이스가 파트너 서버의 주 역할로 이미 전환된 경우에는 연결이 성공하고 새로운 주-미러 매핑이 클라이언트로 전송되며 호출 <xref:System.AppDomain>의 수명 동안 캐시됩니다. 이 매핑은 영구 스토리지에 저장되지 않으므로 다른 **AppDomain** 또는 프로세스의 후속 연결에는 사용할 수 없습니다. 그러나 동일한 **AppDomain** 내에서의 후속 연결에는 사용할 수 있습니다. 같거나 다른 컴퓨터에서 실행되는 다른 **AppDomain** 또는 프로세스에는 항상 연결 풀이 있으며 이러한 연결은 다시 설정되지 않습니다. 이 경우 주 데이터베이스가 다운되면 각 프로세스 또는 **AppDomain**이 실패하고 나서 풀이 자동으로 지워집니다.  
  
> [!NOTE]
> 서버에서의 미러링 지원은 데이터베이스별로 구성됩니다. 다중 파트 이름을 사용하거나 현재 데이터베이스를 변경하는 방식으로 주/미러 집합에 포함되지 않은 다른 데이터베이스에 대해 데이터 조작 작업이 실행되는 경우, 이러한 다른 데이터베이스에 대한 변경 내용은 실패 시 전파되지 않습니다. 미러되지 않은 데이터베이스에서 데이터가 수정되는 경우에는 오류가 발생하지 않습니다. 개발자는 이러한 작업이 미칠 수 있는 영향을 평가해야 합니다.  
  
## <a name="database-mirroring-resources"></a>데이터베이스 미러링 리소스  

 미러링 구성, 배포 및 관리에 대한 개념 설명서 및 정보를 보려면 SQL Server 설명서에서 다음 리소스를 참조하세요.  
  
|리소스|설명|  
|--------------|-----------------|  
|[데이터베이스 미러링](/sql/database-engine/database-mirroring/database-mirroring-sql-server)|SQL Server에서 미러링을 설정 및 구성하는 방법을 설명합니다.|  
  
## <a name="see-also"></a>참고 항목

- [ADO.NET 개요](../ado-net-overview.md)
