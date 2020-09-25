---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 72778ce0070d853f8b081a4889ead9524bafd0e8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181351"
---
# \<policyImporter>

<span data-ttu-id="a1b92-101">바인딩에 대한 사용자 지정 정책 어설션의 가져오기를 제어하는 정책 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b92-101">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<policyImporters>**](policyimporters.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<policyImporter>**  
  
## <a name="syntax"></a><span data-ttu-id="a1b92-102">구문</span><span class="sxs-lookup"><span data-stu-id="a1b92-102">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1b92-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a1b92-103">Attributes and Elements</span></span>  

 <span data-ttu-id="a1b92-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b92-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1b92-105">특성</span><span class="sxs-lookup"><span data-stu-id="a1b92-105">Attributes</span></span>  
  
|<span data-ttu-id="a1b92-106">attribute</span><span class="sxs-lookup"><span data-stu-id="a1b92-106">Attribute</span></span>|<span data-ttu-id="a1b92-107">설명</span><span class="sxs-lookup"><span data-stu-id="a1b92-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="a1b92-108">이 요소의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b92-108">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1b92-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a1b92-109">Child Elements</span></span>  

 <span data-ttu-id="a1b92-110">없음</span><span class="sxs-lookup"><span data-stu-id="a1b92-110">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1b92-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a1b92-111">Parent Elements</span></span>  
  
|<span data-ttu-id="a1b92-112">요소</span><span class="sxs-lookup"><span data-stu-id="a1b92-112">Element</span></span>|<span data-ttu-id="a1b92-113">설명</span><span class="sxs-lookup"><span data-stu-id="a1b92-113">Description</span></span>|  
|-------------|-----------------|  
|[\<policyImporters>](policyimporters.md)|<span data-ttu-id="a1b92-114">바인딩에 대한 사용자 지정 정책 어설션의 가져오기를 제어하는 모든 정책 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b92-114">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1b92-115">설명</span><span class="sxs-lookup"><span data-stu-id="a1b92-115">Remarks</span></span>  

 <span data-ttu-id="a1b92-116">정책 가져오기는, 바인딩 기능에 대한 사용자 지정 정책 어설션을 검색하거나 어설션에서 요구하는 기능을 구현하는 사용자 지정 바인딩 요소를 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b92-116">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1b92-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1b92-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="a1b92-118">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="a1b92-118">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="a1b92-119">클라이언트</span><span class="sxs-lookup"><span data-stu-id="a1b92-119">Clients</span></span>](../../../wcf/feature-details/clients.md)
