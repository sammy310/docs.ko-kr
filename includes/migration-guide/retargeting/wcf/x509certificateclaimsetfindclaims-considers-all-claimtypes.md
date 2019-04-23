---
ms.openlocfilehash: fe5dfa0b8866debd8a6091a264e251f2fd2e4dca
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804572"
---
### <a name="x509certificateclaimsetfindclaims-considers-all-claimtypes"></a>X509CertificateClaimSet.FindClaims가 모든 claimTypes를 고려

|   |   |
|---|---|
|세부 정보|.NET Framework 4.6.1을 대상으로 하는 앱에서 X509 클레임 집합이 해당 SAN 필드에 여러 DNS 항목이 있는 인증서로부터 초기화되는 경우 <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=name> 메서드가 claimType 인수를 모든 DNS 항목과 일치시키려고 합니다. 이전 버전의 .NET Framework를 대상으로 하는 앱의 경우 <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=name> 메서드는 claimType 인수를 마지막 DNS 항목과 일치시키려고 시도합니다.|
|제안 해결 방법|이 변경은 .NET Framework 4.6.1을 대상으로 하는 애플리케이션에만 영향을 줍니다. 이 변경 내용은 [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation) 호환성 스위치로 비활성화(또는 4.6.1 전 버전을 대상으로 하는 경우 활성화)될 수 있습니다.|
|범위|부|
|버전|4.6.1|
|형식|대상 변경|
|영향을 받는 API|<ul><li><xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=nameWithType></li></ul>|
