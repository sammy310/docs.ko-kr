---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 16d4546bce461b55695e0deed093396ce1c2b0b6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189567"
---
# \<bufferReceive>

<span data-ttu-id="74b84-101">서비스에서 버퍼링되는 수신 처리를 사용할 수 있도록 하는 서비스 동작입니다. 이를 통해 워크플로 서비스가 순서가 맞지 않는 메시지를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74b84-101">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bufferReceive>**  
  
## <a name="syntax"></a><span data-ttu-id="74b84-102">구문</span><span class="sxs-lookup"><span data-stu-id="74b84-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74b84-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="74b84-103">Attributes and Elements</span></span>  

 <span data-ttu-id="74b84-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="74b84-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74b84-105">특성</span><span class="sxs-lookup"><span data-stu-id="74b84-105">Attributes</span></span>  
  
|<span data-ttu-id="74b84-106">attribute</span><span class="sxs-lookup"><span data-stu-id="74b84-106">Attribute</span></span>|<span data-ttu-id="74b84-107">설명</span><span class="sxs-lookup"><span data-stu-id="74b84-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="74b84-108">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="74b84-108">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="74b84-109">각 채널에 허용되는 최대 보류 메시지 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="74b84-109">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="74b84-110">기본값은 512입니다.</span><span class="sxs-lookup"><span data-stu-id="74b84-110">The default value is 512.</span></span> <span data-ttu-id="74b84-111">이 속성은 워크플로 서비스가 수신할 수 있는 순서가 맞지 않는 메시지의 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="74b84-111">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74b84-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="74b84-112">Child Elements</span></span>  

 <span data-ttu-id="74b84-113">없음</span><span class="sxs-lookup"><span data-stu-id="74b84-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74b84-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="74b84-114">Parent Elements</span></span>  
  
|<span data-ttu-id="74b84-115">요소</span><span class="sxs-lookup"><span data-stu-id="74b84-115">Element</span></span>|<span data-ttu-id="74b84-116">설명</span><span class="sxs-lookup"><span data-stu-id="74b84-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74b84-117">\<serviceBehaviors>의 \<behavior></span><span class="sxs-lookup"><span data-stu-id="74b84-117">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="74b84-118">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="74b84-118">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="74b84-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74b84-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
