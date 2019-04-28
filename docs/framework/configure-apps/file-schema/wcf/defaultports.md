---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 4d7fdfb1cccb14f03d11864f1939cb578c79880a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704117"
---
# <a name="defaultports"></a><span data-ttu-id="79653-101">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="79653-101">\<defaultPorts></span></span>
<span data-ttu-id="79653-102">클라이언트 응용 프로그램에서 수신하는 기본 통신 엔드포인트를 나열하는 기본 포트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="79653-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="79653-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="79653-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="79653-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="79653-104">\<behaviors></span></span>  
<span data-ttu-id="79653-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="79653-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="79653-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="79653-106">\<behavior></span></span>  
<span data-ttu-id="79653-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="79653-107">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="79653-108">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="79653-108">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79653-109">구문</span><span class="sxs-lookup"><span data-stu-id="79653-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79653-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="79653-110">Attributes and Elements</span></span>  
 <span data-ttu-id="79653-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="79653-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79653-112">특성</span><span class="sxs-lookup"><span data-stu-id="79653-112">Attributes</span></span>  
 <span data-ttu-id="79653-113">없음</span><span class="sxs-lookup"><span data-stu-id="79653-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="79653-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="79653-114">Child Elements</span></span>  
  
|<span data-ttu-id="79653-115">요소</span><span class="sxs-lookup"><span data-stu-id="79653-115">Element</span></span>|<span data-ttu-id="79653-116">설명</span><span class="sxs-lookup"><span data-stu-id="79653-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79653-117">\<추가 >의 \<a d d ></span><span class="sxs-lookup"><span data-stu-id="79653-117">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="79653-118">클라이언트 응용 프로그램에서 수신하는 기본 통신 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="79653-118">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="79653-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="79653-119">Parent Elements</span></span>  
  
|<span data-ttu-id="79653-120">요소</span><span class="sxs-lookup"><span data-stu-id="79653-120">Element</span></span>|<span data-ttu-id="79653-121">설명</span><span class="sxs-lookup"><span data-stu-id="79653-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79653-122">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="79653-122">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="79653-123">기본 포트의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="79653-123">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79653-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="79653-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
