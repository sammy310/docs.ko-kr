---
ms.openlocfilehash: a20fad5f9c95e59c14ffd91f4921cf8bfab443cd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621189"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a>유니코드 표준 버전 8.0 범주가 이제 지원됨

#### <a name="details"></a>세부 정보

.NET Framework 4.6.2에서 유니코드 데이터가 유니코드 표준 버전 6.3에서 8.0으로 업그레이드되었습니다.  .NET Framework 4.6.2에서 유니코드 문자 범주를 요청할 때 일부 결과가 이전 .NET Framework 버전의 결과와 일치하지 않을 수 있습니다.  이러한 변경은 주로 체로키어 음절 및 New Tai Lue 모음 기호 및 성조 표시에 영향을 미칩니다.

#### <a name="suggestion"></a>제안 해결 방법

코드를 검토하고 하드 코드된 유니코드 문자 범주에 종속된 논리를 제거/변경해야 합니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |부|
|버전|4.6.2|
|형식|런타임

#### <a name="affected-apis"></a>영향을 받는 API

-<xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|
