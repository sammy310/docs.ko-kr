---
ms.openlocfilehash: 771238c53dc97f4cf4068968f3c68500ba9f87da
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198509"
---
### <a name="caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package"></a>캐싱: Microsoft.Extensions.Caching.SqlServer는 새 SqlClient 패키지를 사용합니다.

`Microsoft.Extensions.Caching.SqlServer` 패키지는 `System.Data.SqlClient` 패키지 대신 새 `Microsoft.Data.SqlClient` 패키지를 사용합니다. 이 변경으로 인해 약간의 동작이 크게 변경될 수 있습니다. 자세한 내용은 [새 Microsoft.Data.SqlClient 소개](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/)를 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

`Microsoft.Extensions.Caching.SqlServer` 패키지는 `System.Data.SqlClient` 패키지를 사용했습니다.

#### <a name="new-behavior"></a>새 동작

`Microsoft.Extensions.Caching.SqlServer`가 현재 `Microsoft.Data.SqlClient` 패키지를 사용하고 있습니다.

#### <a name="reason-for-change"></a>변경 이유

`Microsoft.Data.SqlClient`는 `System.Data.SqlClient`에서 빌드된 새 패키지입니다. 이제부터 모든 새 기능 작업이 수행됩니다.

#### <a name="recommended-action"></a>권장 작업

고객은 `Microsoft.Extensions.Caching.SqlServer` 패키지에서 반환된 형식을 사용하고 `System.Data.SqlClient` 형식으로 캐스팅하지 않는 한 이러한 호환성이 손상되는 변경에 대해 걱정할 필요가 없습니다. 예를 들어 다른 사용자가 `DbConnection`을 [이전 SqlConnection 형식](xref:System.Data.SqlClient.SqlConnection)으로 캐스팅하는 경우 캐스팅을 새 `Microsoft.Data.SqlClient.SqlConnection` 형식으로 변경해야 합니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

없음

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
