---
title: Entity Framework용 SqlClient
ms.date: 03/30/2017
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
ms.openlocfilehash: e8933a975c075407066bff97672f1b82f125bb47
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2019
ms.locfileid: "67662102"
---
# <a name="sqlclient-for-the-entity-framework"></a>Entity Framework용 SqlClient
이 단원에서는 Entity Framework가 Microsoft SQL Server에서 작동할 수 있도록 하는 .NET Framework Data Provider for SQL Server(SqlClient)에 대해 설명합니다.  
  
## <a name="provider-schema-attribute"></a>공급자 스키마 특성  
 `Provider`는 SSDL(저장소 스키마 정의 언어)의 `Schema` 요소에 대한 특성입니다.  
  
 SqlClient를 사용하려면 `Provider` 요소의 `Schema` 특성에 "System.Data.SqlClient" 문자열을 할당합니다.  
  
## <a name="providermanifesttoken-schema-attribute"></a>ProviderManifestToken 스키마 특성  
 `ProviderManifestToken`은 SSDL에서 `Schema` 요소의 필수 특성입니다. 이 토큰은 오프라인 시나리오용으로 공급자 매니페스트를 로드하는 데 사용됩니다. 에 대 한 자세한 내용은 `ProviderManifestToken` 특성을 참조 하십시오 [스키마 요소 (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl)합니다.  
  
 SqlClient 다른 버전의 SQL Server에 대 한 데이터 공급자로 사용할 수 있습니다. 이러한 버전에는 서로 다른 기능이 있습니다. 예를 들어, SQL Server 2000 지원 하지 않습니다 `varchar(max)` 고 `nvarchar(max)` SQL Server 2005를 사용 하 여 도입 된 형식입니다.  
  
 SqlClient는 여러 버전의 SQL Server에 대해 다음과 같은 공급자 매니페스트 토큰을 생성하고 허용합니다.  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|-|-|-|  
|2000|2005|2008|  
  
> [!NOTE]
>  Visual Studio 2010을 사용 하 여 시작 합니다 [ADO.NET 엔터티 데이터 모델 도구](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)) SQL Server 2000을 지원 하지 않습니다.  
  
## <a name="provider-namespace-name"></a>공급자 네임스페이스 이름  
 모든 공급자에서 네임스페이스가 지정되어야 합니다. 이 속성이 있으면 특정 구문(예: 형식 및 함수)에 대해 이 공급자에서 사용할 수 있는 접두사를 Entity Framework에서 구할 수 있습니다. SqlClient 공급자 매니페스트의 네임스페이스는 `SqlServer`입니다. 네임 스페이스에 대 한 자세한 내용은 참조 하세요. [네임 스페이스](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)합니다.  
  
## <a name="types"></a>유형  
 Entity Framework에 대한 SqlClient 공급자는 개념적 모델 형식과 SQL Server 형식 간의 매핑 정보를 제공합니다. 자세한 내용은 [Entity FrameworkTypes 용 SqlClient](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)합니다.  
  
## <a name="functions"></a>함수  
 Entity Framework에 대한 SqlClient 공급자는 해당 공급자가 지원하는 함수 목록을 정의합니다. 지원 되는 함수의 목록을 참조 하세요 [Entity Framework 함수에 대 한 SqlClient](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [Entity Framework용 SqlClient 기능](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)  
  
 [Entity FrameworkTypes용 SqlClient](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)  
  
 [Entity Framework용 SqlClient에서 알려진 문제](../../../../../docs/framework/data/adonet/ef/known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a>참고자료

- [Entity SQL 언어](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [언어 참조](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
- [Entity Framework 용 SqlClient 공급자의 알려진 문제](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)
