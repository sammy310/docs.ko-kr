---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 940bf28958251e7257b2cc19a9c5ff0059411bcd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201553"
---
# \<backupLists>

<span data-ttu-id="ed821-101">오류 처리에서 사용되는 백업 서비스 집합을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ed821-101">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="ed821-102">각 자식 요소는 라우팅 서비스에서 기본 엔드포인트에 도달할 수 없을 때 사용할 수 있도록 할 엔드포인트 집합을 열거하는 백업 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ed821-102">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="ed821-103">목록의 첫 번째 엔드포인트가 다운되는 경우 라우팅 서비스는 자동으로 목록의 다음 엔드포인트로 장애 조치(failover)됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed821-103">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="ed821-104">따라서 복잡한 패턴을 처리하는 방법이나 모든 서비스가 배포되는 위치를 클라이언트 애플리케이션에 지정할 필요 없이 애플리케이션의 안정성을 빠르게 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed821-104">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupLists>**  
  
## <a name="syntax"></a><span data-ttu-id="ed821-105">구문</span><span class="sxs-lookup"><span data-stu-id="ed821-105">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed821-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ed821-106">Attributes and Elements</span></span>  

 <span data-ttu-id="ed821-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ed821-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed821-108">특성</span><span class="sxs-lookup"><span data-stu-id="ed821-108">Attributes</span></span>  

 <span data-ttu-id="ed821-109">없음</span><span class="sxs-lookup"><span data-stu-id="ed821-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ed821-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ed821-110">Child Elements</span></span>  
  
|<span data-ttu-id="ed821-111">요소</span><span class="sxs-lookup"><span data-stu-id="ed821-111">Element</span></span>|<span data-ttu-id="ed821-112">설명</span><span class="sxs-lookup"><span data-stu-id="ed821-112">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter.md)|<span data-ttu-id="ed821-113">라우팅 서비스에서 기본 엔드포인트에 도달할 수 없을 때 사용할 수 있도록 할 엔드포인트의 목록을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ed821-113">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="ed821-114">.</span><span class="sxs-lookup"><span data-stu-id="ed821-114">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ed821-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ed821-115">Parent Elements</span></span>  
  
|<span data-ttu-id="ed821-116">요소</span><span class="sxs-lookup"><span data-stu-id="ed821-116">Element</span></span>|<span data-ttu-id="ed821-117">설명</span><span class="sxs-lookup"><span data-stu-id="ed821-117">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="ed821-118"><xref:System.ServiceModel.Dispatcher.MessageFilter>들어오는 메시지를 평가할 때 사용할 WCF (Windows Communication Foundation 유형)와 필터가 일치할 때 메시지를 보낼 대상 끝점을 정의 하는 라우팅 테이블을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ed821-118">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ed821-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed821-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
