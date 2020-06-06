---
title: <behaviors>워크플로
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 05a15cdf5c043eb5d94b36028324310d2b7a8413
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398870"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="9f757-102">\<behaviors>워크플로</span><span class="sxs-lookup"><span data-stu-id="9f757-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="9f757-103">이 요소는 **Servicebehaviors** 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f757-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="9f757-104">컬렉션의 각 요소는 워크플로 서비스에서 사용하는 동작 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9f757-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="9f757-105">각 동작 요소는 고유한 **이름** 특성으로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f757-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a><span data-ttu-id="9f757-106">구문</span><span class="sxs-lookup"><span data-stu-id="9f757-106">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f757-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9f757-107">Attributes and Elements</span></span>  
 <span data-ttu-id="9f757-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9f757-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f757-109">특성</span><span class="sxs-lookup"><span data-stu-id="9f757-109">Attributes</span></span>  
 <span data-ttu-id="9f757-110">None</span><span class="sxs-lookup"><span data-stu-id="9f757-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9f757-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9f757-111">Child Elements</span></span>  
  
|<span data-ttu-id="9f757-112">요소</span><span class="sxs-lookup"><span data-stu-id="9f757-112">Element</span></span>|<span data-ttu-id="9f757-113">Description</span><span class="sxs-lookup"><span data-stu-id="9f757-113">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors-of-workflow.md)|<span data-ttu-id="9f757-114">이 구성 섹션은 특정 워크플로 서비스에 정의된 모든 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9f757-114">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9f757-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9f757-115">Parent Elements</span></span>  
  
|<span data-ttu-id="9f757-116">요소</span><span class="sxs-lookup"><span data-stu-id="9f757-116">Element</span></span>|<span data-ttu-id="9f757-117">Description</span><span class="sxs-lookup"><span data-stu-id="9f757-117">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](../wcf/system-servicemodel.md)|<span data-ttu-id="9f757-118">모든 워크플로 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9f757-118">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9f757-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9f757-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="9f757-120">동작을 사용하여 런타임 구성 및 확장</span><span class="sxs-lookup"><span data-stu-id="9f757-120">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
