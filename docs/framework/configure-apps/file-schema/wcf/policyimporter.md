---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 273bd0d5e68a661c639b82264b440b83d8127427
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933786"
---
# <a name="policyimporter"></a><span data-ttu-id="6783c-101">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="6783c-101">\<policyImporter></span></span>
<span data-ttu-id="6783c-102">바인딩에 대한 사용자 지정 정책 어설션의 가져오기를 제어하는 정책 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6783c-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="6783c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6783c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="6783c-104">\<client></span><span class="sxs-lookup"><span data-stu-id="6783c-104">\<client></span></span>  
<span data-ttu-id="6783c-105">\<metadata></span><span class="sxs-lookup"><span data-stu-id="6783c-105">\<metadata></span></span>  
<span data-ttu-id="6783c-106">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="6783c-106">\<policyImporters></span></span>  
<span data-ttu-id="6783c-107">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="6783c-107">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6783c-108">구문</span><span class="sxs-lookup"><span data-stu-id="6783c-108">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6783c-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6783c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6783c-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6783c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6783c-111">특성</span><span class="sxs-lookup"><span data-stu-id="6783c-111">Attributes</span></span>  
  
|<span data-ttu-id="6783c-112">특성</span><span class="sxs-lookup"><span data-stu-id="6783c-112">Attribute</span></span>|<span data-ttu-id="6783c-113">설명</span><span class="sxs-lookup"><span data-stu-id="6783c-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="6783c-114">이 요소의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6783c-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6783c-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6783c-115">Child Elements</span></span>  
 <span data-ttu-id="6783c-116">없음</span><span class="sxs-lookup"><span data-stu-id="6783c-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6783c-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6783c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6783c-118">요소</span><span class="sxs-lookup"><span data-stu-id="6783c-118">Element</span></span>|<span data-ttu-id="6783c-119">Description</span><span class="sxs-lookup"><span data-stu-id="6783c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6783c-120">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="6783c-120">\<policyImporters></span></span>](policyimporters.md)|<span data-ttu-id="6783c-121">바인딩에 대한 사용자 지정 정책 어설션의 가져오기를 제어하는 모든 정책 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6783c-121">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6783c-122">설명</span><span class="sxs-lookup"><span data-stu-id="6783c-122">Remarks</span></span>  
 <span data-ttu-id="6783c-123">정책 가져오기는, 바인딩 기능에 대한 사용자 지정 정책 어설션을 검색하거나 어설션에서 요구하는 기능을 구현하는 사용자 지정 바인딩 요소를 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6783c-123">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6783c-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="6783c-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="6783c-125">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="6783c-125">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="6783c-126">클라이언트</span><span class="sxs-lookup"><span data-stu-id="6783c-126">Clients</span></span>](../../../wcf/feature-details/clients.md)
