---
title: 세계화 구성 설정
description: '.NET Core 앱의 세계화 측면(예: 일본 날짜를 구문 분석하는 방식)을 구성하는 런타임 설정에 대해 알아봅니다.'
ms.date: 05/18/2020
ms.topic: reference
ms.openlocfilehash: fc98e965093c28b75b9b66e4f1c9f147abd4680e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721917"
---
# <a name="run-time-configuration-options-for-globalization"></a>세계화를 위한 런타임 구성 옵션

## <a name="invariant-mode"></a>고정 모드

- .NET Core 앱이 문화권별 데이터와 동작에 액세스하지 않고 세계화 고정 모드에서 실행되는지 여부를 결정합니다.
- 이 설정을 생략하면 앱이 문화권 데이터에 액세스할 수 있는 상태로 실행됩니다. 이는 값을 `false`로 설정하는 것과 같습니다.
- 자세한 내용은 [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md)(.NET Core 세계화 고정 모드)를 참조하세요.

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | `System.Globalization.Invariant` | `false` - 문화권 데이터에 액세스<br/>`true` - 고정 모드에서 실행 |
| **MSBuild 속성** | `InvariantGlobalization` | `false` - 문화권 데이터에 액세스<br/>`true` - 고정 모드에서 실행 |
| **환경 변수** | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | `0` - 문화권 데이터에 액세스<br/>`1` - 고정 모드에서 실행 |

### <a name="examples"></a>예

*runtimeconfig.json* 파일:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Globalization.Invariant": true
      }
   }
}
```

프로젝트 파일:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>

</Project>
```

## <a name="era-year-ranges"></a>연대 연도 범위

- 여러 연대를 지원하는 달력의 범위 검사가 완화적인지 아니면 특정 연대의 날짜 범위를 오버플로하는 날짜는 <xref:System.ArgumentOutOfRangeException>을 throw하는지를 결정합니다.
- 이 설정을 생략하면 범위 검사가 완화됩니다. 이는 값을 `false`로 설정하는 것과 같습니다.
- 자세한 내용은 [달력, 연대 및 날짜 범위: 완화 범위 검사](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks)를 참조하세요.

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | `false` - 완화 범위 검사<br/>`true` - 오버플로 시 예외 발생 |
| **환경 변수** | N/A | N/A |

## <a name="japanese-date-parsing"></a>일본 날짜 구문 분석

- 연도로 “1” 또는 “Gannen”을 포함하는 문자열이 성공적으로 구문 분석되는지 아니면 “1”만 지원되는지를 결정합니다.
- 이 설정을 생략하면 "1" 또는 "Gannen"를 연도로 포함하는 문자열이 성공적으로 구문 분석됩니다. 이는 값을 `false`로 설정하는 것과 같습니다.
- 자세한 내용은 [달력의 날짜를 여러 연대로 표현](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)을 참조하세요.

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | `false` - “Gannen” 또는 “1”이 지원됨<br/>`true` - “1”만 지원됨 |
| **환경 변수** | N/A | N/A |

## <a name="japanese-year-format"></a>일본 연도 형식

- 일본 달력 연대의 첫해의 형식이 “Gannen”으로 지정되는지 아니면 숫자로 지정되는지를 결정합니다.
- 이 설정을 생략하면 첫 번째 연도가 "Gannen"으로 서식 지정됩니다. 이는 값을 `false`로 설정하는 것과 같습니다.
- 자세한 내용은 [달력의 날짜를 여러 연대로 표현](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)을 참조하세요.

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | `false` - “Gannen”으로 형식 지정<br/>`true` - 숫자로 형식 지정 |
| **환경 변수** | N/A | N/A |

## <a name="nls"></a>NLS

- .NET에서 Windows 앱에 NLS(국가별 언어 지원) 또는 ICU(International Components for Unicode) 세계화 API를 사용하는지 여부를 결정합니다. .NET 5.0 이상 버전에서는 기본적으로 Windows 10 2019년 5월 업데이트 이상 버전에 ICU 세계화 API를 사용합니다.
- 이 설정을 생략하면 .NET는 기본적으로 ICU 세계화 API를 사용합니다. 이는 값을 `false`로 설정하는 것과 같습니다.
- 자세한 내용은 [Windows에서 세계화 API가 ICU 라이브러리를 사용](../compatibility/globalization/5.0/icu-globalization-api.md)을 참조하세요.

| | 설정 이름 | 값 | 도입 |
| - | - | - | - |
| **runtimeconfig.json** | `System.Globalization.UseNls` | `false` - ICU 세계화 API를 사용<br/>`true` - NLS 세계화 API를 사용 | .NET 5.0 |
| **환경 변수** | `DOTNET_SYSTEM_GLOBALIZATION_USENLS` | `false` - ICU 세계화 API를 사용<br/>`true` - NLS 세계화 API를 사용 | .NET 5.0 |
