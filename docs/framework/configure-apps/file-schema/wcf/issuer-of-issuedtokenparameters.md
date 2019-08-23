---
title: <issuedTokenParameters>의 <issuer>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: 77ed9534ce872e805a6a6ea2c21a38710e6bc0fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925261"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="1e6ad-102">\<issuedTokenParameters >의 \<발급자 ></span><span class="sxs-lookup"><span data-stu-id="1e6ad-102">\<issuer> of \<issuedTokenParameters></span></span>
<span data-ttu-id="1e6ad-103">보안 토큰을 발급하는 STS(보안 토큰 서비스)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ad-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="1e6ad-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1e6ad-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1e6ad-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="1e6ad-105">\<bindings></span></span>  
<span data-ttu-id="1e6ad-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="1e6ad-106">\<customBinding></span></span>  
<span data-ttu-id="1e6ad-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="1e6ad-107">\<binding></span></span>  
<span data-ttu-id="1e6ad-108">\<security></span><span class="sxs-lookup"><span data-stu-id="1e6ad-108">\<security></span></span>  
<span data-ttu-id="1e6ad-109">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="1e6ad-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="1e6ad-110">\<issuer></span><span class="sxs-lookup"><span data-stu-id="1e6ad-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e6ad-111">구문</span><span class="sxs-lookup"><span data-stu-id="1e6ad-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e6ad-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1e6ad-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1e6ad-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ad-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e6ad-114">특성</span><span class="sxs-lookup"><span data-stu-id="1e6ad-114">Attributes</span></span>  
  
|<span data-ttu-id="1e6ad-115">특성</span><span class="sxs-lookup"><span data-stu-id="1e6ad-115">Attribute</span></span>|<span data-ttu-id="1e6ad-116">설명</span><span class="sxs-lookup"><span data-stu-id="1e6ad-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1e6ad-117">주소</span><span class="sxs-lookup"><span data-stu-id="1e6ad-117">address</span></span>|<span data-ttu-id="1e6ad-118">필수 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ad-118">Required string.</span></span> <span data-ttu-id="1e6ad-119">STS의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ad-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e6ad-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1e6ad-120">Child Elements</span></span>  
  
|<span data-ttu-id="1e6ad-121">요소</span><span class="sxs-lookup"><span data-stu-id="1e6ad-121">Element</span></span>|<span data-ttu-id="1e6ad-122">Description</span><span class="sxs-lookup"><span data-stu-id="1e6ad-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e6ad-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="1e6ad-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="1e6ad-124">작성기에서 만들 수 있는 엔드포인트의 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ad-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="1e6ad-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="1e6ad-125">\<identity></span></span>](identity.md)|<span data-ttu-id="1e6ad-126">발급된 토큰을 사용하는 경우 클라이언트가 서버를 인증할 수 있도록 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ad-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1e6ad-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1e6ad-127">Parent Elements</span></span>  
  
|<span data-ttu-id="1e6ad-128">요소</span><span class="sxs-lookup"><span data-stu-id="1e6ad-128">Element</span></span>|<span data-ttu-id="1e6ad-129">Description</span><span class="sxs-lookup"><span data-stu-id="1e6ad-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e6ad-130">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="1e6ad-130">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="1e6ad-131">현재 발급된 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ad-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1e6ad-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="1e6ad-132">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="1e6ad-133">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="1e6ad-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="1e6ad-134">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="1e6ad-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="1e6ad-135">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="1e6ad-135">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="1e6ad-136">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="1e6ad-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="1e6ad-137">바인딩</span><span class="sxs-lookup"><span data-stu-id="1e6ad-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1e6ad-138">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="1e6ad-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="1e6ad-139">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="1e6ad-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="1e6ad-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="1e6ad-140">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="1e6ad-141">방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="1e6ad-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="1e6ad-142">사용자 지정 바인딩 보안</span><span class="sxs-lookup"><span data-stu-id="1e6ad-142">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
