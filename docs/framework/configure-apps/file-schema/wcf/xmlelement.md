---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 841331f233bb8c42c25c88ad8e9b4fb1a86faa76
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398993"
---
# <a name="xmlelement"></a><span data-ttu-id="2e686-101">\<xmlElement></span><span class="sxs-lookup"><span data-stu-id="2e686-101">\<xmlElement></span></span>
<span data-ttu-id="2e686-102">토큰을 요청할 때 메시지 본문에서 보안 토큰 서비스로 보낼 XML 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2e686-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
<span data-ttu-id="2e686-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2e686-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2e686-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2e686-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2e686-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="2e686-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="2e686-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2e686-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="2e686-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="2e686-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="2e686-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<보안 >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2e686-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="2e686-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<메시지 >** ](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2e686-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="2e686-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<tokenRequestParameters >** ](tokenrequestparameters.md)</span><span class="sxs-lookup"><span data-stu-id="2e686-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tokenRequestParameters>**](tokenrequestparameters.md)</span></span>\
<span data-ttu-id="2e686-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<xmlElement >**</span><span class="sxs-lookup"><span data-stu-id="2e686-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<xmlElement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e686-112">구문</span><span class="sxs-lookup"><span data-stu-id="2e686-112">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e686-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2e686-113">Attributes and Elements</span></span>  
 <span data-ttu-id="2e686-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2e686-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e686-115">특성</span><span class="sxs-lookup"><span data-stu-id="2e686-115">Attributes</span></span>  
  
|<span data-ttu-id="2e686-116">특성</span><span class="sxs-lookup"><span data-stu-id="2e686-116">Attribute</span></span>|<span data-ttu-id="2e686-117">Description</span><span class="sxs-lookup"><span data-stu-id="2e686-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2e686-118">xmlElement</span><span class="sxs-lookup"><span data-stu-id="2e686-118">xmlElement</span></span>|<span data-ttu-id="2e686-119">토큰을 요청할 때 메시지 본문에서 보안 토큰 서비스로 보낼 XML 요소를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2e686-119">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e686-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2e686-120">Child Elements</span></span>  
 <span data-ttu-id="2e686-121">없음</span><span class="sxs-lookup"><span data-stu-id="2e686-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2e686-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2e686-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2e686-123">요소</span><span class="sxs-lookup"><span data-stu-id="2e686-123">Element</span></span>|<span data-ttu-id="2e686-124">Description</span><span class="sxs-lookup"><span data-stu-id="2e686-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e686-125">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="2e686-125">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="2e686-126">토큰 요청 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="2e686-126">A collection of token request parameters.</span></span> <span data-ttu-id="2e686-127">각 매개 변수는 XML 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2e686-127">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2e686-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="2e686-128">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="2e686-129">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="2e686-129">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="2e686-130">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="2e686-130">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="2e686-131">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="2e686-131">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="2e686-132">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="2e686-132">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="2e686-133">바인딩</span><span class="sxs-lookup"><span data-stu-id="2e686-133">Bindings</span></span>](../../../wcf/bindings.md)
