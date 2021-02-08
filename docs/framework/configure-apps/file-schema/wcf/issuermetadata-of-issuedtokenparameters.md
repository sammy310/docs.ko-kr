---
description: '다음에 대 한 자세한 정보:: <issuerMetadata><issuedTokenParameters>'
title: <issuedTokenParameters>의 <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: 6b0b5064254caf1c6bcf72c2e6d3449402853b98
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802244"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="28180-103">\<issuedTokenParameters>의 \<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="28180-103">\<issuerMetadata> of \<issuedTokenParameters></span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**  
  
## <a name="syntax"></a><span data-ttu-id="28180-104">구문</span><span class="sxs-lookup"><span data-stu-id="28180-104">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28180-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="28180-105">Attributes and Elements</span></span>  

 <span data-ttu-id="28180-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28180-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28180-107">특성</span><span class="sxs-lookup"><span data-stu-id="28180-107">Attributes</span></span>  
  
|<span data-ttu-id="28180-108">attribute</span><span class="sxs-lookup"><span data-stu-id="28180-108">Attribute</span></span>|<span data-ttu-id="28180-109">설명</span><span class="sxs-lookup"><span data-stu-id="28180-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="28180-110">address</span><span class="sxs-lookup"><span data-stu-id="28180-110">address</span></span>|<span data-ttu-id="28180-111">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="28180-111">Required.</span></span> <span data-ttu-id="28180-112">엔드포인트의 주소를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="28180-112">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="28180-113">주소는 절대 URI이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28180-113">The address must be an absolute URI.</span></span> <span data-ttu-id="28180-114">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="28180-114">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28180-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="28180-115">Child Elements</span></span>  
  
|<span data-ttu-id="28180-116">요소</span><span class="sxs-lookup"><span data-stu-id="28180-116">Element</span></span>|<span data-ttu-id="28180-117">설명</span><span class="sxs-lookup"><span data-stu-id="28180-117">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="28180-118">주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="28180-118">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="28180-119">한 엔드포인트에서 다른 엔드포인트와 메시지를 교환할 때 상대 엔드포인트를 인증할 수 있도록 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="28180-119">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="28180-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="28180-120">Parent Elements</span></span>  
  
|<span data-ttu-id="28180-121">요소</span><span class="sxs-lookup"><span data-stu-id="28180-121">Element</span></span>|<span data-ttu-id="28180-122">설명</span><span class="sxs-lookup"><span data-stu-id="28180-122">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="28180-123">페더레이션 보안 시나리오에서 발급된 보안 토큰에 대한 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="28180-123">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28180-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28180-124">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="28180-125">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="28180-125">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="28180-126">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="28180-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="28180-127">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="28180-127">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="28180-128">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="28180-128">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="28180-129">바인딩</span><span class="sxs-lookup"><span data-stu-id="28180-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="28180-130">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="28180-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="28180-131">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="28180-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="28180-132">방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="28180-132">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="28180-133">Custom Binding Security</span><span class="sxs-lookup"><span data-stu-id="28180-133">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
