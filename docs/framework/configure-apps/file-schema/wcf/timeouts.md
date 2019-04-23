---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b6ae5faa2dd2ffef9669a0245a75227b0f669cf7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118068"
---
# <a name="timeouts"></a><span data-ttu-id="c1ae0-101">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="c1ae0-101">\<timeOuts></span></span>
<span data-ttu-id="c1ae0-102">서비스 호스트가 열리거나 닫히는 데 허용되는 시간 간격을 지정하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="c1ae0-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c1ae0-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c1ae0-104">\<client></span><span class="sxs-lookup"><span data-stu-id="c1ae0-104">\<client></span></span>  
<span data-ttu-id="c1ae0-105">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="c1ae0-105">\<endpoint></span></span>  
<span data-ttu-id="c1ae0-106">\<host></span><span class="sxs-lookup"><span data-stu-id="c1ae0-106">\<host></span></span>  
<span data-ttu-id="c1ae0-107">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="c1ae0-107">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1ae0-108">구문</span><span class="sxs-lookup"><span data-stu-id="c1ae0-108">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1ae0-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c1ae0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c1ae0-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1ae0-111">특성</span><span class="sxs-lookup"><span data-stu-id="c1ae0-111">Attributes</span></span>  
  
|<span data-ttu-id="c1ae0-112">특성</span><span class="sxs-lookup"><span data-stu-id="c1ae0-112">Attribute</span></span>|<span data-ttu-id="c1ae0-113">설명</span><span class="sxs-lookup"><span data-stu-id="c1ae0-113">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="c1ae0-114">서비스 호스트를 닫는 데 허용되는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-114">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="c1ae0-115">서비스 호스트를 여는 데 허용되는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1ae0-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c1ae0-116">Child Elements</span></span>  
 <span data-ttu-id="c1ae0-117">없음</span><span class="sxs-lookup"><span data-stu-id="c1ae0-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c1ae0-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c1ae0-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c1ae0-119">요소</span><span class="sxs-lookup"><span data-stu-id="c1ae0-119">Element</span></span>|<span data-ttu-id="c1ae0-120">설명</span><span class="sxs-lookup"><span data-stu-id="c1ae0-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1ae0-121">\<host></span><span class="sxs-lookup"><span data-stu-id="c1ae0-121">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="c1ae0-122">서비스 호스트의 설정을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-122">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1ae0-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="c1ae0-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="c1ae0-124">호스팅</span><span class="sxs-lookup"><span data-stu-id="c1ae0-124">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
