---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 81f38d2a163163ca7255ca546bbddbbb58fa3a1b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094179"
---
# <a name="policyimporter"></a><span data-ttu-id="2c6d7-101">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="2c6d7-101">\<policyImporter></span></span>
<span data-ttu-id="2c6d7-102">바인딩에 대한 사용자 지정 정책 어설션의 가져오기를 제어하는 정책 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="2c6d7-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2c6d7-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="2c6d7-104">\<client></span><span class="sxs-lookup"><span data-stu-id="2c6d7-104">\<client></span></span>  
<span data-ttu-id="2c6d7-105">\<metadata></span><span class="sxs-lookup"><span data-stu-id="2c6d7-105">\<metadata></span></span>  
<span data-ttu-id="2c6d7-106">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="2c6d7-106">\<policyImporters></span></span>  
<span data-ttu-id="2c6d7-107">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="2c6d7-107">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c6d7-108">구문</span><span class="sxs-lookup"><span data-stu-id="2c6d7-108">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c6d7-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2c6d7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2c6d7-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c6d7-111">특성</span><span class="sxs-lookup"><span data-stu-id="2c6d7-111">Attributes</span></span>  
  
|<span data-ttu-id="2c6d7-112">특성</span><span class="sxs-lookup"><span data-stu-id="2c6d7-112">Attribute</span></span>|<span data-ttu-id="2c6d7-113">설명</span><span class="sxs-lookup"><span data-stu-id="2c6d7-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="2c6d7-114">이 요소의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2c6d7-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2c6d7-115">Child Elements</span></span>  
 <span data-ttu-id="2c6d7-116">없음</span><span class="sxs-lookup"><span data-stu-id="2c6d7-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2c6d7-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2c6d7-117">Parent Elements</span></span>  
  
|<span data-ttu-id="2c6d7-118">요소</span><span class="sxs-lookup"><span data-stu-id="2c6d7-118">Element</span></span>|<span data-ttu-id="2c6d7-119">설명</span><span class="sxs-lookup"><span data-stu-id="2c6d7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c6d7-120">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="2c6d7-120">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="2c6d7-121">바인딩에 대한 사용자 지정 정책 어설션의 가져오기를 제어하는 모든 정책 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-121">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c6d7-122">설명</span><span class="sxs-lookup"><span data-stu-id="2c6d7-122">Remarks</span></span>  
 <span data-ttu-id="2c6d7-123">정책 가져오기는, 바인딩 기능에 대한 사용자 지정 정책 어설션을 검색하거나 어설션에서 요구하는 기능을 구현하는 사용자 지정 바인딩 요소를 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-123">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c6d7-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="2c6d7-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="2c6d7-125">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="2c6d7-125">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="2c6d7-126">클라이언트</span><span class="sxs-lookup"><span data-stu-id="2c6d7-126">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
