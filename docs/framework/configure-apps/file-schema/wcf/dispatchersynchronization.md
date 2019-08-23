---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 7336c9f7d8a117f9a9bfd338e47941eeb648fa51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925849"
---
# <a name="dispatchersynchronization"></a><span data-ttu-id="308f6-101">\<dispatcherSynchronization></span><span class="sxs-lookup"><span data-stu-id="308f6-101">\<dispatcherSynchronization></span></span>
  
<span data-ttu-id="308f6-102">서비스에서 응답을 비동기적으로 보낼 수 있도록 하는 엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="308f6-102">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="308f6-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="308f6-103">\<system.serviceModel></span></span>  
<span data-ttu-id="308f6-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="308f6-104">\<behaviors></span></span>  
<span data-ttu-id="308f6-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="308f6-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="308f6-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="308f6-106">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="308f6-107">구문</span><span class="sxs-lookup"><span data-stu-id="308f6-107">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="308f6-108">형식</span><span class="sxs-lookup"><span data-stu-id="308f6-108">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="308f6-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="308f6-109">Attributes and elements</span></span>  
  
<span data-ttu-id="308f6-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="308f6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="308f6-111">특성</span><span class="sxs-lookup"><span data-stu-id="308f6-111">Attributes</span></span>

| <span data-ttu-id="308f6-112">특성</span><span class="sxs-lookup"><span data-stu-id="308f6-112">Attribute</span></span>               | <span data-ttu-id="308f6-113">Description</span><span class="sxs-lookup"><span data-stu-id="308f6-113">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="308f6-114">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="308f6-114">asynchronousSendEnabled</span></span> | <span data-ttu-id="308f6-115">비동기 보내기 동작 사용 여부를 나타내는 부울입니다.</span><span class="sxs-lookup"><span data-stu-id="308f6-115">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="308f6-116">채널에서 발급할 수 있는 동시 수신의 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="308f6-116">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="308f6-117">이 값은 서비스 스로틀 동작을 제대로 구성한 후에 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="308f6-117">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="308f6-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="308f6-118">Child elements</span></span>

<span data-ttu-id="308f6-119">없음</span><span class="sxs-lookup"><span data-stu-id="308f6-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="308f6-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="308f6-120">Parent elements</span></span>

| <span data-ttu-id="308f6-121">요소</span><span class="sxs-lookup"><span data-stu-id="308f6-121">Element</span></span> | <span data-ttu-id="308f6-122">설명</span><span class="sxs-lookup"><span data-stu-id="308f6-122">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="308f6-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="308f6-123">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="308f6-124">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="308f6-124">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="308f6-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="308f6-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
