---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 969461d0e5bdc9f8c49b7a019a6000af5af77eec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121188"
---
# <a name="userequestheadersformetadataaddress"></a><span data-ttu-id="b1273-101">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="b1273-101">\<useRequestHeadersForMetadataAddress></span></span>
<span data-ttu-id="b1273-102">요청 메시지 헤더에서 메타데이터 주소 정보를 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1273-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="b1273-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b1273-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="b1273-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="b1273-104">\<behaviors></span></span>  
<span data-ttu-id="b1273-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="b1273-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="b1273-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b1273-106">\<behavior></span></span>  
<span data-ttu-id="b1273-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="b1273-107">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1273-108">구문</span><span class="sxs-lookup"><span data-stu-id="b1273-108">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1273-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b1273-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b1273-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b1273-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1273-111">특성</span><span class="sxs-lookup"><span data-stu-id="b1273-111">Attributes</span></span>  
 <span data-ttu-id="b1273-112">없음</span><span class="sxs-lookup"><span data-stu-id="b1273-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b1273-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b1273-113">Child Elements</span></span>  
  
|<span data-ttu-id="b1273-114">요소</span><span class="sxs-lookup"><span data-stu-id="b1273-114">Element</span></span>|<span data-ttu-id="b1273-115">설명</span><span class="sxs-lookup"><span data-stu-id="b1273-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1273-116">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="b1273-116">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="b1273-117">클라이언트 응용 프로그램에서 수신하는 기본 통신 엔드포인트를 나열하는 기본 포트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b1273-117">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b1273-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b1273-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b1273-119">요소</span><span class="sxs-lookup"><span data-stu-id="b1273-119">Element</span></span>|<span data-ttu-id="b1273-120">설명</span><span class="sxs-lookup"><span data-stu-id="b1273-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1273-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b1273-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="b1273-122">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b1273-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1273-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="b1273-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
