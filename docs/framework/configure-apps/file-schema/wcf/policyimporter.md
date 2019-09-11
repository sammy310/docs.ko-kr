---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 4ef5890d52c3f2af42322f023b9a2a23cb583035
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855055"
---
# <a name="policyimporter"></a><span data-ttu-id="c2ba9-101">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="c2ba9-101">\<policyImporter></span></span>
<span data-ttu-id="c2ba9-102">바인딩에 대한 사용자 지정 정책 어설션의 가져오기를 제어하는 정책 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ba9-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
<span data-ttu-id="c2ba9-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c2ba9-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c2ba9-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c2ba9-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c2ba9-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<클라이언트 >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="c2ba9-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="c2ba9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<메타 데이터 >** ](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="c2ba9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)</span></span>\
<span data-ttu-id="c2ba9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<policyImporters >** ](policyimporters.md)</span><span class="sxs-lookup"><span data-stu-id="c2ba9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<policyImporters>**](policyimporters.md)</span></span>  
<span data-ttu-id="c2ba9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<policyImporter >**</span><span class="sxs-lookup"><span data-stu-id="c2ba9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<policyImporter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2ba9-109">구문</span><span class="sxs-lookup"><span data-stu-id="c2ba9-109">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2ba9-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c2ba9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c2ba9-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ba9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2ba9-112">특성</span><span class="sxs-lookup"><span data-stu-id="c2ba9-112">Attributes</span></span>  
  
|<span data-ttu-id="c2ba9-113">특성</span><span class="sxs-lookup"><span data-stu-id="c2ba9-113">Attribute</span></span>|<span data-ttu-id="c2ba9-114">설명</span><span class="sxs-lookup"><span data-stu-id="c2ba9-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="c2ba9-115">이 요소의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c2ba9-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c2ba9-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c2ba9-116">Child Elements</span></span>  
 <span data-ttu-id="c2ba9-117">없음</span><span class="sxs-lookup"><span data-stu-id="c2ba9-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c2ba9-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c2ba9-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c2ba9-119">요소</span><span class="sxs-lookup"><span data-stu-id="c2ba9-119">Element</span></span>|<span data-ttu-id="c2ba9-120">설명</span><span class="sxs-lookup"><span data-stu-id="c2ba9-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c2ba9-121">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="c2ba9-121">\<policyImporters></span></span>](policyimporters.md)|<span data-ttu-id="c2ba9-122">바인딩에 대한 사용자 지정 정책 어설션의 가져오기를 제어하는 모든 정책 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ba9-122">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2ba9-123">설명</span><span class="sxs-lookup"><span data-stu-id="c2ba9-123">Remarks</span></span>  
 <span data-ttu-id="c2ba9-124">정책 가져오기는, 바인딩 기능에 대한 사용자 지정 정책 어설션을 검색하거나 어설션에서 요구하는 기능을 구현하는 사용자 지정 바인딩 요소를 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2ba9-124">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2ba9-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="c2ba9-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="c2ba9-126">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="c2ba9-126">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="c2ba9-127">클라이언트</span><span class="sxs-lookup"><span data-stu-id="c2ba9-127">Clients</span></span>](../../../wcf/feature-details/clients.md)
