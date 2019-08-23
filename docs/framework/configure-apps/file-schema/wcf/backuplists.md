---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: b65cc4d04b5304e93b70509c9db3bc2248accb7f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926431"
---
# <a name="backuplists"></a><span data-ttu-id="db4f8-101">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="db4f8-101">\<backupLists></span></span>
<span data-ttu-id="db4f8-102">오류 처리에서 사용되는 백업 서비스 집합을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="db4f8-102">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="db4f8-103">각 자식 요소는 라우팅 서비스에서 기본 끝점에 연결할 수 없는 경우 사용할 끝점 집합을 열거 하는 백업 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="db4f8-103">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="db4f8-104">목록의 첫 번째 엔드포인트가 다운되는 경우 라우팅 서비스는 자동으로 목록의 다음 엔드포인트로 장애 조치(failover)됩니다.</span><span class="sxs-lookup"><span data-stu-id="db4f8-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="db4f8-105">따라서 복잡한 패턴을 처리하는 방법이나 모든 서비스가 배포되는 위치를 클라이언트 애플리케이션에 지정할 필요 없이 애플리케이션의 안정성을 빠르게 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db4f8-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="db4f8-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="db4f8-106">\<system.serviceModel></span></span>  
<span data-ttu-id="db4f8-107">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="db4f8-107">\<routing></span></span>  
<span data-ttu-id="db4f8-108">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="db4f8-108">\<backupLists></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db4f8-109">구문</span><span class="sxs-lookup"><span data-stu-id="db4f8-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db4f8-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="db4f8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="db4f8-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="db4f8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db4f8-112">특성</span><span class="sxs-lookup"><span data-stu-id="db4f8-112">Attributes</span></span>  
 <span data-ttu-id="db4f8-113">없음</span><span class="sxs-lookup"><span data-stu-id="db4f8-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="db4f8-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="db4f8-114">Child Elements</span></span>  
  
|<span data-ttu-id="db4f8-115">요소</span><span class="sxs-lookup"><span data-stu-id="db4f8-115">Element</span></span>|<span data-ttu-id="db4f8-116">설명</span><span class="sxs-lookup"><span data-stu-id="db4f8-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db4f8-117">\<filter></span><span class="sxs-lookup"><span data-stu-id="db4f8-117">\<filter></span></span>](filter.md)|<span data-ttu-id="db4f8-118">기본 끝점에 연결할 수 없는 경우 라우팅 서비스에서 사용할 끝점 목록을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="db4f8-118">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="db4f8-119">을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="db4f8-119">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="db4f8-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="db4f8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="db4f8-121">요소</span><span class="sxs-lookup"><span data-stu-id="db4f8-121">Element</span></span>|<span data-ttu-id="db4f8-122">Description</span><span class="sxs-lookup"><span data-stu-id="db4f8-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db4f8-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="db4f8-123">\<routing></span></span>](routing.md)|<span data-ttu-id="db4f8-124">들어오는 메시지를 평가할 때 사용 되는 WCF<xref:System.ServiceModel.Dispatcher.MessageFilter> (Windows Communication Foundation 형식 및 대상 끝점을 정의 하는 라우팅 테이블을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다. 필터가 일치 하는 경우에 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="db4f8-124">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="db4f8-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="db4f8-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
