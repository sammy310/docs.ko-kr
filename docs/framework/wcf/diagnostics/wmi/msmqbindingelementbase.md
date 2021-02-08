---
description: '자세히 알아보기: MsmqBindingElementBase'
title: MsmqBindingElementBase
ms.date: 03/30/2017
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
ms.openlocfilehash: 3aa5ec2343d73798f1cf5e3c7d4b5a8282f97ac9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803180"
---
# <a name="msmqbindingelementbase"></a><span data-ttu-id="4e7bd-103">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="4e7bd-103">MsmqBindingElementBase</span></span>

<span data-ttu-id="4e7bd-104">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="4e7bd-104">MsmqBindingElementBase</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e7bd-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e7bd-105">Syntax</span></span>  
  
```csharp  
class MsmqBindingElementBase : TransportBindingElement  
{  
  string CustomDeadLetterQueue;  
  string DeadLetterQueue;  
  boolean Durable;  
  boolean ExactlyOnce;  
  sint32 MaxRetryCycles;  
  string ReceiveErrorHandling;  
  sint32 ReceiveRetryCount;  
  datetime RetryCycleDelay;  
  datetime TimeToLive;  
  boolean UseMsmqTracing;  
  boolean UseSourceJournal;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4e7bd-106">메서드</span><span class="sxs-lookup"><span data-stu-id="4e7bd-106">Methods</span></span>  

 <span data-ttu-id="4e7bd-107">MsmqBindingElementBase 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7bd-107">The MsmqBindingElementBase class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4e7bd-108">속성</span><span class="sxs-lookup"><span data-stu-id="4e7bd-108">Properties</span></span>  

 <span data-ttu-id="4e7bd-109">MsmqBindingElementBase 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7bd-109">The MsmqBindingElementBase class has the following properties:</span></span>  
  
### <a name="customdeadletterqueue"></a><span data-ttu-id="4e7bd-110">CustomDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="4e7bd-110">CustomDeadLetterQueue</span></span>  

 <span data-ttu-id="4e7bd-111">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="4e7bd-111">Data type: string</span></span>  
  
 <span data-ttu-id="4e7bd-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4e7bd-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e7bd-113">애플리케이션별 배달 못 한 편지 큐의 위치를 포함하는 URI입니다. 이 큐에는 만료되었거나 전송 또는 전달하지 못한 메시지가 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7bd-113">A URI that contains the location of the dead letter queue for each application, where messages that have expired or that have failed transfer or delivery are placed.</span></span>  
  
### <a name="deadletterqueue"></a><span data-ttu-id="4e7bd-114">DeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="4e7bd-114">DeadLetterQueue</span></span>  

 <span data-ttu-id="4e7bd-115">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="4e7bd-115">Data type: string</span></span>  
  
 <span data-ttu-id="4e7bd-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4e7bd-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e7bd-117">사용할 배달 못 한 편지 큐의 형식을 나타내는 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4e7bd-117">An enumeration value that indicates the type of dead letter queue to use.</span></span>  
  
### <a name="durable"></a><span data-ttu-id="4e7bd-118">지속성</span><span class="sxs-lookup"><span data-stu-id="4e7bd-118">Durable</span></span>  

 <span data-ttu-id="4e7bd-119">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="4e7bd-119">Data type: boolean</span></span>  
  
 <span data-ttu-id="4e7bd-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4e7bd-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e7bd-121">이 바인딩에서 처리하는 메시지가 지속적인지 또는 일시적인지를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4e7bd-121">A value that indicates whether the messages processed by this binding are durable or volatile.</span></span>  
  
### <a name="exactlyonce"></a><span data-ttu-id="4e7bd-122">ExactlyOnce</span><span class="sxs-lookup"><span data-stu-id="4e7bd-122">ExactlyOnce</span></span>  

 <span data-ttu-id="4e7bd-123">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="4e7bd-123">Data type: boolean</span></span>  
  
 <span data-ttu-id="4e7bd-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4e7bd-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e7bd-125">이 바인딩에서 처리하는 메시지가 단 한 번 수신되는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4e7bd-125">A Boolean value that indicates whether messages processed by this binding are received exactly once.</span></span>  
  
### <a name="maxretrycycles"></a><span data-ttu-id="4e7bd-126">MaxRetryCycles</span><span class="sxs-lookup"><span data-stu-id="4e7bd-126">MaxRetryCycles</span></span>  

 <span data-ttu-id="4e7bd-127">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="4e7bd-127">Data type: sint32</span></span>  
  
 <span data-ttu-id="4e7bd-128">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4e7bd-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e7bd-129">수신 애플리케이션으로 메시지 전달을 시도하는 최대 재시도 주기 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4e7bd-129">The maximum number of retry cycles to attempt delivery of messages to the receiving application.</span></span>  
  
### <a name="receiveerrorhandling"></a><span data-ttu-id="4e7bd-130">ReceiveErrorHandling</span><span class="sxs-lookup"><span data-stu-id="4e7bd-130">ReceiveErrorHandling</span></span>  

 <span data-ttu-id="4e7bd-131">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="4e7bd-131">Data type: string</span></span>  
  
 <span data-ttu-id="4e7bd-132">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4e7bd-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e7bd-133">포이즌 메시지 처리에 대한 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="4e7bd-133">The settings for poison message handling.</span></span>  
  
### <a name="receiveretrycount"></a><span data-ttu-id="4e7bd-134">ReceiveRetryCount</span><span class="sxs-lookup"><span data-stu-id="4e7bd-134">ReceiveRetryCount</span></span>  

 <span data-ttu-id="4e7bd-135">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="4e7bd-135">Data type: sint32</span></span>  
  
 <span data-ttu-id="4e7bd-136">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4e7bd-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e7bd-137">애플리케이션 큐에서 읽은 메시지에 대해 즉시 재시도하는 최대 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="4e7bd-137">The maximum number of immediate retry attempts on a message that is read from the application queue.</span></span>  
  
### <a name="retrycycledelay"></a><span data-ttu-id="4e7bd-138">RetryCycleDelay</span><span class="sxs-lookup"><span data-stu-id="4e7bd-138">RetryCycleDelay</span></span>  

 <span data-ttu-id="4e7bd-139">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="4e7bd-139">Data type: datetime</span></span>  
  
 <span data-ttu-id="4e7bd-140">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4e7bd-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e7bd-141">전달하지 못한 메시지를 즉시 다시 전달하려고 시도할 때 재시도 주기 사이의 지연 시간을 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4e7bd-141">A value that indicates the time delay between retry cycles when attempting to deliver a message that could not be delivered immediately.</span></span>  
  
### <a name="timetolive"></a><span data-ttu-id="4e7bd-142">timeToLive</span><span class="sxs-lookup"><span data-stu-id="4e7bd-142">TimeToLive</span></span>  

 <span data-ttu-id="4e7bd-143">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="4e7bd-143">Data type: datetime</span></span>  
  
 <span data-ttu-id="4e7bd-144">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4e7bd-144">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e7bd-145">이 바인딩에서 처리하는 메시지가 만료되기 전까지 큐에 머무를 수 있는 기간을 나타내는 시간 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="4e7bd-145">The interval of time that indicates how long the messages processed by this binding can be in the queue before they expire.</span></span>  
  
### <a name="usemsmqtracing"></a><span data-ttu-id="4e7bd-146">UseMsmqTracing</span><span class="sxs-lookup"><span data-stu-id="4e7bd-146">UseMsmqTracing</span></span>  

 <span data-ttu-id="4e7bd-147">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="4e7bd-147">Data type: boolean</span></span>  
  
 <span data-ttu-id="4e7bd-148">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4e7bd-148">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e7bd-149">이 바인딩에서 처리하는 메시지의 추적 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4e7bd-149">A Boolean value that indicates whether messages processed by this binding should be traced.</span></span>  
  
### <a name="usesourcejournal"></a><span data-ttu-id="4e7bd-150">UseSourceJournal</span><span class="sxs-lookup"><span data-stu-id="4e7bd-150">UseSourceJournal</span></span>  

 <span data-ttu-id="4e7bd-151">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="4e7bd-151">Data type: boolean</span></span>  
  
 <span data-ttu-id="4e7bd-152">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4e7bd-152">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e7bd-153">이 바인딩에서 처리하는 메시지의 복사본을 소스 업무 일지 큐에 저장하는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4e7bd-153">A Boolean value that indicates whether copies of messages processed by this binding should be stored in the source journal queue.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e7bd-154">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4e7bd-154">Requirements</span></span>  
  
|<span data-ttu-id="4e7bd-155">MOF</span><span class="sxs-lookup"><span data-stu-id="4e7bd-155">MOF</span></span>|<span data-ttu-id="4e7bd-156">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7bd-156">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4e7bd-157">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="4e7bd-157">Namespace</span></span>|<span data-ttu-id="4e7bd-158">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7bd-158">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4e7bd-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e7bd-159">See also</span></span>

- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.MsmqBindingBase>
