---
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 478211755b9131c03b72777ee95ff7223b9092c9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850280"
---
# \<backupList>
<span data-ttu-id="17e36-101">라우팅 서비스에서 기본 엔드포인트에 도달할 수 없을 때 사용할 수 있도록 할 엔드포인트 집합을 열거하는 백업 목록을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="17e36-101">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="17e36-102">목록의 첫 번째 엔드포인트가 다운되는 경우 라우팅 서비스는 자동으로 목록의 다음 엔드포인트로 장애 조치(failover)됩니다.</span><span class="sxs-lookup"><span data-stu-id="17e36-102">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="17e36-103">따라서 복잡한 패턴을 처리하는 방법이나 모든 서비스가 배포되는 위치를 클라이언트 애플리케이션에 지정할 필요 없이 애플리케이션의 안정성을 빠르게 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17e36-103">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupList>**  
  
## <a name="syntax"></a><span data-ttu-id="17e36-104">구문</span><span class="sxs-lookup"><span data-stu-id="17e36-104">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17e36-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="17e36-105">Attributes and Elements</span></span>  
 <span data-ttu-id="17e36-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="17e36-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17e36-107">특성</span><span class="sxs-lookup"><span data-stu-id="17e36-107">Attributes</span></span>  
  
|<span data-ttu-id="17e36-108">attribute</span><span class="sxs-lookup"><span data-stu-id="17e36-108">Attribute</span></span>|<span data-ttu-id="17e36-109">Description</span><span class="sxs-lookup"><span data-stu-id="17e36-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="17e36-110">name</span><span class="sxs-lookup"><span data-stu-id="17e36-110">name</span></span>|<span data-ttu-id="17e36-111">이 엔드포인트 목록을 식별하는 데 사용되는 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="17e36-111">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="17e36-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="17e36-112">Child Elements</span></span>  
  
|<span data-ttu-id="17e36-113">요소</span><span class="sxs-lookup"><span data-stu-id="17e36-113">Element</span></span>|<span data-ttu-id="17e36-114">Description</span><span class="sxs-lookup"><span data-stu-id="17e36-114">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="17e36-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="17e36-115">Parent Elements</span></span>  
  
|<span data-ttu-id="17e36-116">요소</span><span class="sxs-lookup"><span data-stu-id="17e36-116">Element</span></span>|<span data-ttu-id="17e36-117">Description</span><span class="sxs-lookup"><span data-stu-id="17e36-117">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="17e36-118">백업 엔드포인트의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="17e36-118">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17e36-119">설명</span><span class="sxs-lookup"><span data-stu-id="17e36-119">Remarks</span></span>  
 <span data-ttu-id="17e36-120">이 섹션에는 기본 엔드포인트로 메시지를 보낼 때 통신 예외가 발생하면 이 메시지를 전송할 엔드포인트의 정렬된 컬렉션이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="17e36-120">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="17e36-121">의 특성에 나열 된 기본 끝점에 대 한 보내기가 `endpointName` [\<add>](add-of-entries.md) 통신 예외와 함께 실패 하는 경우 라우팅 서비스는이 구성 섹션에 있는 첫 번째 끝점으로 메시지를 보내려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="17e36-121">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="17e36-122">이것도 통신 예외가 발생하여 실패하는 경우 라우팅 서비스는 보내기가 성공할 때까지, 통신 예외가 아닌 다른 원인으로 보내기가 실패할 때까지 또는 컬렉션의 모든 엔드포인트에 대한 보내기가 실패할 때까지 이 섹션에 포함된 다음 엔드포인트로 메시지를 보내려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="17e36-122">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="17e36-123">다음 예제에서는 &quot;Destination&quot; 이라는 기본 엔드포인트으로 송신 통신 예외가 반환 하는 경우 서비스를 &quot;alternateservicequeue&quot;로 메시지를 보낼 시도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17e36-123">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="17e36-124">이 시도에 대해서도 통신 예외가 반환되면 라우팅 서비스는 컬렉션의 다음 엔드포인트로 메시지를 보내려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="17e36-124">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="17e36-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="17e36-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
