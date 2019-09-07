---
title: <issuedTokenParameters>의 <issuer>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: bdd5ad45984fae7b39defe82c4af75845dfda1b6
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397938"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="d4b94-102">\<issuedTokenParameters >의 \<발급자 ></span><span class="sxs-lookup"><span data-stu-id="d4b94-102">\<issuer> of \<issuedTokenParameters></span></span>
<span data-ttu-id="d4b94-103">보안 토큰을 발급하는 STS(보안 토큰 서비스)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b94-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
<span data-ttu-id="d4b94-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d4b94-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d4b94-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d4b94-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d4b94-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="d4b94-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="d4b94-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="d4b94-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="d4b94-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="d4b94-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="d4b94-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<보안 >** ](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="d4b94-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="d4b94-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedTokenParameters >** ](issuedtokenparameters.md)</span><span class="sxs-lookup"><span data-stu-id="d4b94-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span></span>\
<span data-ttu-id="d4b94-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<발급자 >**</span><span class="sxs-lookup"><span data-stu-id="d4b94-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4b94-112">구문</span><span class="sxs-lookup"><span data-stu-id="d4b94-112">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4b94-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d4b94-113">Attributes and Elements</span></span>  
 <span data-ttu-id="d4b94-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b94-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4b94-115">특성</span><span class="sxs-lookup"><span data-stu-id="d4b94-115">Attributes</span></span>  
  
|<span data-ttu-id="d4b94-116">특성</span><span class="sxs-lookup"><span data-stu-id="d4b94-116">Attribute</span></span>|<span data-ttu-id="d4b94-117">Description</span><span class="sxs-lookup"><span data-stu-id="d4b94-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d4b94-118">주소</span><span class="sxs-lookup"><span data-stu-id="d4b94-118">address</span></span>|<span data-ttu-id="d4b94-119">필수 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d4b94-119">Required string.</span></span> <span data-ttu-id="d4b94-120">STS의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="d4b94-120">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d4b94-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d4b94-121">Child Elements</span></span>  
  
|<span data-ttu-id="d4b94-122">요소</span><span class="sxs-lookup"><span data-stu-id="d4b94-122">Element</span></span>|<span data-ttu-id="d4b94-123">Description</span><span class="sxs-lookup"><span data-stu-id="d4b94-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4b94-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="d4b94-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="d4b94-125">작성기에서 만들 수 있는 엔드포인트의 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d4b94-125">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="d4b94-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="d4b94-126">\<identity></span></span>](identity.md)|<span data-ttu-id="d4b94-127">발급된 토큰을 사용하는 경우 클라이언트가 서버를 인증할 수 있도록 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b94-127">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d4b94-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d4b94-128">Parent Elements</span></span>  
  
|<span data-ttu-id="d4b94-129">요소</span><span class="sxs-lookup"><span data-stu-id="d4b94-129">Element</span></span>|<span data-ttu-id="d4b94-130">설명</span><span class="sxs-lookup"><span data-stu-id="d4b94-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4b94-131">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="d4b94-131">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="d4b94-132">현재 발급된 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b94-132">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4b94-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="d4b94-133">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="d4b94-134">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="d4b94-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d4b94-135">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="d4b94-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d4b94-136">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="d4b94-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="d4b94-137">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="d4b94-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d4b94-138">바인딩</span><span class="sxs-lookup"><span data-stu-id="d4b94-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d4b94-139">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="d4b94-139">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d4b94-140">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="d4b94-140">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="d4b94-141">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d4b94-141">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="d4b94-142">방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="d4b94-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="d4b94-143">사용자 지정 바인딩 보안</span><span class="sxs-lookup"><span data-stu-id="d4b94-143">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
