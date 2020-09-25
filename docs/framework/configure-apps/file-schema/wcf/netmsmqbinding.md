---
title: <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: a68b44d7-7799-43a3-9e63-f07c782810a6
ms.openlocfilehash: 7dca85e4095e581c262611f0120ffb85e2174fee
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204582"
---
# \<netMsmqBinding>

<span data-ttu-id="f03d1-101">시스템 간 통신에 적합한 대기 중인 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-101">Defines a queued binding suitable for cross-machine communication.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netMsmqBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="f03d1-102">구문</span><span class="sxs-lookup"><span data-stu-id="f03d1-102">Syntax</span></span>  
  
```xml  
<netMsmqBinding>
  <binding closeTimeout="TimeSpan"
           customDeadLetterQueue="Uri"
           deadLetterQueue="Uri"
           durable="Boolean"
           exactlyOnce="Boolean"
           maxBufferPoolSize="Integer"
           maxReceivedMessageSize="Integer"
           maxRetryCycles="Integer"
           name="String"
           openTimeout="TimeSpan"
           poisonMessageHandling="Disabled/EnabledIfSupported"
           queueTransferProtocol="Native/Srmp/SrmpSecure"
           receiveErrorHandling="Drop/Fault/Move/Reject"
           receiveTimeout="TimeSpan"
           receiveRetryCount="Integer"
           rejectAfterLastRetry="Boolean"
           retryCycleDelay="TimeSpan"
           sendTimeout="TimeSpan"
           timeToLive="TimeSpan"
           useActiveDirectory="Boolean"
           useMsmqTracing="Boolean"
           useSourceJournal="Boolean">
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="None/Windows/UserName/Certificate/InfoCard" />
      <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netMsmqBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f03d1-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f03d1-103">Attributes and Elements</span></span>  

 <span data-ttu-id="f03d1-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f03d1-105">특성</span><span class="sxs-lookup"><span data-stu-id="f03d1-105">Attributes</span></span>  
  
|<span data-ttu-id="f03d1-106">attribute</span><span class="sxs-lookup"><span data-stu-id="f03d1-106">Attribute</span></span>|<span data-ttu-id="f03d1-107">설명</span><span class="sxs-lookup"><span data-stu-id="f03d1-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="f03d1-108">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-108">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="f03d1-109">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-109">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f03d1-110">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-110">The default is 00:01:00.</span></span>|  
|`customDeadLetterQueue`|<span data-ttu-id="f03d1-111">애플리케이션별 배달 못 한 편지 큐의 위치를 포함하는 URI입니다. 이 큐에는 만료되었거나 전송 또는 배달하지 못한 메시지가 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-111">A URI that contains the location of the per-application dead letter queue, where messages that have expired or that have failed transfer or delivery are placed.</span></span><br /><br /> <span data-ttu-id="f03d1-112">배달 못 한 편지 큐는 송신 애플리케이션의 큐 관리자에서 관리하는 큐로, 배달하지 못한 만료된 메시지가 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-112">The dead letter queue is a queue on the queue manager of the sending application for expired messages that have failed to be delivered.</span></span><br /><br /> <span data-ttu-id="f03d1-113"><xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A>로 지정된 URI는 net.msmq 체계를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-113">The URI that is specified by <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> must use the net.msmq scheme.</span></span>|  
|`deadLetterQueue`|<span data-ttu-id="f03d1-114">배달 못 한 편지 큐가 있는 경우 큐의 형식을 지정하는 <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-114">A <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A> value specifying which type of dead-letter queue to use, if any.</span></span><br /><br /> <span data-ttu-id="f03d1-115">배달 못 한 편지 큐는 애플리케이션에 배달하지 못한 메시지가 전송되는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-115">A dead-letter queue is the place where messages that have failed to be delivered to the application will be transferred.</span></span><br /><br /> <span data-ttu-id="f03d1-116">`exactlyOnce` 보증을 요구하는 메시지(`exactlyOnce` 특성이 `true`로 설정)의 경우 이 특성은 기본적으로 MSMQ의 시스템 전체 트랜잭션 배달 못 한 편지 큐로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-116">For messages that require `exactlyOnce` assurance (that is, the `exactlyOnce` attribute is set to `true`), this attribute defaults to the system-wide transactional dead-letter queue in MSMQ.</span></span><br /><br /> <span data-ttu-id="f03d1-117">보증이 필요하지 않은 메시지의 경우 이 특성은 기본적으로 `null`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-117">For messages that require no assurances, this attribute defaults to `null`.</span></span>|  
|`durable`|<span data-ttu-id="f03d1-118">큐의 메시지가 지속적인지 또는 일시적인지를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-118">A Boolean value that indicates whether the message is durable or volatile in the queue.</span></span> <span data-ttu-id="f03d1-119">지속적 메시지는 큐 관리자가 중단되더라도 남아 있지만, 일시적 메시지는 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-119">A durable message survives a queue manager crash, while a volatile message does not.</span></span> <span data-ttu-id="f03d1-120">애플리케이션에서 더 낮은 대기 시간을 요구하며 어느 정도의 메시지 손실을 허용할 수 있다면 일시적 메시지가 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-120">Volatile messages are useful when applications require lower latency and can tolerate occasional lost messages.</span></span> <span data-ttu-id="f03d1-121">`exactlyOnce` 특성을 `true`로 설정하면 메시지는 지속적이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-121">If the `exactlyOnce` attribute is set to `true`, the messages must be durable.</span></span> <span data-ttu-id="f03d1-122">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-122">The default is `true`.</span></span>|  
|`exactlyOnce`|<span data-ttu-id="f03d1-123">이 바인딩에서 처리하는 각 메시지가 한 번만 배달되는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-123">A Boolean value that indicates whether each message processed by this binding is delivered only once.</span></span> <span data-ttu-id="f03d1-124">배달이 실패하면 발신자는 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-124">The sender will then be notified of delivery failures.</span></span> <span data-ttu-id="f03d1-125">`durable`이 `false`이면 이 특성은 무시되고 배달 보증 없이 메시지가 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-125">When `durable` is `false`, this attribute is ignored and messages are transferred without delivery assurance.</span></span> <span data-ttu-id="f03d1-126">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-126">The default is `true`.</span></span> <span data-ttu-id="f03d1-127">자세한 내용은 <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f03d1-127">For more information, see <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A>.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="f03d1-128">이 바인딩의 최대 버퍼 풀 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-128">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="f03d1-129">기본값은 8입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-129">The default is 8.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="f03d1-130">이 바인딩에 의해 처리되는 최대 메시지 크기(헤더 포함)(바이트)를 정의하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-130">A positive integer that defines the maximum message size, in bytes, including headers, that is processed by this binding.</span></span> <span data-ttu-id="f03d1-131">이 한도를 초과하는 메시지를 보낸 사람은 SOAP 오류를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-131">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="f03d1-132">수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-132">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="f03d1-133">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-133">The default is 65536.</span></span> <span data-ttu-id="f03d1-134">이 메시지 크기 제한은 DoS(서비스 거부) 공격에 대한 노출을 막기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-134">This bound on message size is intended to limit exposure to Denial of Service (DoS) attacks.</span></span>|  
|`maxRetryCycles`|<span data-ttu-id="f03d1-135">포이즌 메시지 검색 기능에 사용되는 재시도 주기 수를 나타내는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-135">An integer that indicates the number of retry cycles used by the poison-message detection feature.</span></span> <span data-ttu-id="f03d1-136">모든 주기의 모든 배달 시도가 실패할 경우 메시지는 포이즌 메시지가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-136">A message becomes a poison message when it fails all delivery attempts of all cycles.</span></span> <span data-ttu-id="f03d1-137">기본값은 3입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-137">The default is 3.</span></span> <span data-ttu-id="f03d1-138">자세한 내용은 <xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f03d1-138">For more information, see <xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A>.</span></span>|  
|`name`|<span data-ttu-id="f03d1-139">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-139">Required attribute.</span></span> <span data-ttu-id="f03d1-140">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-140">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="f03d1-141">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-141">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="f03d1-142">.NET Framework 4부터 바인딩과 동작은 이름을 가질 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-142">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="f03d1-143">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f03d1-143">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="f03d1-144">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-144">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="f03d1-145">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-145">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f03d1-146">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-146">The default is 00:01:00.</span></span>|  
|`QueueTransferProtocol`|<span data-ttu-id="f03d1-147">이 바인딩에서 사용하는 대기 중인 통신 채널 전송을 지정하는 유효한 <xref:System.ServiceModel.QueueTransferProtocol> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-147">A valid <xref:System.ServiceModel.QueueTransferProtocol> value that specifies the queued communication channel transport that this binding uses.</span></span> <span data-ttu-id="f03d1-148">SRMP(SOAP Reliable Messaging Protocol) 사용 시 MSMQ는 Active Directory 주소 지정을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-148">MSMQ does not support Active Directory addressing when using SOAP Reliable Messaging Protocol.</span></span> <span data-ttu-id="f03d1-149">따라서이 특성을로 설정 `Srmp` 하거나 `Srmps` `useActiveDirectory` 특성이로 설정 된 경우에는이 특성을로 설정 하면 안 됩니다 `true` .</span><span class="sxs-lookup"><span data-stu-id="f03d1-149">Therefore, you should not set this attribute to `Srmp` or `Srmps` when the `useActiveDirectory` attribute is set to `true`.</span></span>|  
|`receiveErrorHandling`|<span data-ttu-id="f03d1-150">포이즌 메시지 및 디스패치할 수 없는 메시지의 처리 방법을 지정하는 <xref:System.ServiceModel.ReceiveErrorHandling> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-150">A <xref:System.ServiceModel.ReceiveErrorHandling> value that specifies how poison and nondispatchable messages are handled.</span></span>|  
|`receiveRetryCount`|<span data-ttu-id="f03d1-151">메시지를 재시도 큐로 전송하기 전에 큐 관리자가 메시지 전송을 시도하는 최대 횟수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-151">An integer that specifies the maximum number of times the queue manager should attempt to send a message before transferring it to the retry queue.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="f03d1-152">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-152">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="f03d1-153">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-153">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f03d1-154">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-154">The default is 00:10:00.</span></span>|  
|`retryCycleDelay`|<span data-ttu-id="f03d1-155">전달하지 못한 메시지를 즉시 다시 전달하려고 시도할 때 재시도 주기 사이의 지연 시간을 지정하는 TimeSpan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-155">A TimeSpan value that specifies the time delay between retry cycles when attempting to deliver a message that could not be delivered immediately.</span></span> <span data-ttu-id="f03d1-156">실제 대기 시간이 더 길 수 있으므로 이 값은 최소 대기 시간만 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-156">The value defines only the minimum wait time because actual wait time can be longer.</span></span> <span data-ttu-id="f03d1-157">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-157">The default value is 00:10:00.</span></span> <span data-ttu-id="f03d1-158">자세한 내용은 <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f03d1-158">For more information, see <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A>.</span></span>|  
|`sendTimeout`|<span data-ttu-id="f03d1-159">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-159">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="f03d1-160">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-160">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f03d1-161">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-161">The default is 00:01:00.</span></span>|  
|`timeToLive`|<span data-ttu-id="f03d1-162">메시지가 만료되어 배달 못 한 큐에 추가되기 전에 메시지가 유효한 기간을 지정하는 TimeSpan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-162">A TimeSpan value that specifies how long the messages are valid before they are expired and put into the dead-letter queue.</span></span> <span data-ttu-id="f03d1-163">기본값은 1.00:00:00입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-163">The default is 1.00:00:00.</span></span><br /><br /> <span data-ttu-id="f03d1-164">이 특성은 시간을 다투는 메시지가 수신 애플리케이션에서 처리되기 전에 무효화되지 않도록 하기 위해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-164">This attribute is set to ensure that time-sensitive messages do not become stale before they are processed by the receiving applications.</span></span> <span data-ttu-id="f03d1-165">지정된 시간 간격 내에 수신 애플리케이션에서 사용하지 않은 큐의 메시지는 만료된 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-165">A message in a queue that is not consumed by the receiving application within the time interval specified is said to be expired.</span></span> <span data-ttu-id="f03d1-166">만료된 메시지는 배달 못한 편지 큐라는 특수 큐로 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-166">Expired messages are sent to special queue called the dead letter queue.</span></span> <span data-ttu-id="f03d1-167">배달 못 한 편지 큐의 위치는 보증에 따라 `DeadLetterQueue` 특성으로 설정되거나 해당 기본값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-167">The location of the dead letter queue is set with the `DeadLetterQueue` attribute or to the appropriate default, based on assurances.</span></span>|  
|`usingActiveDirectory`|<span data-ttu-id="f03d1-168">Active Directory를 사용하여 큐 주소를 변환해야 하는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-168">A Boolean value that specifies if queue addresses should be converted using Active Directory.</span></span><br /><br /> <span data-ttu-id="f03d1-169">MSMQ 큐 주소는 경로 이름이나 직접 형식 이름으로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-169">MSMQ queue addresses can consist of path names or direct format names.</span></span> <span data-ttu-id="f03d1-170">직접 형식 이름을 사용할 경우 MSMQ는 DNS, NetBIOS 또는 IP를 사용하여 컴퓨터 이름을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-170">With a direct format name, MSMQ resolves the computer name using DNS, NetBIOS or IP.</span></span> <span data-ttu-id="f03d1-171">경로 이름을 사용할 경우 MSMQ는 Active Directory를 사용하여 컴퓨터 이름을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-171">With a path name, MSMQ resolves the computer name using Active Directory.</span></span><br /><br /> <span data-ttu-id="f03d1-172">기본적으로 Windows Communication Foundation (WCF) 대기 중인 전송은 메시지 큐의 URI를 직접 형식 이름으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-172">By default, Windows Communication Foundation (WCF) queued transport converts the URI of a message queue to a direct format name.</span></span> <span data-ttu-id="f03d1-173">`UseActiveDirectory` 속성을 true로 설정하면 대기 중 전송이 DNS, NetBIOS 또는 IP 대신 Active Directory를 사용하여 컴퓨터 이름을 확인하도록 애플리케이션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-173">By setting the `UseActiveDirectory` property to true, an application can specify that the queued transport should resolve the computer name using Active Directory rather than DNS, NetBIOS, or IP.</span></span>|  
|`useMsmqTracing`|<span data-ttu-id="f03d1-174">이 바인딩이 처리하는 메시지를 추적할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-174">A Boolean value that specifies whether messages processed by this binding should be traced.</span></span> <span data-ttu-id="f03d1-175">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-175">The default is `false`.</span></span> <span data-ttu-id="f03d1-176">추적 기능을 사용하면 메시지가 메시지 큐 컴퓨터에 들어가거나 나올 때마다 보고서 메시지가 만들어진 후 보고서 큐로 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-176">When tracing is enabled, report messages are created and sent to the report queue each time the message leaves or arrives at a Message Queuing computer.</span></span>|  
|`useSourceJournal`|<span data-ttu-id="f03d1-177">이 바인딩에서 처리하는 메시지의 복사본을 소스 업무 일지에 저장할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-177">A Boolean value that specifies copies of messages processed by this binding should be stored in the source journal.</span></span> <span data-ttu-id="f03d1-178">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-178">The default is `false`.</span></span><br /><br /> <span data-ttu-id="f03d1-179">대기 중 애플리케이션에서 컴퓨터의 나가는 큐를 떠난 메시지의 레코드를 보존해야 할 경우 메시지를 업무 일지 큐에 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-179">Queued applications that want to keep a record of messages that have left the computer's outgoing queue can copy the messages to a journal queue.</span></span> <span data-ttu-id="f03d1-180">메시지가 보내는 큐를 떠난 후 대상 컴퓨터에 수신되었다는 승인을 받으면 해당 메시지의 복사본이 보낸 컴퓨터의 시스템 업무 일지 큐에 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-180">Once a message leaves the outgoing queue and an acknowledgment is received that the message was received on the destination computer, a copy of the message is kept in the sending computer's system journal queue.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f03d1-181">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f03d1-181">Child Elements</span></span>  
  
|<span data-ttu-id="f03d1-182">요소</span><span class="sxs-lookup"><span data-stu-id="f03d1-182">Element</span></span>|<span data-ttu-id="f03d1-183">설명</span><span class="sxs-lookup"><span data-stu-id="f03d1-183">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="f03d1-184">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-184">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="f03d1-185">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-185">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<security>](security-of-netmsmqbinding.md)|<span data-ttu-id="f03d1-186">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-186">Defines the security settings for the binding.</span></span> <span data-ttu-id="f03d1-187">이 요소는 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-187">This element is of type <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f03d1-188">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f03d1-188">Parent Elements</span></span>  
  
|<span data-ttu-id="f03d1-189">요소</span><span class="sxs-lookup"><span data-stu-id="f03d1-189">Element</span></span>|<span data-ttu-id="f03d1-190">설명</span><span class="sxs-lookup"><span data-stu-id="f03d1-190">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="f03d1-191">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-191">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f03d1-192">설명</span><span class="sxs-lookup"><span data-stu-id="f03d1-192">Remarks</span></span>  

 <span data-ttu-id="f03d1-193">`netMsmqBinding` 바인딩은 MSMQ(Microsoft Message Queuing)를 전송으로 활용하면서 큐에 대한 지원을 제공하며, 느슨하게 결합된 애플리케이션, 실패 격리, 로드 조정 및 연결이 끊긴 작업을 지원할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f03d1-193">The `netMsmqBinding` binding provides support for queuing by leveraging Microsoft Message Queuing (MSMQ) as a transport and enables support for loosely coupled applications, failure isolation, load leveling and disconnected operations.</span></span> <span data-ttu-id="f03d1-194">이러한 기능에 대 한 설명은 [WCF의 큐](../../../wcf/feature-details/queues-in-wcf.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f03d1-194">For a discussion of these features, see [Queues in WCF](../../../wcf/feature-details/queues-in-wcf.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f03d1-195">예제</span><span class="sxs-lookup"><span data-stu-id="f03d1-195">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <netMsmqBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 deadLetterQueue="net.msmq://localhost/blah"
                 durable="true"
                 exactlyOnce="true"
                 maxReceivedMessageSize="1000"
                 maxRetries="11"
                 maxRetryCycles="12"
                 poisonMessageHandling="Disabled"
                 rejectAfterLastRetry="false"
                 retryCycleDelay="00:05:55"
                 timeToLive="00:11:11"
                 sourceJournal="true"
                 useMsmqTracing="true"
                 useActiveDirectory="true">
          <security>
            <message clientCredentialType="Windows" />
          </security>
        </binding>
      </netMsmqBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="f03d1-196">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f03d1-196">See also</span></span>

- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement>
- [\<binding>](bindings.md)
- [<span data-ttu-id="f03d1-197">바인딩하</span><span class="sxs-lookup"><span data-stu-id="f03d1-197">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f03d1-198">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="f03d1-198">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f03d1-199">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="f03d1-199">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f03d1-200">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="f03d1-200">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
