---
description: 다음에 대해 자세히 알아보세요. <reliableSession>
title: <reliableSession>
ms.date: 03/30/2017
ms.assetid: 129b4a59-37f0-4030-b664-03795d257d29
ms.openlocfilehash: 5b5798326be9b376ece4e590f068f5b5e71bd878
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683413"
---
# \<reliableSession>

<span data-ttu-id="88af4-102">WS-Reliable Messaging 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-102">Defines setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="88af4-103">이 요소가 사용자 지정 바인딩에 추가되면 그 결과로 만들어지는 채널에서 EOD(Exactly-Once Delivery) 보증을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-103">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<reliableSession>**  
  
## <a name="syntax"></a><span data-ttu-id="88af4-104">구문</span><span class="sxs-lookup"><span data-stu-id="88af4-104">Syntax</span></span>  
  
```xml  
<reliableSession acknowledgementInterval="TimeSpan"
                 flowControlEnabled="Boolean"
                 inactivityTimeout="TimeSpan"
                 maxPendingChannels="Integer"
                 maxRetryCount="Integer"
                 maxTransferWindowSize="Integer"
                 reliableMessagingVersion="Default/WSReliableMessagingFebruary2005/WSReliableMessaging11"
                 ordered="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88af4-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="88af4-105">Attributes and Elements</span></span>  

 <span data-ttu-id="88af4-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88af4-107">특성</span><span class="sxs-lookup"><span data-stu-id="88af4-107">Attributes</span></span>  
  
|<span data-ttu-id="88af4-108">attribute</span><span class="sxs-lookup"><span data-stu-id="88af4-108">Attribute</span></span>|<span data-ttu-id="88af4-109">설명</span><span class="sxs-lookup"><span data-stu-id="88af4-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="88af4-110">acknowledgementInterval</span><span class="sxs-lookup"><span data-stu-id="88af4-110">acknowledgementInterval</span></span>|<span data-ttu-id="88af4-111">채널이 해당 시점까지 받은 메시지에 대한 승인을 보내기 위해 대기하는 최대 시간 간격이 포함된 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-111">A <xref:System.TimeSpan> that contains the maximum time interval the channel is going to wait to send an acknowledgment for messages received up to that point.</span></span> <span data-ttu-id="88af4-112">기본값은 00:00:0.2입니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-112">The default is 00:00:0.2.</span></span>|  
|<span data-ttu-id="88af4-113">flowControlEnabled</span><span class="sxs-lookup"><span data-stu-id="88af4-113">flowControlEnabled</span></span>|<span data-ttu-id="88af4-114">WS-Reliable Messaging에 대한 Microsoft 고유의 흐름 제어 구현인 고급 흐름 제어를 활성화할지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-114">A Boolean value that indicates whether advanced flow control, a Microsoft-specific implementation of flow control for WS-Reliable messaging, is activated.</span></span> <span data-ttu-id="88af4-115">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-115">The default is `true`.</span></span>|  
|<span data-ttu-id="88af4-116">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="88af4-116">inactivityTimeout</span></span>|<span data-ttu-id="88af4-117">통신 상대방이 메시지를 보내지 않아도 채널에서 오류가 발생하지 않는 최대 기간을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-117">A <xref:System.TimeSpan> that specifies the maximum duration that the channel is going to allow the other communication party not to send any messages, before faulting the channel.</span></span> <span data-ttu-id="88af4-118">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-118">The default is 00:10:00.</span></span><br /><br /> <span data-ttu-id="88af4-119">채널에서는 애플리케이션 또는 인프라 메시지를 받는 작업이 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-119">Activity on a channel is defined as receiving an application or infrastructure messages.</span></span> <span data-ttu-id="88af4-120">이 속성은 비활성 세션을 유지하는 최대 시간을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-120">This property controls the maximum amount of time to keep an inactive session alive.</span></span> <span data-ttu-id="88af4-121">아무런 작업 없이 이 시간이 초과되면 인프라에서 해당 세션을 중단하며 채널에 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-121">If longer time passes with no activity, the session is aborted by the infrastructure and the channel faults.</span></span> <span data-ttu-id="88af4-122">**참고:**  응용 프로그램에서 정기적으로 메시지를 전송 하 여 연결을 유지할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-122">**Note:**  It is not necessary for the application to periodically send messages to keep the connection alive.</span></span>|  
|<span data-ttu-id="88af4-123">maxPendingChannels</span><span class="sxs-lookup"><span data-stu-id="88af4-123">maxPendingChannels</span></span>|<span data-ttu-id="88af4-124">수신기에서 수락 대기할 수 있는 최대 채널 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-124">An integer that specifies the maximum number of channels that can wait on the listener to be accepted.</span></span> <span data-ttu-id="88af4-125">이 값은 1 이상 16384 이하여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-125">This value should be between 1 to 16384 inclusive.</span></span> <span data-ttu-id="88af4-126">기본값은 4입니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-126">The default is 4.</span></span><br /><br /> <span data-ttu-id="88af4-127">수락 대기 중인 채널은 보류됩니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-127">Channels are pending when they are waiting to be accepted.</span></span> <span data-ttu-id="88af4-128">최대 채널 수에 도달하면 채널이 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-128">Once that limit is reached, no channels are created.</span></span> <span data-ttu-id="88af4-129">대신 대기 중인 채널을 수락함으로써 채널 수가 줄어들 때까지 대기 중 모드를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-129">Rather, they are put in pending mode until this number goes down (by accepting pending channels).</span></span> <span data-ttu-id="88af4-130">이것은 팩터리당 제한입니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-130">This is a per-factory limit.</span></span><br /><br /> <span data-ttu-id="88af4-131">임계값에 도달하여 원격 애플리케이션이 신뢰할 수 있는 새 세션을 설정하려고 하면 요청이 거부되고 열기 작업에 이 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-131">When the threshold is reached and a remote application tries to establish a new reliable session, the request is denied and the open operation that prompted this faults.</span></span> <span data-ttu-id="88af4-132">이러한 제한은 보류 중인 보내는 채널 수에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-132">This limit does not apply to the number of pending outgoing channels.</span></span>|  
|<span data-ttu-id="88af4-133">maxRetryCount</span><span class="sxs-lookup"><span data-stu-id="88af4-133">maxRetryCount</span></span>|<span data-ttu-id="88af4-134">신뢰할 수 있는 채널이 기본 채널에서 Send를 호출하여 아직 승인을 받지 않은 메시지를 다시 전송하기 위해 시도할 수 있는 최대 횟수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-134">An integer that specifies the maximum number of times a reliable channel attempts to retransmit a message it has not received an acknowledgment for, by calling Send on its underlying channel.</span></span><br /><br /> <span data-ttu-id="88af4-135">이 값은 0보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-135">This value should be greater than zero.</span></span> <span data-ttu-id="88af4-136">기본값은 8입니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-136">The default is 8.</span></span><br /><br /> <span data-ttu-id="88af4-137">이 값은 0보다 큰 정수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-137">This value should be an integer greater than zero.</span></span> <span data-ttu-id="88af4-138">마지막 재전송 이후 승인을 받지 못한 경우 채널에 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-138">If an acknowledgment is not received after the last retransmission, the channel faults.</span></span><br /><br /> <span data-ttu-id="88af4-139">받는 사람이 메시지 배달을 승인한 경우 전송 되는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-139">A message is considered to be transferred if its delivery at the recipient has been acknowledged by the recipient.</span></span><br /><br /> <span data-ttu-id="88af4-140">전송 된 메시지의 일정 시간 내에 승인이 수신 되지 않은 경우 인프라에서 자동으로 메시지를 재전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-140">If an acknowledgment has not been received within a certain amount of time for a message that has been transmitted, the infrastructure automatically retransmits the message.</span></span> <span data-ttu-id="88af4-141">인프라는 이 속성에 지정된 횟수만큼 메시지를 다시 보내려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-141">The infrastructure tries to resend the message for at most the number of times specified by this property.</span></span> <span data-ttu-id="88af4-142">마지막 재전송 이후 승인을 받지 못한 경우 채널에 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-142">If an acknowledgment is not received after the last retransmission, the channel faults.</span></span><br /><br /> <span data-ttu-id="88af4-143">인프라는 지수 백오프 알고리즘을 사용하여 계산된 평균 라운드트립 시간에 따라 재전송 시간을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-143">The infrastructure uses an exponential back-off algorithm to determine when to retransmit, based on a computed average round-trip time.</span></span> <span data-ttu-id="88af4-144">처음에 시간은 재전송 1초 전에 시작되고 재전송 시도마다 두 배씩 지연되어, 결과적으로 첫 번째 전송 시도와 마지막 전송 시도 간에 약 8.5분이 지나게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-144">The time initially starts at 1 second before retransmission and doubling the delay with every attempt, which results in approximately 8.5 minutes passing between the first transmission attempt and the last retransmission attempt.</span></span> <span data-ttu-id="88af4-145">첫 번째 재전송 시도는 계산된 라운드트립 시간에 따라 조정되고 결과적으로 재전송 시도에 따라 늘어나는 시간이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-145">The time for the first retransmission attempt is adjusted according to the calculated round-trip time and the resulting stretch of time that those attempts take varies accordingly.</span></span> <span data-ttu-id="88af4-146">따라서 재전송 시간을 다양한 네트워크 조건에 맞게 동적으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-146">This allows the retransmission time to dynamically adapt to varying network conditions.</span></span>|  
|<span data-ttu-id="88af4-147">maxTransferWindowSize</span><span class="sxs-lookup"><span data-stu-id="88af4-147">maxTransferWindowSize</span></span>|<span data-ttu-id="88af4-148">버퍼의 최대 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-148">An integer that specifies the maximum size of the buffer.</span></span> <span data-ttu-id="88af4-149">유효한 값은 1부터 4096까지입니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-149">Valid values are from 1 to 4096 inclusive.</span></span><br /><br /> <span data-ttu-id="88af4-150">클라이언트에서 이 특성은 수신자가 승인하지 않은 메시지를 저장하기 위해 신뢰할 수 있는 채널에서 사용하는 최대 버퍼 크기를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-150">On the client, this attribute defines the maximum size of the buffer used by a reliable channel to hold messages not yet acknowledged by the receiver.</span></span> <span data-ttu-id="88af4-151">할당량 단위는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-151">The unit of the quota is a message.</span></span> <span data-ttu-id="88af4-152">버퍼가 꽉 차면 더 이상의 보내기 작업은 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-152">If the buffer is full, further SEND operations are blocked.</span></span><br /><br /> <span data-ttu-id="88af4-153">수신자에서 이 특성은 애플리케이션으로 발송되지 않은 들어오는 메시지를 저장하기 위해 채널에서 사용하는 최대 버퍼 크기를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-153">On the receiver, this attribute defines the maximum size of the buffer used by the channel to store incoming messages not yet dispatched to the application.</span></span> <span data-ttu-id="88af4-154">버퍼가 꽉 차면 그 이상의 메시지는 수신자에 의해 삭제되고 클라이언트가 다시 전송해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-154">If the buffer is full, further messages are silently dropped by the receiver and require retransmission by the client.</span></span>|  
|<span data-ttu-id="88af4-155">ordered</span><span class="sxs-lookup"><span data-stu-id="88af4-155">ordered</span></span>|<span data-ttu-id="88af4-156">전송된 순서대로 메시지 도착을 보장할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-156">A Boolean that specifies whether messages are guaranteed to arrive in the order they were sent.</span></span> <span data-ttu-id="88af4-157">이 설정이 `false`일 경우 메시지가 순서와 관계없이 도착할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-157">If this setting is `false`, messages can arrive out of order.</span></span> <span data-ttu-id="88af4-158">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-158">The default is `true`.</span></span>|  
|<span data-ttu-id="88af4-159">reliableMessagingVersion</span><span class="sxs-lookup"><span data-stu-id="88af4-159">reliableMessagingVersion</span></span>|<span data-ttu-id="88af4-160">사용할 WS-ReliableMessaging 버전을 지정하는 <xref:System.ServiceModel.ReliableMessagingVersion>의 유효한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-160">A valid value from <xref:System.ServiceModel.ReliableMessagingVersion> that specifies the WS-ReliableMessaging version to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88af4-161">자식 요소</span><span class="sxs-lookup"><span data-stu-id="88af4-161">Child Elements</span></span>  

 <span data-ttu-id="88af4-162">없음</span><span class="sxs-lookup"><span data-stu-id="88af4-162">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="88af4-163">부모 요소</span><span class="sxs-lookup"><span data-stu-id="88af4-163">Parent Elements</span></span>  
  
|<span data-ttu-id="88af4-164">요소</span><span class="sxs-lookup"><span data-stu-id="88af4-164">Element</span></span>|<span data-ttu-id="88af4-165">설명</span><span class="sxs-lookup"><span data-stu-id="88af4-165">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="88af4-166">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-166">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88af4-167">설명</span><span class="sxs-lookup"><span data-stu-id="88af4-167">Remarks</span></span>  

 <span data-ttu-id="88af4-168">신뢰할 수 있는 세션은 신뢰할 수 있는 메시징 및 세션 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-168">Reliable sessions provide features for reliable messaging and sessions.</span></span> <span data-ttu-id="88af4-169">신뢰할 수 있는 메시징 기능은 실패 시 통신을 다시 시도하고 메시지 차례로 도착과 같은 배달 보증을 지정할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-169">Reliable messaging retries communication on failure and allows delivery assurances such as in-order arrival of messages to be specified.</span></span> <span data-ttu-id="88af4-170">세션은 호출 간에 클라이언트의 상태를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-170">Sessions maintain state for clients between calls.</span></span> <span data-ttu-id="88af4-171">이 요소는 메시지를 순서대로 배달하는 기능을 선택적으로도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-171">This element also optionally provides ordered message delivery.</span></span> <span data-ttu-id="88af4-172">이 구현 된 세션은 SOAP 및 전송 중개자를 통과할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-172">This implemented session can cross SOAP and transport intermediaries.</span></span>  
  
 <span data-ttu-id="88af4-173">각 바인딩 요소는 메시지를 보내거나 받을 때의 처리 단계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-173">Each binding element represents a processing step when sending or receiving messages.</span></span> <span data-ttu-id="88af4-174">런타임에 바인딩 요소는 메시지를 보내고 받는 데 필요한 송신 및 들어오는 채널 스택을 빌드하는 데 필요한 채널 팩터리 및 수신기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-174">At runtime, binding elements create the channel factories and listeners that are necessary to build outgoing and incoming channel stacks required to send and receive messages.</span></span> <span data-ttu-id="88af4-175">는 `reliableSession` 끝점 간에 신뢰할 수 있는 세션을 설정 하 고이 세션의 동작을 구성할 수 있는 선택적 계층을 스택에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-175">The `reliableSession` provides an optional layer in the stack that can establish a reliable session between endpoints and configure the behavior of this session.</span></span>  
  
 <span data-ttu-id="88af4-176">자세한 내용은 [신뢰할 수 있는 세션](../../../wcf/feature-details/reliable-sessions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="88af4-176">For more information, see [Reliable Sessions](../../../wcf/feature-details/reliable-sessions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="88af4-177">예제</span><span class="sxs-lookup"><span data-stu-id="88af4-177">Example</span></span>  

 <span data-ttu-id="88af4-178">다음 예제에서는 다양한 전송 및 메시지 인코딩 요소, 특히 신뢰할 수 있는 세션 사용 등을 통해 사용자 지정 바인딩을 구성하는 방법을 보여 줍니다. 이렇게 하면 클라이언트 상태가 유지되며 차례로 배달 보증이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-178">The following example demonstrates how to configure a custom binding with various transport and message encoding elements, especially enabling reliable sessions, which maintains client state and specifies in-order delivery assurances.</span></span> <span data-ttu-id="88af4-179">이 기능은 클라이언트 및 서비스의 애플리케이션 구성 파일에서 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-179">This feature is configured in the application configuration files for the client and service.</span></span> <span data-ttu-id="88af4-180">예제에서는 서비스 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="88af4-180">The example show the service configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by host: http://localhost/servicemodelsamples/service.svc -->
        <!-- specify customBinding binding and a binding configuration to use -->
        <endpoint address=""
                  binding="customBinding"
                  bindingConfiguration="Binding1"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <!-- custom binding configuration - configures HTTP transport, reliable sessions -->
    <bindings>
      <customBinding>
        <binding name="Binding1">
          <reliableSession />
          <security authenticationMode="SecureConversation"
                    requireSecurityContextCancellation="true">
          </security>
          <compositeDuplex />
          <oneWay />
          <textMessageEncoding messageVersion="Soap12WSAddressing10"
                               writeEncoding="utf-8" />
          <httpTransport authenticationScheme="Anonymous"
                         bypassProxyOnLocal="false"
                         hostNameComparisonMode="StrongWildcard"
                         proxyAuthenticationScheme="Anonymous"
                         realm=""
                         useDefaultWebProxy="true" />
        </binding>
      </customBinding>
    </bindings>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="88af4-181">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88af4-181">See also</span></span>

- <xref:System.ServiceModel.Configuration.ReliableSessionElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
- [<span data-ttu-id="88af4-182">신뢰할 수 있는 세션</span><span class="sxs-lookup"><span data-stu-id="88af4-182">Reliable Sessions</span></span>](../../../wcf/feature-details/reliable-sessions.md)
- [<span data-ttu-id="88af4-183">바인딩</span><span class="sxs-lookup"><span data-stu-id="88af4-183">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="88af4-184">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="88af4-184">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="88af4-185">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="88af4-185">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
