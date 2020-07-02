---
ms.openlocfilehash: 51208762cea2a5688c5d43e5d444d4e014e5f0b4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621321"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>X509Certificate2.ToString(Boolean)은 .NET이 인증서를 처리할 수 없을 때 throw하지 않습니다

#### <a name="details"></a>세부 정보

.NET Framework 4.5.2 및 이전 버전에서 verbose 매개 변수에 <code>true</code>가 전달되고 .Net Framework에서 지원하지 않는 인증서가 설치된 경우 이 메서드가 throw되었습니다. 이제 이 메서드는 성공하고 인증서의 액세스할 수 없는 부분을 생략하는 유효한 문자열을 반환합니다.

#### <a name="suggestion"></a>제안 해결 방법

<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType>에 종속된 모든 코드는 API가 이전에 throw된 일부 경우에서 반환된 문자열이 일부 인증서 데이터(예: 퍼블릭 키, 프라이빗 키 및 확장명)를 제외하도록 업데이트되어야 합니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.6|
|형식|런타임

#### <a name="affected-apis"></a>영향을 받는 API

-<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|
