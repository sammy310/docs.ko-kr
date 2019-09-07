---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: be5173ea43c6f7fca7180a311885a26c889b12db
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398843"
---
# <a name="bufferreceive"></a><span data-ttu-id="924cf-101">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="924cf-101">\<bufferReceive></span></span>
<span data-ttu-id="924cf-102">서비스에서 버퍼링되는 수신 처리를 사용할 수 있도록 하는 서비스 동작입니다. 이를 통해 워크플로 서비스가 순서가 맞지 않는 메시지를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="924cf-102">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="924cf-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="924cf-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="924cf-104">&nbsp;&nbsp;[ **\<컴퓨터. ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="924cf-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="924cf-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="924cf-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="924cf-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="924cf-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="924cf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="924cf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="924cf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<bufferReceive >**</span><span class="sxs-lookup"><span data-stu-id="924cf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bufferReceive>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="924cf-109">구문</span><span class="sxs-lookup"><span data-stu-id="924cf-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="924cf-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="924cf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="924cf-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="924cf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="924cf-112">특성</span><span class="sxs-lookup"><span data-stu-id="924cf-112">Attributes</span></span>  
  
|<span data-ttu-id="924cf-113">특성</span><span class="sxs-lookup"><span data-stu-id="924cf-113">Attribute</span></span>|<span data-ttu-id="924cf-114">Description</span><span class="sxs-lookup"><span data-stu-id="924cf-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="924cf-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="924cf-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="924cf-116">각 채널에 허용되는 최대 보류 메시지 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="924cf-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="924cf-117">기본값은 512입니다.</span><span class="sxs-lookup"><span data-stu-id="924cf-117">The default value is 512.</span></span> <span data-ttu-id="924cf-118">이 속성은 워크플로 서비스가 수신할 수 있는 순서가 맞지 않는 메시지의 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="924cf-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="924cf-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="924cf-119">Child Elements</span></span>  
 <span data-ttu-id="924cf-120">없음</span><span class="sxs-lookup"><span data-stu-id="924cf-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="924cf-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="924cf-121">Parent Elements</span></span>  
  
|<span data-ttu-id="924cf-122">요소</span><span class="sxs-lookup"><span data-stu-id="924cf-122">Element</span></span>|<span data-ttu-id="924cf-123">Description</span><span class="sxs-lookup"><span data-stu-id="924cf-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="924cf-124">\<servicebehaviors의 \<동작 > ></span><span class="sxs-lookup"><span data-stu-id="924cf-124">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="924cf-125">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="924cf-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="924cf-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="924cf-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
