---
title: <issuedTokenParameters>의 <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: fcdd66ecd162dff5be86a1d4ab1b196f50dbd445
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400350"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="25d1f-102">\<issuedTokenParameters의 \<issuerMetadata > ></span><span class="sxs-lookup"><span data-stu-id="25d1f-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>

<span data-ttu-id="25d1f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="25d1f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="25d1f-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="25d1f-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="25d1f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="25d1f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="25d1f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="25d1f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="25d1f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="25d1f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="25d1f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<보안 >** ](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="25d1f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="25d1f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedTokenParameters >** ](issuedtokenparameters.md)</span><span class="sxs-lookup"><span data-stu-id="25d1f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span></span>\
<span data-ttu-id="25d1f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerMetadata >**</span><span class="sxs-lookup"><span data-stu-id="25d1f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25d1f-111">구문</span><span class="sxs-lookup"><span data-stu-id="25d1f-111">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25d1f-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="25d1f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="25d1f-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="25d1f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25d1f-114">특성</span><span class="sxs-lookup"><span data-stu-id="25d1f-114">Attributes</span></span>  
  
|<span data-ttu-id="25d1f-115">특성</span><span class="sxs-lookup"><span data-stu-id="25d1f-115">Attribute</span></span>|<span data-ttu-id="25d1f-116">Description</span><span class="sxs-lookup"><span data-stu-id="25d1f-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="25d1f-117">주소</span><span class="sxs-lookup"><span data-stu-id="25d1f-117">address</span></span>|<span data-ttu-id="25d1f-118">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="25d1f-118">Required.</span></span> <span data-ttu-id="25d1f-119">엔드포인트의 주소를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="25d1f-119">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="25d1f-120">주소는 절대 URI이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d1f-120">The address must be an absolute URI.</span></span> <span data-ttu-id="25d1f-121">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="25d1f-121">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="25d1f-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="25d1f-122">Child Elements</span></span>  
  
|<span data-ttu-id="25d1f-123">요소</span><span class="sxs-lookup"><span data-stu-id="25d1f-123">Element</span></span>|<span data-ttu-id="25d1f-124">설명</span><span class="sxs-lookup"><span data-stu-id="25d1f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25d1f-125">\<headers></span><span class="sxs-lookup"><span data-stu-id="25d1f-125">\<headers></span></span>](headers-element.md)|<span data-ttu-id="25d1f-126">주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="25d1f-126">A collection of address headers.</span></span>|  
|[<span data-ttu-id="25d1f-127">\<identity></span><span class="sxs-lookup"><span data-stu-id="25d1f-127">\<identity></span></span>](identity.md)|<span data-ttu-id="25d1f-128">한 엔드포인트에서 다른 엔드포인트와 메시지를 교환할 때 상대 엔드포인트를 인증할 수 있도록 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="25d1f-128">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="25d1f-129">부모 요소</span><span class="sxs-lookup"><span data-stu-id="25d1f-129">Parent Elements</span></span>  
  
|<span data-ttu-id="25d1f-130">요소</span><span class="sxs-lookup"><span data-stu-id="25d1f-130">Element</span></span>|<span data-ttu-id="25d1f-131">설명</span><span class="sxs-lookup"><span data-stu-id="25d1f-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25d1f-132">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="25d1f-132">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="25d1f-133">페더레이션 보안 시나리오에서 발급된 보안 토큰에 대한 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="25d1f-133">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="25d1f-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="25d1f-134">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="25d1f-135">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="25d1f-135">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="25d1f-136">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="25d1f-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="25d1f-137">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="25d1f-137">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="25d1f-138">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="25d1f-138">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="25d1f-139">바인딩</span><span class="sxs-lookup"><span data-stu-id="25d1f-139">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="25d1f-140">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="25d1f-140">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="25d1f-141">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="25d1f-141">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="25d1f-142">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="25d1f-142">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="25d1f-143">방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="25d1f-143">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="25d1f-144">사용자 지정 바인딩 보안</span><span class="sxs-lookup"><span data-stu-id="25d1f-144">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
