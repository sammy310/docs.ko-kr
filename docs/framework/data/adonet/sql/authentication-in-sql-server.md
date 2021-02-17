---
title: SQL Server에서 인증
description: Windows 인증 모드 및 혼합 모드를 포함 하 여 ADO.NET에 대 한 SQL Server 인증에 대해 알아봅니다.
ms.date: 05/22/2018
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
ms.openlocfilehash: a1ecc0debd584797f72a89318aadc6ccc8a41062
ms.sourcegitcommit: f0fc5db7bcbf212e46933e9cf2d555bb82666141
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2021
ms.locfileid: "100581927"
---
# <a name="authentication-in-sql-server"></a>SQL Server에서 인증

SQL Server에서는 Windows 인증 모드와 혼합 모드의 두 가지 인증 모드를 지원합니다.  
  
- Windows 인증은 기본 인증이며 흔히 통합 보안이라고 하는데, 그 이유는 이 SQL Server 보안 모델이 Windows와 긴밀하게 통합되기 때문입니다. 특정 Windows 사용자 및 그룹 계정은 SQL Server에 로그인할 수 있습니다. 이미 인증된 Windows 사용자는 추가 자격 증명을 제공할 필요가 없습니다.  
  
- 혼합 모드에서는 Windows 인증과 SQL Server 인증을 모두 지원하며 사용자 이름 및 암호 쌍이 SQL Server 내에서 유지 관리됩니다.  
  
> [!IMPORTANT]
> 가능하면 Windows 인증을 사용하는 것이 좋습니다. Windows 인증은 일련의 암호화된 메시지를 사용하여 SQL Server에서 사용자를 인증합니다. SQL Server 로그인을 사용하는 경우 SQL Server 로그인 이름과 암호화된 암호가 네트워크를 통해 전달되므로 Windows 인증에 비해 보안이 떨어집니다.  
  
 Windows 인증을 사용하는 경우 사용자가 Windows에 이미 로그온되어 있으므로 SQL Server에 별도로 로그온할 필요가 없습니다. 다음 `SqlConnection.ConnectionString`은 사용자가 사용자 이름이나 암호를 제공할 필요가 없는 Windows 인증을 지정합니다.  
  
```csharp  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;"
```  
  
> [!NOTE]
> 로그인은 데이터베이스 사용자와 구분됩니다. 별도의 작업으로 로그인 또는 Windows 그룹을 데이터베이스 사용자 또는 역할에 매핑해야 합니다. 그런 다음 사용자 또는 역할에 데이터베이스 개체에 액세스할 수 있는 권한을 부여합니다.  
  
## <a name="authentication-scenarios"></a>인증 시나리오  

 Windows 인증은 일반적으로 다음과 같은 경우에 가장 적합합니다.  
  
- 도메인 컨트롤러가 있는 경우  
  
- 애플리케이션과 데이터베이스가 같은 컴퓨터에 있는 경우  
  
- SQL Server Express 또는 LocalDB의 인스턴스를 사용하는 경우  
  
 SQL Server 로그인은 다음과 같은 경우에 자주 사용됩니다.  
  
- 작업 그룹이 있는 경우  
  
- 사용자가 신뢰할 수 없는 다른 도메인에서 연결하는 경우  
  
- ASP.NET와 같은 인터넷 애플리케이션  
  
> [!NOTE]
> Windows 인증을 지정하더라도 SQL Server 로그인이 비활성화되지는 않습니다. 따라서 높은 수준의 권한이 있는 SQL Server 로그인은 ALTER LOGIN DISABLE Transact-SQL 문을 사용하여 비활성화해야 합니다.  
  
## <a name="login-types"></a>로그인 유형  

 SQL Server에서는 세 가지 유형의 로그인을 지원합니다.  
  
- 로컬 Windows 사용자 계정 또는 신뢰할 수 있는 도메인 계정. SQL Server는 Windows를 통해 Windows 사용자 계정을 인증합니다.  
  
- Windows group. Windows 그룹에 액세스 권한을 부여하면 해당 그룹의 멤버인 모든 Windows 사용자 로그인에 액세스 권한이 부여됩니다.  
  
- SQL Server 로그인. SQL Server에서는 사용자 이름과 암호 해시를 모두 master 데이터베이스에 저장하고, 내부 인증 방법을 사용하여 로그인 시도가 유효한지 검사합니다.  
  
> [!NOTE]
> SQL Server에서는 코드 서명에만 사용되는 인증서 또는 비대칭 키에서 만들어진 로그인을 제공합니다. SQL Server에 연결할 때는 사용할 수 없습니다.  
  
## <a name="mixed-mode-authentication"></a>혼합 모드 인증  

 불가피하게 혼합 모드 인증을 사용하는 경우 SQL Server 로그인을 만들어야 합니다. 이 로그인은 SQL Server에 저장됩니다. 그런 다음 런타임에 SQL Server 사용자 이름과 암호를 제공해야 합니다.  
  
> [!IMPORTANT]
> SQL Server는 `sa`("시스템 관리자"의 약어)라는 SQL Server 로그인을 사용하여 설치됩니다. `sa` 로그인에 강력한 암호를 할당하고 애플리케이션에서는 `sa` 로그인을 사용하지 마세요. `sa` 로그인은 전체 서버에 대한 해지할 수 없는 관리 자격 증명을 갖는 `sysadmin` 고정 서버 역할에 매핑됩니다. 공격자가 시스템 관리자 권한으로 액세스할 경우 잠재적 피해는 무제한입니다.
  
 SQL Server는 SQL Server 로그인에 대 한 Windows 암호 정책 메커니즘을 제공 합니다. 암호 복잡성 정책은 가능한 암호의 수를 늘려 문자 조합을 이용한 공격(brute force attacks)을 방지하도록 설계되었습니다. SQL Server SQL Server 내에서 사용 되는 암호에 동일한 복잡성 및 만료 정책을 적용할 수 있습니다.  
  
> [!IMPORTANT]
> 사용자 입력에서 연결 문자열을 연결하면 연결 문자열 삽입 공격에 취약해질 수 있습니다. <xref:System.Data.SqlClient.SqlConnectionStringBuilder>를 사용하여 런타임에 구문이 올바른 연결 문자열을 만들 수 있습니다. 자세한 내용은 [연결 문자열 작성기](../connection-string-builders.md)를 참조하세요.  
  
## <a name="external-resources"></a>외부 리소스  

 자세한 내용은 다음 리소스를 참조하세요.  
  
|리소스|Description|  
|--------------|-----------------|  
|[보안 주체](/sql/relational-databases/security/authentication-access/principals-database-engine)|SQL Server의 로그인 및 기타 보안 주체에 대해 설명합니다.|  
  
## <a name="see-also"></a>참고 항목

- [ADO.NET 애플리케이션 보안](../securing-ado-net-applications.md)
- [SQL Server의 애플리케이션 보안 시나리오](application-security-scenarios-in-sql-server.md)
- [데이터 소스에 연결](../connecting-to-a-data-source.md)
- [연결 문자열](../connection-strings.md)
- [ADO.NET 개요](../ado-net-overview.md)
