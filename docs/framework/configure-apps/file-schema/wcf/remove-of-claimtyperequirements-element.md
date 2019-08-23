---
title: <remove>of <claimTypeRequirements> 요소
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 7238c253bfbc3224c8bbd31265e197dd35e56514
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934234"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="7b045-102">\<\<claimTypeRequirements > 요소의 > 제거</span><span class="sxs-lookup"><span data-stu-id="7b045-102">\<remove> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="7b045-103">페더레이션 자격 증명에서 제거할 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
 <span data-ttu-id="7b045-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7b045-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7b045-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="7b045-105">\<bindings></span></span>  
<span data-ttu-id="7b045-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="7b045-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="7b045-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="7b045-107">\<binding></span></span>  
<span data-ttu-id="7b045-108">\<security></span><span class="sxs-lookup"><span data-stu-id="7b045-108">\<security></span></span>  
<span data-ttu-id="7b045-109">\<message></span><span class="sxs-lookup"><span data-stu-id="7b045-109">\<message></span></span>  
<span data-ttu-id="7b045-110">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="7b045-110">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b045-111">구문</span><span class="sxs-lookup"><span data-stu-id="7b045-111">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b045-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7b045-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7b045-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b045-114">특성</span><span class="sxs-lookup"><span data-stu-id="7b045-114">Attributes</span></span>  
  
|<span data-ttu-id="7b045-115">특성</span><span class="sxs-lookup"><span data-stu-id="7b045-115">Attribute</span></span>|<span data-ttu-id="7b045-116">Description</span><span class="sxs-lookup"><span data-stu-id="7b045-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7b045-117">claimType</span><span class="sxs-lookup"><span data-stu-id="7b045-117">claimType</span></span>|<span data-ttu-id="7b045-118">제거할 클레임의 형식을 정의하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-118">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b045-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7b045-119">Child Elements</span></span>  
 <span data-ttu-id="7b045-120">없음</span><span class="sxs-lookup"><span data-stu-id="7b045-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7b045-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7b045-121">Parent Elements</span></span>  
  
|<span data-ttu-id="7b045-122">요소</span><span class="sxs-lookup"><span data-stu-id="7b045-122">Element</span></span>|<span data-ttu-id="7b045-123">Description</span><span class="sxs-lookup"><span data-stu-id="7b045-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b045-124">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="7b045-124">\<claimTypeRequirements></span></span>](claimtyperequirements-for-message.md)|<span data-ttu-id="7b045-125">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="7b045-126">각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="7b045-127">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="7b045-128">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="7b045-129">이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b045-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b045-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="7b045-130">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
