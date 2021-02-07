---
description: 다음에 대해 자세히 알아보세요. <dispatcherSynchronization>
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 93664dec3648ed58df7e3e5c0760f1694c60ba7e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749606"
---
# \<dispatcherSynchronization>
  
<span data-ttu-id="9150f-102">서비스에서 응답을 비동기적으로 보낼 수 있도록 하는 엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9150f-102">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dispatcherSynchronization>**  
  
## <a name="syntax"></a><span data-ttu-id="9150f-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="9150f-103">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="9150f-104">Type</span><span class="sxs-lookup"><span data-stu-id="9150f-104">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9150f-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9150f-105">Attributes and elements</span></span>  
  
<span data-ttu-id="9150f-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9150f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9150f-107">특성</span><span class="sxs-lookup"><span data-stu-id="9150f-107">Attributes</span></span>

| <span data-ttu-id="9150f-108">attribute</span><span class="sxs-lookup"><span data-stu-id="9150f-108">Attribute</span></span>               | <span data-ttu-id="9150f-109">설명</span><span class="sxs-lookup"><span data-stu-id="9150f-109">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="9150f-110">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="9150f-110">asynchronousSendEnabled</span></span> | <span data-ttu-id="9150f-111">비동기 보내기 동작 사용 여부를 나타내는 부울입니다.</span><span class="sxs-lookup"><span data-stu-id="9150f-111">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="9150f-112">채널에서 발급할 수 있는 동시 수신의 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="9150f-112">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="9150f-113">이 값은 서비스 스로틀 동작을 제대로 구성한 후에 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9150f-113">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="9150f-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9150f-114">Child elements</span></span>

<span data-ttu-id="9150f-115">없음</span><span class="sxs-lookup"><span data-stu-id="9150f-115">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9150f-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9150f-116">Parent elements</span></span>

| <span data-ttu-id="9150f-117">요소</span><span class="sxs-lookup"><span data-stu-id="9150f-117">Element</span></span> | <span data-ttu-id="9150f-118">설명</span><span class="sxs-lookup"><span data-stu-id="9150f-118">Description</span></span> |  
| ------- | ----------- |  
| [\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="9150f-119">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9150f-119">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="9150f-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9150f-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
