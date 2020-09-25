---
title: <issuedTokenParameters>의 <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: 389ac9e96c1462f59bc42b2e20cb511acdefda00
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185667"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="88120-102">\<issuedTokenParameters>의 \<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="88120-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**  
  
## <a name="syntax"></a><span data-ttu-id="88120-103">구문</span><span class="sxs-lookup"><span data-stu-id="88120-103">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88120-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="88120-104">Attributes and Elements</span></span>  

 <span data-ttu-id="88120-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="88120-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88120-106">특성</span><span class="sxs-lookup"><span data-stu-id="88120-106">Attributes</span></span>  
  
|<span data-ttu-id="88120-107">attribute</span><span class="sxs-lookup"><span data-stu-id="88120-107">Attribute</span></span>|<span data-ttu-id="88120-108">설명</span><span class="sxs-lookup"><span data-stu-id="88120-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="88120-109">address</span><span class="sxs-lookup"><span data-stu-id="88120-109">address</span></span>|<span data-ttu-id="88120-110">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="88120-110">Required.</span></span> <span data-ttu-id="88120-111">엔드포인트의 주소를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="88120-111">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="88120-112">주소는 절대 URI이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88120-112">The address must be an absolute URI.</span></span> <span data-ttu-id="88120-113">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="88120-113">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88120-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="88120-114">Child Elements</span></span>  
  
|<span data-ttu-id="88120-115">요소</span><span class="sxs-lookup"><span data-stu-id="88120-115">Element</span></span>|<span data-ttu-id="88120-116">설명</span><span class="sxs-lookup"><span data-stu-id="88120-116">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="88120-117">주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="88120-117">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="88120-118">한 엔드포인트에서 다른 엔드포인트와 메시지를 교환할 때 상대 엔드포인트를 인증할 수 있도록 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="88120-118">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="88120-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="88120-119">Parent Elements</span></span>  
  
|<span data-ttu-id="88120-120">요소</span><span class="sxs-lookup"><span data-stu-id="88120-120">Element</span></span>|<span data-ttu-id="88120-121">설명</span><span class="sxs-lookup"><span data-stu-id="88120-121">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="88120-122">페더레이션 보안 시나리오에서 발급된 보안 토큰에 대한 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="88120-122">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="88120-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88120-123">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="88120-124">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="88120-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="88120-125">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="88120-125">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="88120-126">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="88120-126">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="88120-127">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="88120-127">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="88120-128">바인딩하</span><span class="sxs-lookup"><span data-stu-id="88120-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="88120-129">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="88120-129">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="88120-130">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="88120-130">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="88120-131">방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="88120-131">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="88120-132">Custom Binding Security</span><span class="sxs-lookup"><span data-stu-id="88120-132">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
