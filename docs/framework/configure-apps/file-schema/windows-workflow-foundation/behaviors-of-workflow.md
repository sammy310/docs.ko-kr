---
title: <behaviors>워크플로
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 7dd3b0b20c9d7accd80a85b3693e67ffc9b729e5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946001"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="3965c-102">\<워크플로의 동작 ></span><span class="sxs-lookup"><span data-stu-id="3965c-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="3965c-103">이 요소는 **Servicebehaviors** 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3965c-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="3965c-104">컬렉션의 각 요소는 워크플로 서비스에서 사용하는 동작 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3965c-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="3965c-105">각 동작 요소는 고유한 **이름** 특성으로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3965c-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="3965c-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3965c-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3965c-107">구문</span><span class="sxs-lookup"><span data-stu-id="3965c-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3965c-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3965c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3965c-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3965c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3965c-110">특성</span><span class="sxs-lookup"><span data-stu-id="3965c-110">Attributes</span></span>  
 <span data-ttu-id="3965c-111">없음</span><span class="sxs-lookup"><span data-stu-id="3965c-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3965c-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3965c-112">Child Elements</span></span>  
  
|<span data-ttu-id="3965c-113">요소</span><span class="sxs-lookup"><span data-stu-id="3965c-113">Element</span></span>|<span data-ttu-id="3965c-114">설명</span><span class="sxs-lookup"><span data-stu-id="3965c-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3965c-115">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="3965c-115">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="3965c-116">이 구성 섹션은 특정 워크플로 서비스에 정의된 모든 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3965c-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3965c-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3965c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3965c-118">요소</span><span class="sxs-lookup"><span data-stu-id="3965c-118">Element</span></span>|<span data-ttu-id="3965c-119">Description</span><span class="sxs-lookup"><span data-stu-id="3965c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3965c-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3965c-120">\<system.serviceModel></span></span>](../wcf/system-servicemodel.md)|<span data-ttu-id="3965c-121">모든 워크플로 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3965c-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3965c-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="3965c-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="3965c-123">동작을 사용하여 런타임 구성 및 확장</span><span class="sxs-lookup"><span data-stu-id="3965c-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
