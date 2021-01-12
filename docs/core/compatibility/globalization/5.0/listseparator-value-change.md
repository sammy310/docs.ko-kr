---
title: '호환성이 손상되는 변경: TextInfo.ListSeparator 값 변경'
description: 버전 5.0과 5.0.1 간에 TextInfo.ListSeparator의 기본값이 변경된 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 12/10/2020
ms.openlocfilehash: 720d46c1908bcd70812f575a90f580470dbc7f32
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596392"
---
# <a name="textinfolistseparator-values-changed"></a>TextInfo.ListSeparator 값이 변경됨

모든 운영 체제에서 여러 문화권의 기본 <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> 값이 변경되었습니다.

## <a name="change-description"></a>변경 내용 설명

.NET 5.0.0에서 [NLS에서 ICU 라이브러리로 전환](icu-globalization-api.md)의 일환으로 Windows에서 여러 문화권의 기본 <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> 값이 변경되었습니다. ICU(International Components for Unicode)에서 가져온 소수 구분 기호 값이 <xref:System.Globalization.TextInfo.ListSeparator> 값으로 사용되었습니다. Linux 및 macOS에서는 <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> 값이 변경되지 않았습니다. 즉, 소수 구분 기호 값을 계속 사용합니다.

.NET 5.0.1 이후 버전에서는 모든 운영 체제에서 <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>의 값은 NLS에서 얻을 수 있는 값과 동일합니다. Windows의 경우 이 값은 .NET Framework 및 .NET Core 1.0~3.1에서 사용된 값과 동일합니다. Linux 및 macOS의 경우 이제 <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> 값이 Windows의 <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> 값과 일치합니다.

다음 표에 <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> 값의 변경 내용이 요약되어 있습니다.

| | .NET Framework<br/>.NET Core 1.0 - 3.1 | .NET 5.0 | .NET 5.0.1 |
-|-|-|-
| **Windows** | NLS에서 가져옴 | ICU의 소수 구분 기호.<br/>다시 NLS로 전환할 수 있습니다. | NLS와 같음 |
| **Linux 및 macOS** | ICU의 소수 구분 기호 | ICU의 소수 구분 기호 | NLS와 같음 |

## <a name="version-introduced"></a>도입된 버전

5.0.1

## <a name="reason-for-change"></a>변경 이유

개발자가 CSV(쉼표로 구분된 값) 파일을 구문 분석할 때 <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> 속성을 사용하는 경우 새 <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> 값에서 구문 분석이 중단된다고 보고했습니다.

## <a name="recommended-action"></a>권장 조치

코드에서 이전 소수 구분 기호 값을 사용하는 경우 원하는 <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> 값을 하드 코딩할 수 있습니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=fullName>

<!--

#### Category

- Globalization

### Affected APIs

- `P:System.Globalization.TextInfo.ListSeparator`

-->
