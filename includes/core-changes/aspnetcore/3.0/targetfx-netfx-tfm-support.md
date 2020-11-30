---
ms.openlocfilehash: ec6724ab378dd614c55a024ede18d997d27be3a3
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032907"
---
### <a name="target-framework-net-framework-support-dropped"></a>대상 프레임워크: .NET Framework 지원 삭제

ASP.NET Core 3.0부터 .NET Framework는 지원되는 않는 대상 프레임워크입니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Framework 4.8은 .NET Framework의 마지막 주 버전입니다. 새 ASP.NET Core 앱은 .NET Core를 기반으로 빌드해야 합니다. .NET Core 3.0 릴리스부터는 ASP.NET Core 3.0을 .NET Core의 일부로 간주할 수 있습니다.

.NET Framework와 함께 ASP.NET Core를 사용하는 고객은 [2.1 LTS 릴리스](https://dotnet.microsoft.com/download/dotnet-core/2.1)를 사용하여 완전히 지원되는 방식으로 계속할 수 있습니다. 2\.1에 대한 지원 및 서비스는 2021년 8월 21일까지 계속됩니다. 이 날짜는 [.NET 지원 정책](https://dotnet.microsoft.com/platform/support-policy)에 따라 LTS 릴리스가 선언된 후 3년입니다. **.NET Framework에서** ASP.NET Core 2.1 패키지에 대한 지원은 [다른 패키지 기반 ASP.NET 프레임워크에 대한 서비스 정책](https://dotnet.microsoft.com/platform/support/policy/aspnet)과 유사하게 무기한으로 확장됩니다.

.NET Framework에서 .NET Core로 포팅하는 방법에 대한 자세한 내용은 [.NET Core로 포팅](~/docs/core/porting/index.md)을 참조하세요.

`Microsoft.Extensions` 패키지(예: 로깅, 종속성 주입 및 구성)와 Entity Framework Core는 영향을 받지 않습니다. .NET Standard를 계속 지원합니다.

이러한 변경의 동기에 대한 자세한 내용은 [원래 블로그 게시물](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/)을 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

ASP.NET Core 앱은 .NET Core 또는 .NET Framework에서 실행될 수 있습니다.

#### <a name="new-behavior"></a>새 동작

ASP.NET Core 앱은 .NET Core에서만 실행할 수 있습니다.

#### <a name="recommended-action"></a>권장 조치

다음 작업 중 하나를 수행합니다.

- 앱을 ASP.NET Core 2.1에 보관합니다.
- 앱 및 종속성을 .NET Core로 마이그레이션합니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

None

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
