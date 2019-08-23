---
title: <defaultPorts>의 <add>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: d2723dad14a63c4b05fdb70157f7eb21d193d3ab
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926703"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="4dac2-102">\<defaultports의 \<> 추가 ></span><span class="sxs-lookup"><span data-stu-id="4dac2-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="4dac2-103">클라이언트 애플리케이션에서 수신하는 기본 통신 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="4dac2-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="4dac2-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4dac2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4dac2-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="4dac2-105">\<behaviors></span></span>  
<span data-ttu-id="4dac2-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="4dac2-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="4dac2-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4dac2-107">\<behavior></span></span>  
<span data-ttu-id="4dac2-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="4dac2-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="4dac2-109">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="4dac2-109">\<defaultPorts></span></span>  
<span data-ttu-id="4dac2-110">\<add></span><span class="sxs-lookup"><span data-stu-id="4dac2-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dac2-111">구문</span><span class="sxs-lookup"><span data-stu-id="4dac2-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4dac2-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4dac2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4dac2-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4dac2-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4dac2-114">특성</span><span class="sxs-lookup"><span data-stu-id="4dac2-114">Attributes</span></span>  
  
|<span data-ttu-id="4dac2-115">특성</span><span class="sxs-lookup"><span data-stu-id="4dac2-115">Attribute</span></span>|<span data-ttu-id="4dac2-116">설명</span><span class="sxs-lookup"><span data-stu-id="4dac2-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4dac2-117">포트</span><span class="sxs-lookup"><span data-stu-id="4dac2-117">port</span></span>|<span data-ttu-id="4dac2-118">기본 통신 포트 번호를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="4dac2-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="4dac2-119">scheme</span><span class="sxs-lookup"><span data-stu-id="4dac2-119">scheme</span></span>|<span data-ttu-id="4dac2-120">통신 포트와 연결된 프로토콜 설정 그룹을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4dac2-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4dac2-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4dac2-121">Child Elements</span></span>  
 <span data-ttu-id="4dac2-122">없음</span><span class="sxs-lookup"><span data-stu-id="4dac2-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4dac2-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4dac2-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4dac2-124">요소</span><span class="sxs-lookup"><span data-stu-id="4dac2-124">Element</span></span>|<span data-ttu-id="4dac2-125">Description</span><span class="sxs-lookup"><span data-stu-id="4dac2-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4dac2-126">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="4dac2-126">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="4dac2-127">클라이언트 애플리케이션에서 수신하는 기본 통신 엔드포인트를 나열하는 기본 포트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4dac2-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4dac2-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="4dac2-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
