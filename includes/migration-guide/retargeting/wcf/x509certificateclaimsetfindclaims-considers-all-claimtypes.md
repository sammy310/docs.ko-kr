---
ms.openlocfilehash: abef47c64a7cfd99c5b50bf2100401a2d5fcc5c3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614734"
---
### <a name="x509certificateclaimsetfindclaims-considers-all-claimtypes"></a><span data-ttu-id="65eac-101">X509CertificateClaimSet.FindClaims가 모든 claimTypes를 고려</span><span class="sxs-lookup"><span data-stu-id="65eac-101">X509CertificateClaimSet.FindClaims Considers All claimTypes</span></span>

#### <a name="details"></a><span data-ttu-id="65eac-102">설명</span><span class="sxs-lookup"><span data-stu-id="65eac-102">Details</span></span>

<span data-ttu-id="65eac-103">.NET Framework 4.6.1을 대상으로 하는 앱에서 X509 클레임 집합이 해당 SAN 필드에 여러 DNS 항목이 있는 인증서로부터 초기화되는 경우 <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> 메서드가 claimType 인수를 모든 DNS 항목과 일치시키려고 합니다. 이전 버전의 .NET Framework를 대상으로 하는 앱의 경우 <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> 메서드는 claimType 인수를 마지막 DNS 항목과 일치시키려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="65eac-103">In apps that target the .NET Framework 4.6.1, if an X509 claim set is initialized from a certificate that has multiple DNS entries in its SAN field, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> method attempts to match the claimType argument with all the DNS entries.For apps that target previous versions of the .NET Framework, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> method attempts to match the claimType argument only with the last DNS entry.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="65eac-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="65eac-104">Suggestion</span></span>

<span data-ttu-id="65eac-105">이 변경은 .NET Framework 4.6.1을 대상으로 하는 애플리케이션에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65eac-105">This change only affects applications targeting the .NET Framework 4.6.1.</span></span> <span data-ttu-id="65eac-106">이 변경 내용은 [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation) 호환성 스위치로 비활성화(또는 4.6.1 전 버전을 대상으로 하는 경우 활성화)될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65eac-106">This change may be disabled (or enabled if targeting pre-4.6.1) with the [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation) compatibility switch.</span></span>

| <span data-ttu-id="65eac-107">이름</span><span class="sxs-lookup"><span data-stu-id="65eac-107">Name</span></span>    | <span data-ttu-id="65eac-108">값</span><span class="sxs-lookup"><span data-stu-id="65eac-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="65eac-109">Scope</span><span class="sxs-lookup"><span data-stu-id="65eac-109">Scope</span></span>   | <span data-ttu-id="65eac-110">부</span><span class="sxs-lookup"><span data-stu-id="65eac-110">Minor</span></span>       |
| <span data-ttu-id="65eac-111">버전</span><span class="sxs-lookup"><span data-stu-id="65eac-111">Version</span></span> | <span data-ttu-id="65eac-112">4.6.1</span><span class="sxs-lookup"><span data-stu-id="65eac-112">4.6.1</span></span>       |
| <span data-ttu-id="65eac-113">형식</span><span class="sxs-lookup"><span data-stu-id="65eac-113">Type</span></span>    | <span data-ttu-id="65eac-114">대상 변경</span><span class="sxs-lookup"><span data-stu-id="65eac-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="65eac-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="65eac-115">Affected APIs</span></span>

- <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=nameWithType>
