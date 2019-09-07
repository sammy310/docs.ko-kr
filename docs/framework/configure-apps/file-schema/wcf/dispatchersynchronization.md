---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: b95f25217c2a3558846cc7a0ef43e21aacd2ee2a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398010"
---
# <a name="dispatchersynchronization"></a><span data-ttu-id="78dc8-101">\<dispatcherSynchronization></span><span class="sxs-lookup"><span data-stu-id="78dc8-101">\<dispatcherSynchronization></span></span>
  
<span data-ttu-id="78dc8-102">서비스에서 응답을 비동기적으로 보낼 수 있도록 하는 엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="78dc8-102">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="78dc8-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="78dc8-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="78dc8-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="78dc8-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="78dc8-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="78dc8-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="78dc8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="78dc8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="78dc8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="78dc8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="78dc8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<dispatcherSynchronization >**</span><span class="sxs-lookup"><span data-stu-id="78dc8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dispatcherSynchronization>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78dc8-109">구문</span><span class="sxs-lookup"><span data-stu-id="78dc8-109">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="78dc8-110">형식</span><span class="sxs-lookup"><span data-stu-id="78dc8-110">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78dc8-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="78dc8-111">Attributes and elements</span></span>  
  
<span data-ttu-id="78dc8-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="78dc8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78dc8-113">특성</span><span class="sxs-lookup"><span data-stu-id="78dc8-113">Attributes</span></span>

| <span data-ttu-id="78dc8-114">특성</span><span class="sxs-lookup"><span data-stu-id="78dc8-114">Attribute</span></span>               | <span data-ttu-id="78dc8-115">Description</span><span class="sxs-lookup"><span data-stu-id="78dc8-115">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="78dc8-116">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="78dc8-116">asynchronousSendEnabled</span></span> | <span data-ttu-id="78dc8-117">비동기 보내기 동작 사용 여부를 나타내는 부울입니다.</span><span class="sxs-lookup"><span data-stu-id="78dc8-117">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="78dc8-118">채널에서 발급할 수 있는 동시 수신의 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="78dc8-118">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="78dc8-119">이 값은 서비스 스로틀 동작을 제대로 구성한 후에 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78dc8-119">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="78dc8-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="78dc8-120">Child elements</span></span>

<span data-ttu-id="78dc8-121">없음</span><span class="sxs-lookup"><span data-stu-id="78dc8-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="78dc8-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="78dc8-122">Parent elements</span></span>

| <span data-ttu-id="78dc8-123">요소</span><span class="sxs-lookup"><span data-stu-id="78dc8-123">Element</span></span> | <span data-ttu-id="78dc8-124">설명</span><span class="sxs-lookup"><span data-stu-id="78dc8-124">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="78dc8-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="78dc8-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="78dc8-126">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="78dc8-126">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="78dc8-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="78dc8-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
