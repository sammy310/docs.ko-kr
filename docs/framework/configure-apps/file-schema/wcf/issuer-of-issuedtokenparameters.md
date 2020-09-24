---
title: <issuedTokenParameters>의 <issuer>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: bfe8163d2d6baba1d6e8053f7f6579673d8b4b21
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157280"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="eba5e-102">\<issuedTokenParameters>의 \<issuer></span><span class="sxs-lookup"><span data-stu-id="eba5e-102">\<issuer> of \<issuedTokenParameters></span></span>

<span data-ttu-id="eba5e-103">보안 토큰을 발급하는 STS(보안 토큰 서비스)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5e-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**  
  
## <a name="syntax"></a><span data-ttu-id="eba5e-104">구문</span><span class="sxs-lookup"><span data-stu-id="eba5e-104">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eba5e-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="eba5e-105">Attributes and Elements</span></span>  

 <span data-ttu-id="eba5e-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5e-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eba5e-107">특성</span><span class="sxs-lookup"><span data-stu-id="eba5e-107">Attributes</span></span>  
  
|<span data-ttu-id="eba5e-108">attribute</span><span class="sxs-lookup"><span data-stu-id="eba5e-108">Attribute</span></span>|<span data-ttu-id="eba5e-109">설명</span><span class="sxs-lookup"><span data-stu-id="eba5e-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eba5e-110">address</span><span class="sxs-lookup"><span data-stu-id="eba5e-110">address</span></span>|<span data-ttu-id="eba5e-111">필수 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="eba5e-111">Required string.</span></span> <span data-ttu-id="eba5e-112">STS의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="eba5e-112">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eba5e-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="eba5e-113">Child Elements</span></span>  
  
|<span data-ttu-id="eba5e-114">요소</span><span class="sxs-lookup"><span data-stu-id="eba5e-114">Element</span></span>|<span data-ttu-id="eba5e-115">설명</span><span class="sxs-lookup"><span data-stu-id="eba5e-115">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="eba5e-116">작성기에서 만들 수 있는 엔드포인트의 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="eba5e-116">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="eba5e-117">발급된 토큰을 사용하는 경우 클라이언트가 서버를 인증할 수 있도록 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5e-117">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eba5e-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="eba5e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="eba5e-119">요소</span><span class="sxs-lookup"><span data-stu-id="eba5e-119">Element</span></span>|<span data-ttu-id="eba5e-120">설명</span><span class="sxs-lookup"><span data-stu-id="eba5e-120">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="eba5e-121">현재 발급된 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eba5e-121">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eba5e-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eba5e-122">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="eba5e-123">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="eba5e-123">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="eba5e-124">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="eba5e-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="eba5e-125">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="eba5e-125">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="eba5e-126">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="eba5e-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="eba5e-127">바인딩하</span><span class="sxs-lookup"><span data-stu-id="eba5e-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="eba5e-128">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="eba5e-128">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="eba5e-129">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="eba5e-129">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="eba5e-130">방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="eba5e-130">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="eba5e-131">Custom Binding Security</span><span class="sxs-lookup"><span data-stu-id="eba5e-131">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
