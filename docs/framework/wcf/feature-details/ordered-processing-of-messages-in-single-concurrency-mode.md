---
title: 단일 동시성 모델에서 메시지의 순서 지정 처리
ms.date: 03/30/2017
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
ms.openlocfilehash: 785c2953e57eaf967209b0d9e52ab85a3a99c450
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229721"
---
# <a name="ordered-processing-of-messages-in-single-concurrency-mode"></a><span data-ttu-id="e8e37-102">단일 동시성 모델에서 메시지의 순서 지정 처리</span><span class="sxs-lookup"><span data-stu-id="e8e37-102">Ordered Processing of Messages in Single Concurrency Mode</span></span>
<span data-ttu-id="e8e37-103">WCF는 기본 채널 세션 없는 메시지 처리 되는 순서에 대 한 보증도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8e37-103">WCF makes no guarantees about the order in which messages are processed, unless the underlying channel is sessionful.</span></span>  <span data-ttu-id="e8e37-104">예를 들어 MsmqInputChannel 없는 세션 채널을 사용 하는 WCF 서비스는 순서 대로 메시지를 처리 하는 데 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8e37-104">For instance, a WCF service that uses MsmqInputChannel, which is not a sessionful channel, will fail to process messages in order.</span></span> <span data-ttu-id="e8e37-105">개발자 처리 동작에 순서를 사용할 수 있지만 세션을 사용 하려면 여기서 몇 가지 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8e37-105">There are some circumstances where a developer may want the in order processing behavior but not want to use sessions.</span></span> <span data-ttu-id="e8e37-106">이 항목에서는 서비스가 단일 동시성 모델에서 실행되고 있을 때 이 동작을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e8e37-106">This topic describes how to configure this behavior when a service is running in Single Concurrency Mode.</span></span>  
  
## <a name="in-order-message-processing"></a><span data-ttu-id="e8e37-107">순서에 따른 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="e8e37-107">In-order Message Processing</span></span>  
 <span data-ttu-id="e8e37-108"><xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A>라는 새 속성이 <xref:System.ServiceModel.ServiceBehaviorAttribute>에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e8e37-108">A new attribute called <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> has been added to the <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span></span> <span data-ttu-id="e8e37-109"><xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A>가 true로 설정되고 <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>가 <xref:System.ServiceModel.ConcurrencyMode.Single>로 설정되면 서비스에 전송된 메시지는 순서대로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8e37-109">When <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> is set to true and <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to <xref:System.ServiceModel.ConcurrencyMode.Single> messages sent to the service will be processed in order.</span></span> <span data-ttu-id="e8e37-110">다음 코드 조각에서는 이러한 특성을 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e8e37-110">The following code snippet illustrates how to set these attributes.</span></span>  
  
```  
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
```  
  
 <span data-ttu-id="e8e37-111"><xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>가 다른 값으로 설정되면 <xref:System.InvalidOperationException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8e37-111">If <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to any other value, an <xref:System.InvalidOperationException> is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8e37-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="e8e37-112">See also</span></span>

- [<span data-ttu-id="e8e37-113">세션, 인스턴스 및 동시성</span><span class="sxs-lookup"><span data-stu-id="e8e37-113">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
- [<span data-ttu-id="e8e37-114">동시성</span><span class="sxs-lookup"><span data-stu-id="e8e37-114">Concurrency</span></span>](../../../../docs/framework/wcf/samples/concurrency.md)
