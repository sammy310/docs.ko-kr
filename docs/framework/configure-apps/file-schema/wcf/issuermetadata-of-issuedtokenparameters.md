---
title: <issuedTokenParameters>의 <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: fcdd66ecd162dff5be86a1d4ab1b196f50dbd445
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400350"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="b1875-102">\<issuedTokenParameters>의 \<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="b1875-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**  
  
## <a name="syntax"></a><span data-ttu-id="b1875-103">구문</span><span class="sxs-lookup"><span data-stu-id="b1875-103">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1875-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b1875-104">Attributes and Elements</span></span>  
 <span data-ttu-id="b1875-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b1875-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1875-106">특성</span><span class="sxs-lookup"><span data-stu-id="b1875-106">Attributes</span></span>  
  
|<span data-ttu-id="b1875-107">attribute</span><span class="sxs-lookup"><span data-stu-id="b1875-107">Attribute</span></span>|<span data-ttu-id="b1875-108">Description</span><span class="sxs-lookup"><span data-stu-id="b1875-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b1875-109">address</span><span class="sxs-lookup"><span data-stu-id="b1875-109">address</span></span>|<span data-ttu-id="b1875-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b1875-110">Required.</span></span> <span data-ttu-id="b1875-111">엔드포인트의 주소를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b1875-111">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="b1875-112">주소는 절대 URI이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1875-112">The address must be an absolute URI.</span></span> <span data-ttu-id="b1875-113">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b1875-113">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b1875-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b1875-114">Child Elements</span></span>  
  
|<span data-ttu-id="b1875-115">요소</span><span class="sxs-lookup"><span data-stu-id="b1875-115">Element</span></span>|<span data-ttu-id="b1875-116">Description</span><span class="sxs-lookup"><span data-stu-id="b1875-116">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="b1875-117">주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b1875-117">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="b1875-118">한 엔드포인트에서 다른 엔드포인트와 메시지를 교환할 때 상대 엔드포인트를 인증할 수 있도록 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b1875-118">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b1875-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b1875-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b1875-120">요소</span><span class="sxs-lookup"><span data-stu-id="b1875-120">Element</span></span>|<span data-ttu-id="b1875-121">Description</span><span class="sxs-lookup"><span data-stu-id="b1875-121">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="b1875-122">페더레이션 보안 시나리오에서 발급된 보안 토큰에 대한 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b1875-122">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1875-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1875-123">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b1875-124">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="b1875-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="b1875-125">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="b1875-125">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="b1875-126">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="b1875-126">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="b1875-127">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="b1875-127">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="b1875-128">바인딩</span><span class="sxs-lookup"><span data-stu-id="b1875-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b1875-129">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="b1875-129">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b1875-130">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="b1875-130">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="b1875-131">방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="b1875-131">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="b1875-132">Custom Binding Security</span><span class="sxs-lookup"><span data-stu-id="b1875-132">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
