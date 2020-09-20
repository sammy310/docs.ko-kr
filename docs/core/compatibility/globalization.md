---
title: 세계화 관련 호환성이 손상되는 변경
description: .NET Core의 세계화 관련 호환성이 손상되는 변경 목록입니다.
ms.date: 04/07/2020
ms.openlocfilehash: 93990d89204df1b2d7498e1d748378fae05598c3
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065069"
---
# <a name="globalization-breaking-changes"></a>세계화 관련 호환성이 손상되는 변경

이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.

| 주요 변경 내용 | 도입된 버전 |
| - | :-: |
| [일부 라틴어-1 문자의 유니코드 범주가 변경됨](#unicode-category-changed-for-some-latin-1-characters) | 5.0 |
| [Windows에서 세계화 API가 ICU 라이브러리를 사용](#globalization-apis-use-icu-libraries-on-windows) | 5.0 |
| [StringInfo 및 TextElementEnumerator가 이제 UAX29 규격임](#stringinfo-and-textelementenumerator-are-now-uax29-compliant) | 5.0 |
| [“C” 로캘이 고정 로캘에 매핑됩니다.](#c-locale-maps-to-the-invariant-locale) | 3.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [unicode-categories-for-latin1-chars](../../../includes/core-changes/globalization/5.0/unicode-categories-for-latin1-chars.md)]

***

[!INCLUDE [icu-globalization-api](../../../includes/core-changes/globalization/5.0/icu-globalization-api.md)]

***

[!INCLUDE [uax29-compliant-grapheme-enumeration](../../../includes/core-changes/globalization/5.0/uax29-compliant-grapheme-enumeration.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE["C" locale maps to the invariant locale](~/includes/core-changes/globalization/3.0/c-locale-maps-to-invariant-locale.md)]

***
