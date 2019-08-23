---
title: 쿼리에 주석 사용
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
ms.openlocfilehash: 728408e744bc1eca62158fab1a7a17e985fe3b6c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947279"
---
# <a name="using-annotation-in-queries"></a><span data-ttu-id="82ae2-102">쿼리에 주석 사용</span><span class="sxs-lookup"><span data-stu-id="82ae2-102">Using Annotation in Queries</span></span>
<span data-ttu-id="82ae2-103">주석을 사용하여 빌드 시간 후에 구성될 수 있는 값으로 추적 레코드에 임의 태그를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ae2-103">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="82ae2-104">예를 들어 여러 워크플로 간에 여러 추적 레코드를 "Mail Server" = = "Mail Server1"로 태그를 지정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="82ae2-104">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="82ae2-105">이렇게 하면 나중에 추적 레코드를 쿼리할 때 이 태그를 사용하여 모든 레코드를 쉽게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ae2-105">This makes it easy to find all records with this tag when querying tracking records later.</span></span>  
  
## <a name="adding-annotations"></a><span data-ttu-id="82ae2-106">주석 추가</span><span class="sxs-lookup"><span data-stu-id="82ae2-106">Adding Annotations</span></span>  
 <span data-ttu-id="82ae2-107">다음 예제와 같이 추적 쿼리에 주석을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ae2-107">An annotation can be added to a tracking query as shown in the following example.</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <annotations>  
    <annotation name="MailServer" value="Mail Server1"/>  
  </annotations>  
</activityStateQuery>  
```  
  
> [!NOTE]
> <span data-ttu-id="82ae2-108">이러한 추적 쿼리 요소를 사용하여 추적 프로필을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ae2-108">These tracking query elements can be used to create a tracking profile.</span></span> <span data-ttu-id="82ae2-109">추적 프로필은 구성이나 코드를 사용하여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ae2-109">A tracking profile can be created either in configuration or using code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82ae2-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="82ae2-110">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="82ae2-111">\<participants></span><span class="sxs-lookup"><span data-stu-id="82ae2-111">\<participants></span></span>](participants.md)
- [<span data-ttu-id="82ae2-112">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="82ae2-112">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="82ae2-113">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="82ae2-113">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
