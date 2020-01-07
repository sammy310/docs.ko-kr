---
title: System.object와 비교
ms.date: 12/13/2019
description: Microsoft. Sqlite 및 system.xml 라이브러리 간의 차이점에 대해 설명 합니다.
ms.openlocfilehash: dee90c132b108f2c876c0d8becc1b02035a47b61
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450281"
---
# <a name="comparison-to-systemdatasqlite"></a>System.object와 비교

2005에서는 ADO.NET 2.0에 대 한 SQLite 공급자 인 Robert를 만들었습니다. 2010에서 SQLite 팀은 프로젝트를 유지 관리 하 고 개발 했습니다. 또한 Mono 팀은 2007의 코드를 분기으로 기록 하는 것이 좋습니다. ADO.NET는 긴 기록을 포함 하 고 있으며 Visual Studio 도구를 사용 하 여 안정적이 고 완전 한 기능을 갖춘 공급자로 발전 했습니다. 새 릴리스는 모든 버전의 .NET Framework 호환 되는 어셈블리를 버전 2.0 및 .NET Compact Framework 3.5로 다시 제공 합니다.

.NET Core (2016에 출시)의 첫 번째 버전은 .NET의 단일, 경량, 최신 및 플랫폼 간 구현입니다. 더 최신 대안이 포함 된 사용 되지 않는 Api 및 Api는 의도적으로 제거 되었습니다. ADO.NET에는 데이터 집합 Api (DataTable 및 DataAdapter 포함)가 포함 되어 있지 않습니다.

Entity Framework 팀은 System.web 코드 베이스를 사용 하는 것이 약간 익숙할 것입니다. EF 팀의 멤버인 brice Lambson는 이전에 SQLite 팀에 Entity Framework 버전 5 및 6에 대 한 지원을 추가 했습니다. 또한 brice는 .NET Core를 계획 하는 동시에 SQLite ADO.NET 공급자를 자체적으로 구현 하는 방법을 시험해 볼 수 있습니다. 자세한 논의 후 Entity Framework 팀은 Brice의 프로토타입을 기반으로 하는 Microsoft. Sqlite를 만들어 결정 했습니다. 이를 통해 .NET Core의 목표에 맞게 새로운 경량 및 최신 구현을 만들 수 있습니다.

더 최신 정보를 제공 하는 예로, 다음 코드를 사용 하 여 [사용자 정의 함수](user-defined-functions.md) 를 만들 수 있습니다.

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

2017에서는 .NET Core 2.0이 전략을 변경 했습니다. .NET Framework와의 호환성이 .NET Core의 성공에 중요 한 것으로 결정 되었습니다. 데이터 집합 Api를 포함 하 여 제거 된 Api의 대부분이 다시 추가 되었습니다. 다른 많은 사용자의 경우와 마찬가지로,이를 .NET Core로 이식할 수 있도록 차단 해제 합니다. 그러나 간단 하 고 현대적인 Microsoft. Sqlite의 목표는 그대로 남아 있습니다. ADO.NET에서 구현 하지 않은 Api에 대 한 자세한 내용은 [ADO.NET 제한 사항](adonet-limitations.md) 을 참조 하세요.

새 기능이 Microsoft. Sqlite에 추가 된 경우에는 System.web의 설계가 고려 됩니다. 가능 하면 두 항목 간의 변경 내용을 최소화 하 여 두 항목 사이를 쉽게 전환할 수 있도록 시도 합니다.

## <a name="data-types"></a>데이터 형식

Microsoft. Sqlite와 System.object의 가장 큰 차이점은 데이터 형식이 처리 되는 방법입니다. [데이터 형식](types.md)에 설명 된 대로 quirkiness는 임의의 문자열을 열 형식으로 지정할 수 있도록 하는 sqlite의 기본 사용을 숨기고 정수, 실제, 텍스트 및 BLOB의 네 가지 기본 유형만 포함 합니다.

System.object는 .NET 형식에 직접 매핑하는 열 형식에 추가 의미 체계를 적용 합니다. 이렇게 하면 공급자에 게 더 강력한 형식의 느낌이 제공 되지만 몇 가지 거친 가장자리가 있습니다. 예를 들어 SELECT 문에 식의 열 유형을 지정 하기 위해 새 SQL 문 (유형)을 도입 해야 했습니다.

## <a name="connection-strings"></a>연결 문자열

Microsoft. Data. Sqlite에는 [연결 문자열](connection-strings.md) 키워드가 훨씬 줄어듭니다. 다음 표에서는 대신 사용할 수 있는 대체 방법을 보여 줍니다.

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
| Read Only        | `Mode=ReadOnly` 사용                                 |
| Synchronous      | `PRAGMA synchronous = <mode>` 보내기                  |
| URI              | 데이터 원본 키워드 사용                         |
| UseUTF16Encoding | `PRAGMA encoding = 'UTF-16'` 보내기                   |

## <a name="authorization"></a>권한 부여

Microsoft. Sqlite의 권한 부여 콜백을 노출 하는 API가 없습니다. 문제 [#13835](https://github.com/aspnet/EntityFrameworkCore/issues/13835) 를 사용 하 여이 기능에 대 한 피드백을 제공 합니다.

## <a name="data-change-notifications"></a>데이터 변경 알림

SQLite의 데이터 변경 알림을 노출 하는 API가 없습니다. 문제 [#13827](https://github.com/aspnet/EntityFrameworkCore/issues/13827) 를 사용 하 여이 기능에 대 한 피드백을 제공 합니다.

## <a name="virtual-table-modules"></a>가상 테이블 모듈

Microsoft. Data. Sqlite에는 가상 테이블 모듈을 만들기 위한 API가 없습니다. 문제 [#13823](https://github.com/aspnet/EntityFrameworkCore/issues/13823) 를 사용 하 여이 기능에 대 한 피드백을 제공 합니다.

## <a name="see-also"></a>참조

* [데이터 형식](types.md)
* [연결 문자열](connection-strings.md)
* [암호화](encryption.md)
* [ADO.NET 제한 사항](adonet-limitations.md)
* [Dapper 제한 사항](dapper-limitations.md)
