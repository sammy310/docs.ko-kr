---
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: d5feab6cb374f98e683cf15f797de4f478e23131
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919918"
---
# <a name="backuplist"></a><span data-ttu-id="bec5b-101">\<backupList></span><span class="sxs-lookup"><span data-stu-id="bec5b-101">\<backupList></span></span>
<span data-ttu-id="bec5b-102">기본 끝점에 연결할 수 없는 경우 라우팅 서비스에서 사용할 끝점 집합을 열거 하는 백업 목록을 정의 하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bec5b-102">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="bec5b-103">목록의 첫 번째 엔드포인트가 다운되는 경우 라우팅 서비스는 자동으로 목록의 다음 엔드포인트로 장애 조치(failover)됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec5b-103">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="bec5b-104">따라서 복잡한 패턴을 처리하는 방법이나 모든 서비스가 배포되는 위치를 클라이언트 애플리케이션에 지정할 필요 없이 애플리케이션의 안정성을 빠르게 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec5b-104">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="bec5b-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="bec5b-105">\<system.serviceModel></span></span>  
<span data-ttu-id="bec5b-106">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="bec5b-106">\<routing></span></span>  
<span data-ttu-id="bec5b-107">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="bec5b-107">\<backupLists></span></span>  
<span data-ttu-id="bec5b-108">\<backupList></span><span class="sxs-lookup"><span data-stu-id="bec5b-108">\<backupList></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bec5b-109">구문</span><span class="sxs-lookup"><span data-stu-id="bec5b-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bec5b-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bec5b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bec5b-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bec5b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bec5b-112">특성</span><span class="sxs-lookup"><span data-stu-id="bec5b-112">Attributes</span></span>  
  
|<span data-ttu-id="bec5b-113">특성</span><span class="sxs-lookup"><span data-stu-id="bec5b-113">Attribute</span></span>|<span data-ttu-id="bec5b-114">설명</span><span class="sxs-lookup"><span data-stu-id="bec5b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bec5b-115">name</span><span class="sxs-lookup"><span data-stu-id="bec5b-115">name</span></span>|<span data-ttu-id="bec5b-116">이 엔드포인트 목록을 식별하는 데 사용되는 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="bec5b-116">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bec5b-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bec5b-117">Child Elements</span></span>  
  
|<span data-ttu-id="bec5b-118">요소</span><span class="sxs-lookup"><span data-stu-id="bec5b-118">Element</span></span>|<span data-ttu-id="bec5b-119">설명</span><span class="sxs-lookup"><span data-stu-id="bec5b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bec5b-120">\<filter></span><span class="sxs-lookup"><span data-stu-id="bec5b-120">\<filter></span></span>](filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="bec5b-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bec5b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="bec5b-122">요소</span><span class="sxs-lookup"><span data-stu-id="bec5b-122">Element</span></span>|<span data-ttu-id="bec5b-123">Description</span><span class="sxs-lookup"><span data-stu-id="bec5b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bec5b-124">\<routing></span><span class="sxs-lookup"><span data-stu-id="bec5b-124">\<routing></span></span>](routing.md)|<span data-ttu-id="bec5b-125">백업 엔드포인트의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="bec5b-125">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bec5b-126">설명</span><span class="sxs-lookup"><span data-stu-id="bec5b-126">Remarks</span></span>  
 <span data-ttu-id="bec5b-127">이 섹션에는 기본 엔드포인트로 메시지를 보낼 때 통신 예외가 발생하면 이 메시지를 전송할 엔드포인트의 정렬된 컬렉션이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec5b-127">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="bec5b-128">`endpointName` [ \<추가 >](add-of-entries.md) 의 특성에 나열 된 기본 끝점으로의 보내기가 통신 예외와 함께 실패 하는 경우 라우팅 서비스는이 구성 섹션에 있는 첫 번째 끝점으로 메시지를 보내려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec5b-128">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="bec5b-129">이것도 통신 예외가 발생하여 실패하는 경우 라우팅 서비스는 보내기가 성공할 때까지, 통신 예외가 아닌 다른 원인으로 보내기가 실패할 때까지 또는 컬렉션의 모든 엔드포인트에 대한 보내기가 실패할 때까지 이 섹션에 포함된 다음 엔드포인트로 메시지를 보내려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="bec5b-129">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="bec5b-130">다음 예제에서는 "Destination" 이라는 기본 끝점으로 송신 통신 예외가 반환 하는 경우 서비스를 "alternateservicequeue"로 메시지를 보낼 시도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec5b-130">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="bec5b-131">이 시도에 대해서도 통신 예외가 반환되면 라우팅 서비스는 컬렉션의 다음 엔드포인트로 메시지를 보내려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="bec5b-131">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
```xml  
<filterTables>
  <filterTable name="filterTable1">
    <add filterName="MatchAllFilter1"
         endpointName="Destination"
         backupList="backupEndpointList" />
  </filterTable>
</filterTables>
<backupLists>
  <backupList name="backupEndpointList">
    <add endpointName="backupServiceQueue" />
    <add endpointName="alternateServiceQueue" />
  </backupList>
</backupLists>
```  
  
## <a name="see-also"></a><span data-ttu-id="bec5b-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="bec5b-132">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
