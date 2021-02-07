---
description: 다음에 대해 자세히 알아보세요. <policyImporter>
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 2103c424aef081b72fa822ed207537195b8fdea9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683517"
---
# \<policyImporter>

<span data-ttu-id="0420c-102">바인딩에 대한 사용자 지정 정책 어설션의 가져오기를 제어하는 정책 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0420c-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<policyImporters>**](policyimporters.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<policyImporter>**  
  
## <a name="syntax"></a><span data-ttu-id="0420c-103">구문</span><span class="sxs-lookup"><span data-stu-id="0420c-103">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0420c-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0420c-104">Attributes and Elements</span></span>  

 <span data-ttu-id="0420c-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0420c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0420c-106">특성</span><span class="sxs-lookup"><span data-stu-id="0420c-106">Attributes</span></span>  
  
|<span data-ttu-id="0420c-107">attribute</span><span class="sxs-lookup"><span data-stu-id="0420c-107">Attribute</span></span>|<span data-ttu-id="0420c-108">설명</span><span class="sxs-lookup"><span data-stu-id="0420c-108">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="0420c-109">이 요소의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0420c-109">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0420c-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0420c-110">Child Elements</span></span>  

 <span data-ttu-id="0420c-111">없음</span><span class="sxs-lookup"><span data-stu-id="0420c-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0420c-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0420c-112">Parent Elements</span></span>  
  
|<span data-ttu-id="0420c-113">요소</span><span class="sxs-lookup"><span data-stu-id="0420c-113">Element</span></span>|<span data-ttu-id="0420c-114">설명</span><span class="sxs-lookup"><span data-stu-id="0420c-114">Description</span></span>|  
|-------------|-----------------|  
|[\<policyImporters>](policyimporters.md)|<span data-ttu-id="0420c-115">바인딩에 대한 사용자 지정 정책 어설션의 가져오기를 제어하는 모든 정책 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0420c-115">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0420c-116">설명</span><span class="sxs-lookup"><span data-stu-id="0420c-116">Remarks</span></span>  

 <span data-ttu-id="0420c-117">정책 가져오기는, 바인딩 기능에 대한 사용자 지정 정책 어설션을 검색하거나 어설션에서 요구하는 기능을 구현하는 사용자 지정 바인딩 요소를 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0420c-117">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0420c-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0420c-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="0420c-119">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="0420c-119">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="0420c-120">클라이언트</span><span class="sxs-lookup"><span data-stu-id="0420c-120">Clients</span></span>](../../../wcf/feature-details/clients.md)
