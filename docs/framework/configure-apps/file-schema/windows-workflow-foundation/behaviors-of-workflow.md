---
description: '다음에 대 한 자세한 정보: <behaviors> 워크플로'
title: <behaviors> 워크플로
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 5154a389aded34065cc7bdb11d1c73d71ca9f9f5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698195"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="60b0f-103">\<behaviors> 워크플로</span><span class="sxs-lookup"><span data-stu-id="60b0f-103">\<behaviors> of workflow</span></span>

<span data-ttu-id="60b0f-104">이 요소는 **Servicebehaviors** 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b0f-104">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="60b0f-105">컬렉션의 각 요소는 워크플로 서비스에서 사용하는 동작 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="60b0f-105">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="60b0f-106">각 동작 요소는 고유한 **이름** 특성으로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60b0f-106">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a><span data-ttu-id="60b0f-107">구문</span><span class="sxs-lookup"><span data-stu-id="60b0f-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60b0f-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="60b0f-108">Attributes and Elements</span></span>  

 <span data-ttu-id="60b0f-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="60b0f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60b0f-110">특성</span><span class="sxs-lookup"><span data-stu-id="60b0f-110">Attributes</span></span>  

 <span data-ttu-id="60b0f-111">None</span><span class="sxs-lookup"><span data-stu-id="60b0f-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="60b0f-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="60b0f-112">Child Elements</span></span>  
  
|<span data-ttu-id="60b0f-113">요소</span><span class="sxs-lookup"><span data-stu-id="60b0f-113">Element</span></span>|<span data-ttu-id="60b0f-114">설명</span><span class="sxs-lookup"><span data-stu-id="60b0f-114">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors-of-workflow.md)|<span data-ttu-id="60b0f-115">이 구성 섹션은 특정 워크플로 서비스에 정의된 모든 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="60b0f-115">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="60b0f-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="60b0f-116">Parent Elements</span></span>  
  
|<span data-ttu-id="60b0f-117">요소</span><span class="sxs-lookup"><span data-stu-id="60b0f-117">Element</span></span>|<span data-ttu-id="60b0f-118">설명</span><span class="sxs-lookup"><span data-stu-id="60b0f-118">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](../wcf/system-servicemodel.md)|<span data-ttu-id="60b0f-119">모든 워크플로 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="60b0f-119">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60b0f-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60b0f-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="60b0f-121">동작을 사용하여 런타임 구성 및 확장</span><span class="sxs-lookup"><span data-stu-id="60b0f-121">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
