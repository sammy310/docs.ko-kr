---
title: <issuedTokenParameters>의 <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: d9d7d41277eff1de43f717816b35fdc10d52192e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928871"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="5c36e-102">\<issuedTokenParameters의 \<issuerMetadata > ></span><span class="sxs-lookup"><span data-stu-id="5c36e-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>
<span data-ttu-id="5c36e-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5c36e-103">\<system.serviceModel></span></span>  
<span data-ttu-id="5c36e-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5c36e-104">\<bindings></span></span>  
<span data-ttu-id="5c36e-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5c36e-105">\<customBinding></span></span>  
<span data-ttu-id="5c36e-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="5c36e-106">\<binding></span></span>  
<span data-ttu-id="5c36e-107">\<security></span><span class="sxs-lookup"><span data-stu-id="5c36e-107">\<security></span></span>  
<span data-ttu-id="5c36e-108">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="5c36e-108">\<issuedTokenParameters></span></span>  
<span data-ttu-id="5c36e-109">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="5c36e-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c36e-110">구문</span><span class="sxs-lookup"><span data-stu-id="5c36e-110">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c36e-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5c36e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5c36e-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5c36e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c36e-113">특성</span><span class="sxs-lookup"><span data-stu-id="5c36e-113">Attributes</span></span>  
  
|<span data-ttu-id="5c36e-114">특성</span><span class="sxs-lookup"><span data-stu-id="5c36e-114">Attribute</span></span>|<span data-ttu-id="5c36e-115">설명</span><span class="sxs-lookup"><span data-stu-id="5c36e-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5c36e-116">주소</span><span class="sxs-lookup"><span data-stu-id="5c36e-116">address</span></span>|<span data-ttu-id="5c36e-117">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="5c36e-117">Required.</span></span> <span data-ttu-id="5c36e-118">엔드포인트의 주소를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5c36e-118">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="5c36e-119">주소는 절대 URI이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c36e-119">The address must be an absolute URI.</span></span> <span data-ttu-id="5c36e-120">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5c36e-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c36e-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5c36e-121">Child Elements</span></span>  
  
|<span data-ttu-id="5c36e-122">요소</span><span class="sxs-lookup"><span data-stu-id="5c36e-122">Element</span></span>|<span data-ttu-id="5c36e-123">설명</span><span class="sxs-lookup"><span data-stu-id="5c36e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c36e-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="5c36e-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="5c36e-125">주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5c36e-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="5c36e-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="5c36e-126">\<identity></span></span>](identity.md)|<span data-ttu-id="5c36e-127">한 엔드포인트에서 다른 엔드포인트와 메시지를 교환할 때 상대 엔드포인트를 인증할 수 있도록 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5c36e-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5c36e-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5c36e-128">Parent Elements</span></span>  
  
|<span data-ttu-id="5c36e-129">요소</span><span class="sxs-lookup"><span data-stu-id="5c36e-129">Element</span></span>|<span data-ttu-id="5c36e-130">Description</span><span class="sxs-lookup"><span data-stu-id="5c36e-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c36e-131">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="5c36e-131">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="5c36e-132">페더레이션 보안 시나리오에서 발급된 보안 토큰에 대한 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c36e-132">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c36e-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="5c36e-133">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="5c36e-134">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="5c36e-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="5c36e-135">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="5c36e-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="5c36e-136">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="5c36e-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="5c36e-137">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="5c36e-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="5c36e-138">바인딩</span><span class="sxs-lookup"><span data-stu-id="5c36e-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5c36e-139">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="5c36e-139">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5c36e-140">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="5c36e-140">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="5c36e-141">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5c36e-141">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="5c36e-142">방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="5c36e-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="5c36e-143">사용자 지정 바인딩 보안</span><span class="sxs-lookup"><span data-stu-id="5c36e-143">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
