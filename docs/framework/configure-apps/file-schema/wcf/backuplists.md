---
description: 다음에 대해 자세히 알아보세요. <backupLists>
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 9647c507f85eba6bfd001b34dbf617bc881d3f2e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749703"
---
# \<backupLists>

<span data-ttu-id="3c8b9-102">오류 처리에서 사용되는 백업 서비스 집합을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3c8b9-102">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="3c8b9-103">각 자식 요소는 라우팅 서비스에서 기본 엔드포인트에 도달할 수 없을 때 사용할 수 있도록 할 엔드포인트 집합을 열거하는 백업 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="3c8b9-103">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="3c8b9-104">목록의 첫 번째 엔드포인트가 다운되는 경우 라우팅 서비스는 자동으로 목록의 다음 엔드포인트로 장애 조치(failover)됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c8b9-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="3c8b9-105">따라서 복잡한 패턴을 처리하는 방법이나 모든 서비스가 배포되는 위치를 클라이언트 애플리케이션에 지정할 필요 없이 애플리케이션의 안정성을 빠르게 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c8b9-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupLists>**  
  
## <a name="syntax"></a><span data-ttu-id="3c8b9-106">구문</span><span class="sxs-lookup"><span data-stu-id="3c8b9-106">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c8b9-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3c8b9-107">Attributes and Elements</span></span>  

 <span data-ttu-id="3c8b9-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3c8b9-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c8b9-109">특성</span><span class="sxs-lookup"><span data-stu-id="3c8b9-109">Attributes</span></span>  

 <span data-ttu-id="3c8b9-110">없음</span><span class="sxs-lookup"><span data-stu-id="3c8b9-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3c8b9-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3c8b9-111">Child Elements</span></span>  
  
|<span data-ttu-id="3c8b9-112">요소</span><span class="sxs-lookup"><span data-stu-id="3c8b9-112">Element</span></span>|<span data-ttu-id="3c8b9-113">설명</span><span class="sxs-lookup"><span data-stu-id="3c8b9-113">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter.md)|<span data-ttu-id="3c8b9-114">라우팅 서비스에서 기본 엔드포인트에 도달할 수 없을 때 사용할 수 있도록 할 엔드포인트의 목록을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3c8b9-114">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="3c8b9-115">.</span><span class="sxs-lookup"><span data-stu-id="3c8b9-115">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3c8b9-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3c8b9-116">Parent Elements</span></span>  
  
|<span data-ttu-id="3c8b9-117">요소</span><span class="sxs-lookup"><span data-stu-id="3c8b9-117">Element</span></span>|<span data-ttu-id="3c8b9-118">설명</span><span class="sxs-lookup"><span data-stu-id="3c8b9-118">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="3c8b9-119"><xref:System.ServiceModel.Dispatcher.MessageFilter>들어오는 메시지를 평가할 때 사용할 WCF (Windows Communication Foundation 유형)와 필터가 일치할 때 메시지를 보낼 대상 끝점을 정의 하는 라우팅 테이블을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3c8b9-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3c8b9-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c8b9-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
