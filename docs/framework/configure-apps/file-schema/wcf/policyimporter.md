---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 81f38d2a163163ca7255ca546bbddbbb58fa3a1b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783188"
---
# <a name="policyimporter"></a><span data-ttu-id="05649-101">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="05649-101">\<policyImporter></span></span>
<span data-ttu-id="05649-102">바인딩에 대한 사용자 지정 정책 어설션의 가져오기를 제어하는 정책 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="05649-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="05649-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="05649-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="05649-104">\<client></span><span class="sxs-lookup"><span data-stu-id="05649-104">\<client></span></span>  
<span data-ttu-id="05649-105">\<metadata></span><span class="sxs-lookup"><span data-stu-id="05649-105">\<metadata></span></span>  
<span data-ttu-id="05649-106">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="05649-106">\<policyImporters></span></span>  
<span data-ttu-id="05649-107">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="05649-107">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05649-108">구문</span><span class="sxs-lookup"><span data-stu-id="05649-108">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05649-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="05649-109">Attributes and Elements</span></span>  
 <span data-ttu-id="05649-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="05649-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05649-111">특성</span><span class="sxs-lookup"><span data-stu-id="05649-111">Attributes</span></span>  
  
|<span data-ttu-id="05649-112">특성</span><span class="sxs-lookup"><span data-stu-id="05649-112">Attribute</span></span>|<span data-ttu-id="05649-113">설명</span><span class="sxs-lookup"><span data-stu-id="05649-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="05649-114">이 요소의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="05649-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="05649-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="05649-115">Child Elements</span></span>  
 <span data-ttu-id="05649-116">없음</span><span class="sxs-lookup"><span data-stu-id="05649-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="05649-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="05649-117">Parent Elements</span></span>  
  
|<span data-ttu-id="05649-118">요소</span><span class="sxs-lookup"><span data-stu-id="05649-118">Element</span></span>|<span data-ttu-id="05649-119">설명</span><span class="sxs-lookup"><span data-stu-id="05649-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05649-120">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="05649-120">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="05649-121">바인딩에 대한 사용자 지정 정책 어설션의 가져오기를 제어하는 모든 정책 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="05649-121">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05649-122">설명</span><span class="sxs-lookup"><span data-stu-id="05649-122">Remarks</span></span>  
 <span data-ttu-id="05649-123">정책 가져오기는, 바인딩 기능에 대한 사용자 지정 정책 어설션을 검색하거나 어설션에서 요구하는 기능을 구현하는 사용자 지정 바인딩 요소를 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="05649-123">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05649-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="05649-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="05649-125">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="05649-125">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="05649-126">클라이언트</span><span class="sxs-lookup"><span data-stu-id="05649-126">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
