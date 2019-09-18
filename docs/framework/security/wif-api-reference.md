---
title: WIF API 참조
ms.date: 03/30/2017
ms.assetid: a027d902-9314-4bfd-b172-4e81847b1d68
author: BrucePerlerMS
ms.openlocfilehash: fd7f34e619626ddca63074a89ec7253fd818ab55
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71045144"
---
# <a name="wif-api-reference"></a><span data-ttu-id="6c5a5-102">WIF API 참조</span><span class="sxs-lookup"><span data-stu-id="6c5a5-102">WIF API Reference</span></span>
<span data-ttu-id="6c5a5-103">WIF(Windows Identity Foundation) 클래스는 `mscorlib`(mscorlib.dll), `System.IdentityModel`(System.IdentityModel.dll), `System.IdentityModel.Services`(System.IdentityModel.Services.dll) 및 `System.ServiceModel`(System.ServiceModel.dll) 어셈블리에 분할됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-103">Windows Identity Foundation (WIF) classes are split across the following assemblies: `mscorlib` (mscorlib.dll), `System.IdentityModel` (System.IdentityModel.dll), `System.IdentityModel.Services` (System.IdentityModel.Services.dll), and `System.ServiceModel` (System.ServiceModel.dll).</span></span> <span data-ttu-id="6c5a5-104">이 항목에서는 WIF 네임스페이스에 대한 링크 및 각 네임스페이스에 포함된 클래스에 대한 간략한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-104">This topic provides links to the WIF namespaces and brief explanations of the classes that each namespace contains.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6c5a5-105">다음 `System.IdentityModel` 네임스페이스에는 WCF 클레임 기반 ID 모델을 구현하는 클래스가 포함됩니다. <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType> 및 <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-105">The following `System.IdentityModel` namespaces contain classes that implement the WCF claims-based identity model: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType>, and <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6c5a5-106">.NET Framework 4.5부터 WCF 클레임 기반 ID 모델은 WIF로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-106">Starting with .NET Framework 4.5, the WCF claims-based identity model is superseded by WIF.</span></span> <span data-ttu-id="6c5a5-107">WIF를 기반으로 솔루션을 빌드할 때 이러한 세 개의 네임스페이스에서 클래스를 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-107">You should not use classes in these three namespaces when building solutions based on WIF.</span></span>  
  
 <xref:System.IdentityModel?displayProperty=nameWithType>  
 <span data-ttu-id="6c5a5-108">쿠키 변환, 보안 토큰 서비스 및 특수 XML 사전 판독기를 나타내는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-108">Contains classes that represent cookie transforms, security token services, and specialized XML dictionary readers.</span></span>  
  
 <xref:System.IdentityModel.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="6c5a5-109">WIF(Windows Identity Foundation)를 사용하여 빌드된 애플리케이션 및 서비스에 대한 구성을 제공하는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-109">Contains classes that provide configuration for applications and services built using the Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="6c5a5-110">이 네임 스페이스의 클래스는 [\<identityConfiguration>](../configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소 아래에 있는 설정을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-110">The classes in this namespace represent settings under the [\<identityConfiguration>](../configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span>  
  
 <xref:System.IdentityModel.Metadata?displayProperty=nameWithType>  
 <span data-ttu-id="6c5a5-111">페더레이션 메타데이터 문서에 있는 요소를 나타내는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-111">Contains classes that represent elements in a Federation Metadata document.</span></span>  
  
 <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType>  
 <span data-ttu-id="6c5a5-112">WS-Trust 아티팩트를 나타내는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-112">Contains classes that represent WS-Trust artifacts.</span></span>  
  
 <xref:System.IdentityModel.Services?displayProperty=nameWithType>  
 <span data-ttu-id="6c5a5-113">수동(WS-Federation) 시나리오에서 사용되는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-113">Contains classes that are used in passive (WS-Federation) scenarios.</span></span> <span data-ttu-id="6c5a5-114">또한 [\<system.identityModel.services>](../configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) 요소 아래에 있는 설정을 나타내는 일부 클래스도 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-114">Also contains some classes that represent settings under the [\<system.identityModel.services>](../configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) element.</span></span> <span data-ttu-id="6c5a5-115">이 요소 아래에 있는 설정은 애플리케이션에 대해 WS-Federation을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-115">Settings under this element configure WS-Federation for applications.</span></span> <span data-ttu-id="6c5a5-116">`System.IdentityModel.Services.Configuration` 네임스페이스에는 WS-Federation 구성에 사용되는 클래스가 대부분 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-116">The `System.IdentityModel.Services.Configuration` namespace contains most of the classes that are used to configure WS-Federation.</span></span>  
  
 <xref:System.IdentityModel.Services.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="6c5a5-117">WS-Federation 프로토콜을 사용하는 WIF 애플리케이션에 대한 구성을 제공하는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-117">Contains classes that provide configuration for WIF applications that use the WS-Federation protocol.</span></span> <span data-ttu-id="6c5a5-118">이 네임스페이스의 클래스는 [\<system.identityModel.services>](../configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) 요소 아래에 있는 설정을 나타내는 일부 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-118">The classes in this namespace represent settings under the [\<system.identityModel.services>](../configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) element.</span></span> <span data-ttu-id="6c5a5-119">`System.IdentityModel.Services` 네임스페이스에는 WS-Federation 구성에 사용되는 일부 클래스도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-119">The `System.IdentityModel.Services` namespace also contains some classes that are used to configure WS-Federation.</span></span>  
  
 <xref:System.IdentityModel.Services.Tokens?displayProperty=nameWithType>  
 <span data-ttu-id="6c5a5-120">웹 팜 시나리오에 대한 특수 보안 토큰 처리기를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-120">Contains specialized security token handlers for Web farm scenarios.</span></span>  
  
 <xref:System.IdentityModel.Tokens?displayProperty=nameWithType>  
 <span data-ttu-id="6c5a5-121">보안 토큰, 보안 토큰 처리기 및 기타 보안 토큰 아티팩트를 나타내는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-121">Contains classes that represent security tokens, security token handlers, and other security token artifacts.</span></span>  
  
 <xref:System.Security.Claims?displayProperty=nameWithType>  
 <span data-ttu-id="6c5a5-122">클레임, 클레임 기반 ID, 클레임 기반 주체 및 기타 클레임 기반 ID 모델 아티팩트를 나타내는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-122">Contains classes that represent claims, claims-based identities, claims-based principals, and other claims-based identity model artifacts.</span></span>  
  
 <xref:System.ServiceModel.Security?displayProperty=nameWithType>  
 <span data-ttu-id="6c5a5-123">활성(WS-Trust) 시나리오에서 사용되는 WCF 계약, 채널, 서비스 호스트 및 기타 아티팩트를 나타내는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-123">Contains classes that represent WCF contracts, channels, service hosts and other artifacts that are used in active (WS-Trust) scenarios.</span></span> <span data-ttu-id="6c5a5-124">이 네임스페이스에는 WCF(Windows Communication Foundation)에 관련이 있고 WIF에서 사용되지 않는 클래스도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5a5-124">This namespace also contains classes that are specific to Windows Communication Foundation (WCF) and that are not used by WIF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c5a5-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="6c5a5-125">See also</span></span>

- [<span data-ttu-id="6c5a5-126">WIF 구성 참조</span><span class="sxs-lookup"><span data-stu-id="6c5a5-126">WIF Configuration Reference</span></span>](wif-configuration-reference.md)
- [<span data-ttu-id="6c5a5-127">WIF 3.5와 WIF 4.5 간의 네임스페이스 매핑</span><span class="sxs-lookup"><span data-stu-id="6c5a5-127">Namespace Mapping between WIF 3.5 and WIF 4.5</span></span>](namespace-mapping-between-wif-3-5-and-wif-4-5.md)
