---
title: '완화: X509CertificateClaimSet.FindClaims 메서드'
ms.date: 03/30/2017
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ffc03e6c88a2aabb967587d8b1ee7d0b784b4e7d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70778941"
---
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a><span data-ttu-id="fdda0-102">완화: X509CertificateClaimSet.FindClaims 메서드</span><span class="sxs-lookup"><span data-stu-id="fdda0-102">Mitigation: X509CertificateClaimSet.FindClaims Method</span></span>
<span data-ttu-id="fdda0-103">.NET Framework 4.6.1을 대상으로 하는 앱부터 <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> 메서드는 `claimType` 인수를 해당 SAN 필드의 모든 DNS 항목과 일치시키려 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdda0-103">Starting with apps that target the .NET Framework 4.6.1,  the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method will attempt to match the `claimType` argument with all the DNS entries in its SAN field.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="fdda0-104">영향</span><span class="sxs-lookup"><span data-stu-id="fdda0-104">Impact</span></span>  
 <span data-ttu-id="fdda0-105">이 변경은 .NET Framework 4.6.1로 시작하는 .NET Framework 버전을 대상으로 하는 애플리케이션에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fdda0-105">This change only affects apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1.</span></span>  
  
 <span data-ttu-id="fdda0-106">이전 버전의 .NET Framework를 대상으로 하는 앱의 경우에는 <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> 메서드가 `claimType` 인수를 마지막 DNS 항목에만 일치시키려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdda0-106">For apps that target previous versions of the .NET Framework, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method attempts to match the `claimType` argument only with the last  DNS entry.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="fdda0-107">완화</span><span class="sxs-lookup"><span data-stu-id="fdda0-107">Mitigation</span></span>  
 <span data-ttu-id="fdda0-108">이러한 변경을 원치 않는 경우 .NET Framework 4.6.1로 시작하는 .NET Framework 버전을 대상으로 하는 앱은 앱 구성 파일의 [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 설정을 추가하여 이 동작을 사용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdda0-108">If this change is undesirable, apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1 can opt out of it by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />   
</runtime>  
```  
  
 <span data-ttu-id="fdda0-109">또한 이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.6.1 및 이후 버전에서 실행되는 앱은 앱 구성 파일의 [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 설정을 추가하여 이 동작을 옵트인(opt in)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdda0-109">In addition, apps that target previous versions of the .NET Framework but are running under the .NET Framework 4.6.1 and later versions can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />   
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fdda0-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fdda0-110">See also</span></span>

- [<span data-ttu-id="fdda0-111">대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="fdda0-111">Retargeting Changes</span></span>](retargeting-changes-in-the-net-framework-4-6-1.md)
