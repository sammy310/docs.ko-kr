---
ms.openlocfilehash: c103dff320ae30d02c12ea5c585a47b589da8237
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621309"
---
### <a name="contentdisposition-datetimes-returns-slightly-different-string"></a>ContentDisposition DateTimes는 약간 다른 문자열을 반환합니다

#### <a name="details"></a>세부 정보

4\.6부터 <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName>의 문자열 표현이 항상 <xref:System.DateTime?displayProperty=fullName>의 시간 구성 요소를 두 자리로 표시하도록 업데이트되었습니다. 이것은 [RFC822](https://www.ietf.org/rfc/rfc0822.txt) 및 [RFC2822](https://www.ietf.org/rfc/rfc2822.txt)를 준수하기 위함입니다. 이로 인해 4.6에서 <xref:System.Net.Mime.ContentDisposition.ToString>은 처리 시간 요소 중 하나가 오전 10시 전인 시나리오에서 약간 다른 문자열을 반환합니다. ContentDispositions는 가끔 문자열로 변환하여 직렬화되므로 모든 <xref:System.Net.Mime.ContentDisposition.ToString> 작업, 직렬화 또는 GetHashCode 호출이 검토되어야 합니다.

#### <a name="suggestion"></a>제안 해결 방법

다른 .NET Framework 버전에서 ContentDispositions의 문자열 표현이 서로 올바르게 비교할 것으로 기대하지 마십시오. 가능하면 비교를 수행하기 전에 문자열을 다시 ContentDispositions로 변환합니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |부|
|버전|4.6|
|형식|런타임

#### <a name="affected-apis"></a>영향을 받는 API

-<xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=nameWithType></li><li><xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=nameWithType></li></ul>|
