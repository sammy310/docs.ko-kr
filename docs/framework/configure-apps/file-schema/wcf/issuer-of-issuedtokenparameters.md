---
title: <issuedTokenParameters>의 <issuer>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: bdd5ad45984fae7b39defe82c4af75845dfda1b6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397938"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="e2559-102">\<issuedTokenParameters>의 \<issuer></span><span class="sxs-lookup"><span data-stu-id="e2559-102">\<issuer> of \<issuedTokenParameters></span></span>
<span data-ttu-id="e2559-103">보안 토큰을 발급하는 STS(보안 토큰 서비스)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2559-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**  
  
## <a name="syntax"></a><span data-ttu-id="e2559-104">구문</span><span class="sxs-lookup"><span data-stu-id="e2559-104">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2559-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e2559-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e2559-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e2559-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2559-107">특성</span><span class="sxs-lookup"><span data-stu-id="e2559-107">Attributes</span></span>  
  
|<span data-ttu-id="e2559-108">attribute</span><span class="sxs-lookup"><span data-stu-id="e2559-108">Attribute</span></span>|<span data-ttu-id="e2559-109">Description</span><span class="sxs-lookup"><span data-stu-id="e2559-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e2559-110">address</span><span class="sxs-lookup"><span data-stu-id="e2559-110">address</span></span>|<span data-ttu-id="e2559-111">필수 문자열</span><span class="sxs-lookup"><span data-stu-id="e2559-111">Required string.</span></span> <span data-ttu-id="e2559-112">STS의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="e2559-112">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2559-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e2559-113">Child Elements</span></span>  
  
|<span data-ttu-id="e2559-114">요소</span><span class="sxs-lookup"><span data-stu-id="e2559-114">Element</span></span>|<span data-ttu-id="e2559-115">Description</span><span class="sxs-lookup"><span data-stu-id="e2559-115">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="e2559-116">작성기에서 만들 수 있는 엔드포인트의 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="e2559-116">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="e2559-117">발급된 토큰을 사용하는 경우 클라이언트가 서버를 인증할 수 있도록 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2559-117">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e2559-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e2559-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e2559-119">요소</span><span class="sxs-lookup"><span data-stu-id="e2559-119">Element</span></span>|<span data-ttu-id="e2559-120">Description</span><span class="sxs-lookup"><span data-stu-id="e2559-120">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="e2559-121">현재 발급된 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2559-121">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2559-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2559-122">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e2559-123">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="e2559-123">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="e2559-124">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="e2559-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="e2559-125">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="e2559-125">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="e2559-126">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="e2559-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="e2559-127">바인딩</span><span class="sxs-lookup"><span data-stu-id="e2559-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e2559-128">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="e2559-128">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e2559-129">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="e2559-129">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="e2559-130">방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="e2559-130">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="e2559-131">Custom Binding Security</span><span class="sxs-lookup"><span data-stu-id="e2559-131">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
