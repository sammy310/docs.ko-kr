---
title: <remove>of <claimTypeRequirements> 요소
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 84f4208d3f4581cf7e8c4455bf3f5d78f7e13b9f
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399992"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="dfcd9-102">\<\<claimTypeRequirements > 요소의 > 제거</span><span class="sxs-lookup"><span data-stu-id="dfcd9-102">\<remove> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="dfcd9-103">페더레이션 자격 증명에서 제거할 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcd9-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
<span data-ttu-id="dfcd9-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dfcd9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dfcd9-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="dfcd9-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="dfcd9-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="dfcd9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="dfcd9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="dfcd9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="dfcd9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="dfcd9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="dfcd9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<보안 >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="dfcd9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="dfcd9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<메시지 >** ](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="dfcd9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="dfcd9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<claimTypeRequirements >** ](claimtyperequirements-for-message.md)</span><span class="sxs-lookup"><span data-stu-id="dfcd9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)</span></span>\
<span data-ttu-id="dfcd9-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 제거**</span><span class="sxs-lookup"><span data-stu-id="dfcd9-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfcd9-113">구문</span><span class="sxs-lookup"><span data-stu-id="dfcd9-113">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dfcd9-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dfcd9-114">Attributes and Elements</span></span>  
 <span data-ttu-id="dfcd9-115">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcd9-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dfcd9-116">특성</span><span class="sxs-lookup"><span data-stu-id="dfcd9-116">Attributes</span></span>  
  
|<span data-ttu-id="dfcd9-117">특성</span><span class="sxs-lookup"><span data-stu-id="dfcd9-117">Attribute</span></span>|<span data-ttu-id="dfcd9-118">Description</span><span class="sxs-lookup"><span data-stu-id="dfcd9-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dfcd9-119">claimType</span><span class="sxs-lookup"><span data-stu-id="dfcd9-119">claimType</span></span>|<span data-ttu-id="dfcd9-120">제거할 클레임의 형식을 정의하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="dfcd9-120">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dfcd9-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dfcd9-121">Child Elements</span></span>  
 <span data-ttu-id="dfcd9-122">없음</span><span class="sxs-lookup"><span data-stu-id="dfcd9-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dfcd9-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dfcd9-123">Parent Elements</span></span>  
  
|<span data-ttu-id="dfcd9-124">요소</span><span class="sxs-lookup"><span data-stu-id="dfcd9-124">Element</span></span>|<span data-ttu-id="dfcd9-125">Description</span><span class="sxs-lookup"><span data-stu-id="dfcd9-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dfcd9-126">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="dfcd9-126">\<claimTypeRequirements></span></span>](claimtyperequirements-for-message.md)|<span data-ttu-id="dfcd9-127">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcd9-127">Specifies a collection of required claim types.</span></span> <span data-ttu-id="dfcd9-128">각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="dfcd9-128">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="dfcd9-129">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcd9-129">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="dfcd9-130">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcd9-130">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="dfcd9-131">이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcd9-131">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dfcd9-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="dfcd9-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
