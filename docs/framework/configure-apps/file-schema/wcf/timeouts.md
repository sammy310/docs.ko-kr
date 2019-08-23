---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b159488efa2a80a9dea625e4c6dfe2f215dfc457
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939182"
---
# <a name="timeouts"></a><span data-ttu-id="ca0db-101">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="ca0db-101">\<timeOuts></span></span>
<span data-ttu-id="ca0db-102">서비스 호스트가 열리거나 닫히는 데 허용되는 시간 간격을 지정하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ca0db-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="ca0db-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ca0db-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="ca0db-104">\<client></span><span class="sxs-lookup"><span data-stu-id="ca0db-104">\<client></span></span>  
<span data-ttu-id="ca0db-105">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="ca0db-105">\<endpoint></span></span>  
<span data-ttu-id="ca0db-106">\<host></span><span class="sxs-lookup"><span data-stu-id="ca0db-106">\<host></span></span>  
<span data-ttu-id="ca0db-107">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="ca0db-107">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca0db-108">구문</span><span class="sxs-lookup"><span data-stu-id="ca0db-108">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca0db-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ca0db-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ca0db-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ca0db-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca0db-111">특성</span><span class="sxs-lookup"><span data-stu-id="ca0db-111">Attributes</span></span>  
  
|<span data-ttu-id="ca0db-112">특성</span><span class="sxs-lookup"><span data-stu-id="ca0db-112">Attribute</span></span>|<span data-ttu-id="ca0db-113">설명</span><span class="sxs-lookup"><span data-stu-id="ca0db-113">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="ca0db-114">서비스 호스트를 닫는 데 허용되는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ca0db-114">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="ca0db-115">서비스 호스트를 여는 데 허용되는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ca0db-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca0db-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ca0db-116">Child Elements</span></span>  
 <span data-ttu-id="ca0db-117">없음</span><span class="sxs-lookup"><span data-stu-id="ca0db-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca0db-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ca0db-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ca0db-119">요소</span><span class="sxs-lookup"><span data-stu-id="ca0db-119">Element</span></span>|<span data-ttu-id="ca0db-120">Description</span><span class="sxs-lookup"><span data-stu-id="ca0db-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca0db-121">\<host></span><span class="sxs-lookup"><span data-stu-id="ca0db-121">\<host></span></span>](host.md)|<span data-ttu-id="ca0db-122">서비스 호스트의 설정을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ca0db-122">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca0db-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="ca0db-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="ca0db-124">호스팅</span><span class="sxs-lookup"><span data-stu-id="ca0db-124">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
