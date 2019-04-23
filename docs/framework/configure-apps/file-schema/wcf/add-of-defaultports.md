---
title: <defaultPorts>의 <add>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 5200c8893a89488b72c2c71d1a3703bf2aad1235
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136749"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="3be93-102">\<추가 >의 \<a d d ></span><span class="sxs-lookup"><span data-stu-id="3be93-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="3be93-103">클라이언트 응용 프로그램에서 수신하는 기본 통신 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="3be93-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="3be93-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3be93-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3be93-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="3be93-105">\<behaviors></span></span>  
<span data-ttu-id="3be93-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="3be93-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="3be93-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3be93-107">\<behavior></span></span>  
<span data-ttu-id="3be93-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="3be93-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="3be93-109">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="3be93-109">\<defaultPorts></span></span>  
<span data-ttu-id="3be93-110">\<add></span><span class="sxs-lookup"><span data-stu-id="3be93-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3be93-111">구문</span><span class="sxs-lookup"><span data-stu-id="3be93-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3be93-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3be93-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3be93-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3be93-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3be93-114">특성</span><span class="sxs-lookup"><span data-stu-id="3be93-114">Attributes</span></span>  
  
|<span data-ttu-id="3be93-115">특성</span><span class="sxs-lookup"><span data-stu-id="3be93-115">Attribute</span></span>|<span data-ttu-id="3be93-116">설명</span><span class="sxs-lookup"><span data-stu-id="3be93-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3be93-117">포트</span><span class="sxs-lookup"><span data-stu-id="3be93-117">port</span></span>|<span data-ttu-id="3be93-118">기본 통신 포트 번호를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="3be93-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="3be93-119">scheme</span><span class="sxs-lookup"><span data-stu-id="3be93-119">scheme</span></span>|<span data-ttu-id="3be93-120">통신 포트와 연결된 프로토콜 설정 그룹을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3be93-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3be93-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3be93-121">Child Elements</span></span>  
 <span data-ttu-id="3be93-122">없음</span><span class="sxs-lookup"><span data-stu-id="3be93-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3be93-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3be93-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3be93-124">요소</span><span class="sxs-lookup"><span data-stu-id="3be93-124">Element</span></span>|<span data-ttu-id="3be93-125">설명</span><span class="sxs-lookup"><span data-stu-id="3be93-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3be93-126">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="3be93-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="3be93-127">클라이언트 응용 프로그램에서 수신하는 기본 통신 엔드포인트를 나열하는 기본 포트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="3be93-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3be93-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="3be93-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
