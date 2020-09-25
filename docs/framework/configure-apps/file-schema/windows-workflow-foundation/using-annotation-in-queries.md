---
title: 쿼리에 주석 사용
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
ms.openlocfilehash: 3dd5d19cc303314386ae62ba67f7eec978f6d80b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185368"
---
# <a name="using-annotation-in-queries"></a><span data-ttu-id="be4aa-102">쿼리에 주석 사용</span><span class="sxs-lookup"><span data-stu-id="be4aa-102">Using Annotation in Queries</span></span>

<span data-ttu-id="be4aa-103">주석을 사용하여 빌드 시간 후에 구성될 수 있는 값으로 추적 레코드에 임의 태그를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be4aa-103">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="be4aa-104">예를 들어 여러 워크플로 간에 여러 추적 레코드를 "Mail Server" = = "Mail Server1"로 태그를 지정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="be4aa-104">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="be4aa-105">이렇게 하면 나중에 추적 레코드를 쿼리할 때 이 태그를 사용하여 모든 레코드를 쉽게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be4aa-105">This makes it easy to find all records with this tag when querying tracking records later.</span></span>  
  
## <a name="adding-annotations"></a><span data-ttu-id="be4aa-106">주석 추가</span><span class="sxs-lookup"><span data-stu-id="be4aa-106">Adding Annotations</span></span>  

 <span data-ttu-id="be4aa-107">다음 예제와 같이 추적 쿼리에 주석을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be4aa-107">An annotation can be added to a tracking query as shown in the following example.</span></span>  
  
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
> <span data-ttu-id="be4aa-108">이러한 추적 쿼리 요소를 사용하여 추적 프로필을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be4aa-108">These tracking query elements can be used to create a tracking profile.</span></span> <span data-ttu-id="be4aa-109">추적 프로필은 구성이나 코드를 사용하여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be4aa-109">A tracking profile can be created either in configuration or using code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be4aa-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be4aa-110">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [\<participants>](participants.md)
- [<span data-ttu-id="be4aa-111">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="be4aa-111">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="be4aa-112">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="be4aa-112">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
