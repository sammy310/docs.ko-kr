---
title: System.Data.SQLite와 비교
ms.date: 12/13/2019
description: Microsoft.Data.Sqlite와 System.Data.SQLite 라이브러리 간의 차이점에 대해 설명합니다.
ms.openlocfilehash: 076bbc6f746cf9296c96ec73047397a21a3b2558
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900706"
---
# <a name="comparison-to-systemdatasqlite"></a>System.Data.SQLite와 비교

2005년에 Robert Simpson은 ADO.NET 2.0에 대한 SQLite 공급자인 System.Data.SQLite를 만들었습니다. 2010년에 SQLite 팀은 프로젝트를 유지 관리하고 개발했습니다. 또한 2007년에 Mono 팀이 Mono.Data.Sqlite로 코드를 포크했다는 것도 주목할 필요가 있습니다. System.Data.SQLite는 오랜 역사를 가지고 있으며 Visual Studio 도구를 사용하여 안정적이고 완전한 기능을 갖춘 ADO.NET 공급자로 발전했습니다. 새 릴리스는 모든 버전의 .NET Framework와 호환되는 어셈블리를 버전 2.0 및 .NET Compact Framework 3.5로 다시 계속해서 제공합니다.

.NET Core(2016년에 출시)의 첫 번째 버전은 .NET의 단일, 경량, 최신 및 플랫폼 간 구현입니다. 더 최신 대안이 포함된 사용되지 않는 API 및 API는 의도적으로 제거되었습니다. ADO.NET에는 DataSet API(DataTable 및 DataAdapter 포함)가 포함되어 있지 않았습니다.

Entity Framework 팀은 System.Data.SQLite 코드베이스를 사용하는 것이 약간 익숙했을 것입니다. EF 팀의 멤버인 Brice Lambson은 이전에 SQLite 팀이 Entity Framework 버전 5 및 6에 대한 지원을 추가하는 것을 도왔습니다. 또한 Brice는 .NET Core를 계획하는 동시에 SQLite ADO.NET 공급자를 자체적으로 구현하는 실험을 하고 있었습니다. 자세한 논의 후 Entity Framework 팀은 Brice의 프로토타입을 기반으로 하는 Microsoft.Data.Sqlite를 만들도록 결정했습니다. 이를 통해 .NET Core의 목표에 맞게 새로운 경량의 최신 구현을 만들 수 있습니다.

더 최신을 의미하는 예제로, System.Data.SQLite 및 Microsoft.Data.Sqlite 모두에서 [사용자 정의 함수](user-defined-functions.md)를 만드는 코드는 다음과 같습니다.

```csharp
// System.Data.SQLite
connection.BindFunction(
    new SQLiteFunctionAttribute("ceiling", 1, FunctionType.Scalar),
    (Func<object[], object>)((object[] args) => Math.Ceiling((double)((object[])args[1])[0])),
    null);

// Microsoft.Data.Sqlite
connection.CreateFunction(
    "ceiling",
    (double arg) => Math.Ceiling(arg));
```

2017년에 .NET Core 2.0은 전략의 변화를 경험했습니다. .NET Framework와의 호환성이 .NET Core의 성공에 중요한 것으로 결정되었습니다. DataSet API를 포함하여 제거된 API의 대부분이 다시 추가되었습니다. 다른 많은 사용자의 경우와 마찬가지로 .NET Core로 이식할 수 있도록 System.Data.SQLite를 차단 해제했습니다. 그러나 간단하고 현대적이어야 하는 Microsoft.Data.Sqlite의 목표는 그대로 남아 있습니다. Microsoft.Data.Sqlite에서 구현되지 않은 ADO.NET API에 대한 자세한 내용은 [ADO.NET 제한 사항](adonet-limitations.md)을 참조하세요.

새 기능이 Microsoft.Data.Sqlite에 추가되는 경우에는 System.Data.SQLite의 설계가 고려됩니다. 가능하면 두 항목 간의 변경 내용을 최소화하여 두 항목 사이를 쉽게 전환할 수 있도록 시도합니다.

## <a name="data-types"></a>데이터 형식

Microsoft.Data.Sqlite와 System.Data.SQLite의 가장 큰 차이점은 데이터 형식이 처리되는 방법입니다. [데이터 형식](types.md)에 설명된 것처럼 Microsoft.Data.Sqlite는 모든 임의 문자열을 열 형식으로 지정할 수 있도록 하는 SQLite의 기본 기이함을 숨기려고 시도하지 않으며, 다음 네 가지 기본 형식만 있습니다. INTEGER, REAL, TEXT 및 BLOB

System.Data.SQLite는 .NET 형식에 직접 매핑하는 열 형식에 추가 의미 체계를 적용합니다. 이렇게 하면 공급자에게 더 강력한 형식의 느낌을 주지만 몇 가지 다듬어지지 못한 점들이 있습니다. 예를 들어 SELECT 문에 식의 열 형식을 지정하도록 새 SQL 문(TYPES)을 도입해야 했습니다.

## <a name="connection-strings"></a>연결 문자열

Microsoft.Data.Sqlite에는 훨씬 더 적은 [연결 문자열](connection-strings.md) 키워드가 있습니다. 다음 표에서는 대신 사용할 수 있는 대체 방법을 보여 줍니다.

| 키워드          | 대체                                         |
| ---------------- | --------------------------------------------------- |
| 캐시 크기       | `PRAGMA cache_size = <pages>` 보내기                  |
| 기본 시간 제한  | SqliteConnection에서 DefaultTimeout 속성 사용 |
| FailIfMissing    | `Mode=ReadWrite` 사용                                |
| FullUri          | 데이터 원본 키워드 사용                         |
| 저널 모드     | `PRAGMA journal_mode = <mode>` 보내기                 |
| 레거시 형식    | `PRAGMA legacy_file_format = 1` 보내기                |
| 최대 페이지 수   | `PRAGMA max_page_count = <pages>` 보내기              |
| 페이지 크기        | `PRAGMA page_size = <bytes>` 보내기                   |
| 읽기 전용        | `Mode=ReadOnly` 사용                                 |
| 동기      | `PRAGMA synchronous = <mode>` 보내기                  |
| URI              | 데이터 원본 키워드 사용                         |
| UseUTF16Encoding | `PRAGMA encoding = 'UTF-16'` 보내기                   |

## <a name="authorization"></a>권한 부여

Microsoft.Data.Sqlite에는 SQLite의 권한 부여 콜백을 노출하는 API가 없습니다. [#13835](https://github.com/dotnet/efcore/issues/13835) 문제를 사용하여 이 기능에 대한 피드백을 제공합니다.

## <a name="data-change-notifications"></a>데이터 변경 알림

Microsoft.Data.Sqlite에는 SQLite의 데이터 변경 알림을 노출하는 API가 없습니다. [#13827](https://github.com/dotnet/efcore/issues/13827) 문제를 사용하여 이 기능에 대한 피드백을 제공합니다.

## <a name="virtual-table-modules"></a>가상 테이블 모듈

Microsoft.Data.Sqlite에는 가상 테이블 모듈을 만들기 위한 API가 없습니다. [#13823](https://github.com/dotnet/efcore/issues/13823) 문제를 사용하여 이 기능에 대한 피드백을 제공합니다.

## <a name="see-also"></a>참조

* [데이터 형식](types.md)
* [연결 문자열](connection-strings.md)
* [암호화](encryption.md)
* [ADO.NET 제한 사항](adonet-limitations.md)
* [Dapper 제한 사항](dapper-limitations.md)
