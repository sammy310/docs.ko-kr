---
description: 다음에 대해 자세히 알아보세요. <bufferReceive>
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 8f5e58e0e72a81d8b3a20a68e0890be907c20d2b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698091"
---
# \<bufferReceive>

<span data-ttu-id="c2dc7-102">서비스에서 버퍼링되는 수신 처리를 사용할 수 있도록 하는 서비스 동작입니다. 이를 통해 워크플로 서비스가 순서가 맞지 않는 메시지를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2dc7-102">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bufferReceive>**  
  
## <a name="syntax"></a><span data-ttu-id="c2dc7-103">구문</span><span class="sxs-lookup"><span data-stu-id="c2dc7-103">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2dc7-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c2dc7-104">Attributes and Elements</span></span>  

 <span data-ttu-id="c2dc7-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c2dc7-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2dc7-106">특성</span><span class="sxs-lookup"><span data-stu-id="c2dc7-106">Attributes</span></span>  
  
|<span data-ttu-id="c2dc7-107">attribute</span><span class="sxs-lookup"><span data-stu-id="c2dc7-107">Attribute</span></span>|<span data-ttu-id="c2dc7-108">설명</span><span class="sxs-lookup"><span data-stu-id="c2dc7-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c2dc7-109">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="c2dc7-109">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="c2dc7-110">각 채널에 허용되는 최대 보류 메시지 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="c2dc7-110">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="c2dc7-111">기본값은 512입니다.</span><span class="sxs-lookup"><span data-stu-id="c2dc7-111">The default value is 512.</span></span> <span data-ttu-id="c2dc7-112">이 속성은 워크플로 서비스가 수신할 수 있는 순서가 맞지 않는 메시지의 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="c2dc7-112">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c2dc7-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c2dc7-113">Child Elements</span></span>  

 <span data-ttu-id="c2dc7-114">없음</span><span class="sxs-lookup"><span data-stu-id="c2dc7-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c2dc7-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c2dc7-115">Parent Elements</span></span>  
  
|<span data-ttu-id="c2dc7-116">요소</span><span class="sxs-lookup"><span data-stu-id="c2dc7-116">Element</span></span>|<span data-ttu-id="c2dc7-117">설명</span><span class="sxs-lookup"><span data-stu-id="c2dc7-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c2dc7-118">\<serviceBehaviors>의 \<behavior></span><span class="sxs-lookup"><span data-stu-id="c2dc7-118">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="c2dc7-119">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c2dc7-119">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c2dc7-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2dc7-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
