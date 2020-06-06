---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: b95f25217c2a3558846cc7a0ef43e21aacd2ee2a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398010"
---
# \<dispatcherSynchronization>
  
<span data-ttu-id="3be48-101">서비스에서 응답을 비동기적으로 보낼 수 있도록 하는 엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3be48-101">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dispatcherSynchronization>**  
  
## <a name="syntax"></a><span data-ttu-id="3be48-102">구문</span><span class="sxs-lookup"><span data-stu-id="3be48-102">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="3be48-103">Type</span><span class="sxs-lookup"><span data-stu-id="3be48-103">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3be48-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3be48-104">Attributes and elements</span></span>  
  
<span data-ttu-id="3be48-105">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3be48-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3be48-106">특성</span><span class="sxs-lookup"><span data-stu-id="3be48-106">Attributes</span></span>

| <span data-ttu-id="3be48-107">attribute</span><span class="sxs-lookup"><span data-stu-id="3be48-107">Attribute</span></span>               | <span data-ttu-id="3be48-108">Description</span><span class="sxs-lookup"><span data-stu-id="3be48-108">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="3be48-109">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="3be48-109">asynchronousSendEnabled</span></span> | <span data-ttu-id="3be48-110">비동기 보내기 동작 사용 여부를 나타내는 부울입니다.</span><span class="sxs-lookup"><span data-stu-id="3be48-110">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="3be48-111">채널에서 발급할 수 있는 동시 수신의 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="3be48-111">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="3be48-112">이 값은 서비스 스로틀 동작을 제대로 구성한 후에 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be48-112">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="3be48-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3be48-113">Child elements</span></span>

<span data-ttu-id="3be48-114">없음</span><span class="sxs-lookup"><span data-stu-id="3be48-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3be48-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3be48-115">Parent elements</span></span>

| <span data-ttu-id="3be48-116">요소</span><span class="sxs-lookup"><span data-stu-id="3be48-116">Element</span></span> | <span data-ttu-id="3be48-117">Description</span><span class="sxs-lookup"><span data-stu-id="3be48-117">Description</span></span> |  
| ------- | ----------- |  
| [\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="3be48-118">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3be48-118">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="3be48-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3be48-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
