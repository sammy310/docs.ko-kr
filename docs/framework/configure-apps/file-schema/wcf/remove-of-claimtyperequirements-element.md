---
title: <remove> <claimTypeRequirements> 요소
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 9ab1162ff5d86b8a9d43dae79ebf9c9321119206
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783099"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="659ad-102">\<제거 >의 \<claimTypeRequirements > 요소</span><span class="sxs-lookup"><span data-stu-id="659ad-102">\<remove> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="659ad-103">페더레이션 자격 증명에서 제거할 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="659ad-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
 <span data-ttu-id="659ad-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="659ad-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="659ad-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="659ad-105">\<bindings></span></span>  
<span data-ttu-id="659ad-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="659ad-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="659ad-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="659ad-107">\<binding></span></span>  
<span data-ttu-id="659ad-108">\<security></span><span class="sxs-lookup"><span data-stu-id="659ad-108">\<security></span></span>  
<span data-ttu-id="659ad-109">\<message></span><span class="sxs-lookup"><span data-stu-id="659ad-109">\<message></span></span>  
<span data-ttu-id="659ad-110">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="659ad-110">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="659ad-111">구문</span><span class="sxs-lookup"><span data-stu-id="659ad-111">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="659ad-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="659ad-112">Attributes and Elements</span></span>  
 <span data-ttu-id="659ad-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="659ad-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="659ad-114">특성</span><span class="sxs-lookup"><span data-stu-id="659ad-114">Attributes</span></span>  
  
|<span data-ttu-id="659ad-115">특성</span><span class="sxs-lookup"><span data-stu-id="659ad-115">Attribute</span></span>|<span data-ttu-id="659ad-116">설명</span><span class="sxs-lookup"><span data-stu-id="659ad-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="659ad-117">claimType</span><span class="sxs-lookup"><span data-stu-id="659ad-117">claimType</span></span>|<span data-ttu-id="659ad-118">제거할 클레임의 형식을 정의하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="659ad-118">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="659ad-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="659ad-119">Child Elements</span></span>  
 <span data-ttu-id="659ad-120">없음</span><span class="sxs-lookup"><span data-stu-id="659ad-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="659ad-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="659ad-121">Parent Elements</span></span>  
  
|<span data-ttu-id="659ad-122">요소</span><span class="sxs-lookup"><span data-stu-id="659ad-122">Element</span></span>|<span data-ttu-id="659ad-123">설명</span><span class="sxs-lookup"><span data-stu-id="659ad-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="659ad-124">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="659ad-124">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="659ad-125">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="659ad-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="659ad-126">각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="659ad-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="659ad-127">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="659ad-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="659ad-128">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="659ad-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="659ad-129">이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="659ad-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="659ad-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="659ad-130">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
