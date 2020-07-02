---
ms.openlocfilehash: abef47c64a7cfd99c5b50bf2100401a2d5fcc5c3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614734"
---
### <a name="x509certificateclaimsetfindclaims-considers-all-claimtypes"></a>X509CertificateClaimSet.FindClaims가 모든 claimTypes를 고려

#### <a name="details"></a>설명

.NET Framework 4.6.1을 대상으로 하는 앱에서 X509 클레임 집합이 해당 SAN 필드에 여러 DNS 항목이 있는 인증서로부터 초기화되는 경우 <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> 메서드가 claimType 인수를 모든 DNS 항목과 일치시키려고 합니다. 이전 버전의 .NET Framework를 대상으로 하는 앱의 경우 <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> 메서드는 claimType 인수를 마지막 DNS 항목과 일치시키려고 시도합니다.

#### <a name="suggestion"></a>제안 해결 방법

이 변경은 .NET Framework 4.6.1을 대상으로 하는 애플리케이션에만 영향을 줍니다. 이 변경 내용은 [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation) 호환성 스위치로 비활성화(또는 4.6.1 전 버전을 대상으로 하는 경우 활성화)될 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.6.1       |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=nameWithType>
