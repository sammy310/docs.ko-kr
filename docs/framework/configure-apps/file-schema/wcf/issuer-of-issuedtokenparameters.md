---
description: '다음에 대 한 자세한 정보:: <issuer><issuedTokenParameters>'
title: <issuedTokenParameters>의 <issuer>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: 7d67583eda22414750631b6dff40f6e6ea8831e4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725651"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="1eac7-103">\<issuedTokenParameters>의 \<issuer></span><span class="sxs-lookup"><span data-stu-id="1eac7-103">\<issuer> of \<issuedTokenParameters></span></span>

<span data-ttu-id="1eac7-104">보안 토큰을 발급하는 STS(보안 토큰 서비스)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1eac7-104">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**  
  
## <a name="syntax"></a><span data-ttu-id="1eac7-105">구문</span><span class="sxs-lookup"><span data-stu-id="1eac7-105">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1eac7-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1eac7-106">Attributes and Elements</span></span>  

 <span data-ttu-id="1eac7-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1eac7-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1eac7-108">특성</span><span class="sxs-lookup"><span data-stu-id="1eac7-108">Attributes</span></span>  
  
|<span data-ttu-id="1eac7-109">attribute</span><span class="sxs-lookup"><span data-stu-id="1eac7-109">Attribute</span></span>|<span data-ttu-id="1eac7-110">설명</span><span class="sxs-lookup"><span data-stu-id="1eac7-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1eac7-111">address</span><span class="sxs-lookup"><span data-stu-id="1eac7-111">address</span></span>|<span data-ttu-id="1eac7-112">필수 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1eac7-112">Required string.</span></span> <span data-ttu-id="1eac7-113">STS의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="1eac7-113">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1eac7-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1eac7-114">Child Elements</span></span>  
  
|<span data-ttu-id="1eac7-115">요소</span><span class="sxs-lookup"><span data-stu-id="1eac7-115">Element</span></span>|<span data-ttu-id="1eac7-116">설명</span><span class="sxs-lookup"><span data-stu-id="1eac7-116">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="1eac7-117">작성기에서 만들 수 있는 엔드포인트의 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="1eac7-117">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="1eac7-118">발급된 토큰을 사용하는 경우 클라이언트가 서버를 인증할 수 있도록 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1eac7-118">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1eac7-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1eac7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1eac7-120">요소</span><span class="sxs-lookup"><span data-stu-id="1eac7-120">Element</span></span>|<span data-ttu-id="1eac7-121">설명</span><span class="sxs-lookup"><span data-stu-id="1eac7-121">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="1eac7-122">현재 발급된 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1eac7-122">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1eac7-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1eac7-123">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="1eac7-124">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="1eac7-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="1eac7-125">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="1eac7-125">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="1eac7-126">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="1eac7-126">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="1eac7-127">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="1eac7-127">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="1eac7-128">바인딩</span><span class="sxs-lookup"><span data-stu-id="1eac7-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1eac7-129">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="1eac7-129">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="1eac7-130">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="1eac7-130">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="1eac7-131">방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="1eac7-131">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="1eac7-132">Custom Binding Security</span><span class="sxs-lookup"><span data-stu-id="1eac7-132">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
