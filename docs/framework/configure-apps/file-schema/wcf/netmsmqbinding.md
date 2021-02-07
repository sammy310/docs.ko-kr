---
description: 다음에 대해 자세히 알아보세요. <netMsmqBinding>
title: <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: a68b44d7-7799-43a3-9e63-f07c782810a6
ms.openlocfilehash: 2d0e475065b1ed34df895fc289567d678489fbbf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683959"
---
# \<netMsmqBinding>

<span data-ttu-id="9d50c-102">시스템 간 통신에 적합한 대기 중인 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-102">Defines a queued binding suitable for cross-machine communication.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netMsmqBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="9d50c-103">구문</span><span class="sxs-lookup"><span data-stu-id="9d50c-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d50c-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9d50c-104">Attributes and Elements</span></span>  

 <span data-ttu-id="9d50c-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d50c-106">특성</span><span class="sxs-lookup"><span data-stu-id="9d50c-106">Attributes</span></span>  
  
|<span data-ttu-id="9d50c-107">attribute</span><span class="sxs-lookup"><span data-stu-id="9d50c-107">Attribute</span></span>|<span data-ttu-id="9d50c-108">설명</span><span class="sxs-lookup"><span data-stu-id="9d50c-108">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="9d50c-109">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-109">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="9d50c-110">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-110">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9d50c-111">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-111">The default is 00:01:00.</span></span>|  
|`customDeadLetterQueue`|<span data-ttu-id="9d50c-112">애플리케이션별 배달 못 한 편지 큐의 위치를 포함하는 URI입니다. 이 큐에는 만료되었거나 전송 또는 배달하지 못한 메시지가 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-112">A URI that contains the location of the per-application dead letter queue, where messages that have expired or that have failed transfer or delivery are placed.</span></span><br /><br /> <span data-ttu-id="9d50c-113">배달 못 한 편지 큐는 송신 애플리케이션의 큐 관리자에서 관리하는 큐로, 배달하지 못한 만료된 메시지가 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-113">The dead letter queue is a queue on the queue manager of the sending application for expired messages that have failed to be delivered.</span></span><br /><br /> <span data-ttu-id="9d50c-114"><xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A>로 지정된 URI는 net.msmq 체계를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-114">The URI that is specified by <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> must use the net.msmq scheme.</span></span>|  
|`deadLetterQueue`|<span data-ttu-id="9d50c-115">배달 못 한 편지 큐가 있는 경우 큐의 형식을 지정하는 <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-115">A <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A> value specifying which type of dead-letter queue to use, if any.</span></span><br /><br /> <span data-ttu-id="9d50c-116">배달 못 한 편지 큐는 애플리케이션에 배달하지 못한 메시지가 전송되는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-116">A dead-letter queue is the place where messages that have failed to be delivered to the application will be transferred.</span></span><br /><br /> <span data-ttu-id="9d50c-117">`exactlyOnce` 보증을 요구하는 메시지(`exactlyOnce` 특성이 `true`로 설정)의 경우 이 특성은 기본적으로 MSMQ의 시스템 전체 트랜잭션 배달 못 한 편지 큐로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-117">For messages that require `exactlyOnce` assurance (that is, the `exactlyOnce` attribute is set to `true`), this attribute defaults to the system-wide transactional dead-letter queue in MSMQ.</span></span><br /><br /> <span data-ttu-id="9d50c-118">보증이 필요하지 않은 메시지의 경우 이 특성은 기본적으로 `null`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-118">For messages that require no assurances, this attribute defaults to `null`.</span></span>|  
|`durable`|<span data-ttu-id="9d50c-119">큐의 메시지가 지속적인지 또는 일시적인지를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-119">A Boolean value that indicates whether the message is durable or volatile in the queue.</span></span> <span data-ttu-id="9d50c-120">지속적 메시지는 큐 관리자가 중단되더라도 남아 있지만, 일시적 메시지는 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-120">A durable message survives a queue manager crash, while a volatile message does not.</span></span> <span data-ttu-id="9d50c-121">애플리케이션에서 더 낮은 대기 시간을 요구하며 어느 정도의 메시지 손실을 허용할 수 있다면 일시적 메시지가 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-121">Volatile messages are useful when applications require lower latency and can tolerate occasional lost messages.</span></span> <span data-ttu-id="9d50c-122">`exactlyOnce` 특성을 `true`로 설정하면 메시지는 지속적이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-122">If the `exactlyOnce` attribute is set to `true`, the messages must be durable.</span></span> <span data-ttu-id="9d50c-123">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-123">The default is `true`.</span></span>|  
|`exactlyOnce`|<span data-ttu-id="9d50c-124">이 바인딩에서 처리하는 각 메시지가 한 번만 배달되는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-124">A Boolean value that indicates whether each message processed by this binding is delivered only once.</span></span> <span data-ttu-id="9d50c-125">배달이 실패하면 발신자는 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-125">The sender will then be notified of delivery failures.</span></span> <span data-ttu-id="9d50c-126">`durable`이 `false`이면 이 특성은 무시되고 배달 보증 없이 메시지가 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-126">When `durable` is `false`, this attribute is ignored and messages are transferred without delivery assurance.</span></span> <span data-ttu-id="9d50c-127">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-127">The default is `true`.</span></span> <span data-ttu-id="9d50c-128">자세한 내용은 <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d50c-128">For more information, see <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A>.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="9d50c-129">이 바인딩의 최대 버퍼 풀 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-129">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="9d50c-130">기본값은 8입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-130">The default is 8.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="9d50c-131">이 바인딩에 의해 처리되는 최대 메시지 크기(헤더 포함)(바이트)를 정의하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-131">A positive integer that defines the maximum message size, in bytes, including headers, that is processed by this binding.</span></span> <span data-ttu-id="9d50c-132">이 한도를 초과하는 메시지를 보낸 사람은 SOAP 오류를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-132">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="9d50c-133">수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-133">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="9d50c-134">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-134">The default is 65536.</span></span> <span data-ttu-id="9d50c-135">이 메시지 크기 제한은 DoS(서비스 거부) 공격에 대한 노출을 막기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-135">This bound on message size is intended to limit exposure to Denial of Service (DoS) attacks.</span></span>|  
|`maxRetryCycles`|<span data-ttu-id="9d50c-136">포이즌 메시지 검색 기능에 사용되는 재시도 주기 수를 나타내는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-136">An integer that indicates the number of retry cycles used by the poison-message detection feature.</span></span> <span data-ttu-id="9d50c-137">모든 주기의 모든 배달 시도가 실패할 경우 메시지는 포이즌 메시지가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-137">A message becomes a poison message when it fails all delivery attempts of all cycles.</span></span> <span data-ttu-id="9d50c-138">기본값은 3입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-138">The default is 3.</span></span> <span data-ttu-id="9d50c-139">자세한 내용은 <xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d50c-139">For more information, see <xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A>.</span></span>|  
|`name`|<span data-ttu-id="9d50c-140">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-140">Required attribute.</span></span> <span data-ttu-id="9d50c-141">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-141">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="9d50c-142">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-142">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="9d50c-143">.NET Framework 4부터 바인딩과 동작은 이름을 가질 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-143">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="9d50c-144">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d50c-144">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="9d50c-145">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="9d50c-146">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9d50c-147">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-147">The default is 00:01:00.</span></span>|  
|`QueueTransferProtocol`|<span data-ttu-id="9d50c-148">이 바인딩에서 사용하는 대기 중인 통신 채널 전송을 지정하는 유효한 <xref:System.ServiceModel.QueueTransferProtocol> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-148">A valid <xref:System.ServiceModel.QueueTransferProtocol> value that specifies the queued communication channel transport that this binding uses.</span></span> <span data-ttu-id="9d50c-149">SRMP(SOAP Reliable Messaging Protocol) 사용 시 MSMQ는 Active Directory 주소 지정을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-149">MSMQ does not support Active Directory addressing when using SOAP Reliable Messaging Protocol.</span></span> <span data-ttu-id="9d50c-150">따라서이 특성을로 설정 `Srmp` 하거나 `Srmps` `useActiveDirectory` 특성이로 설정 된 경우에는이 특성을로 설정 하면 안 됩니다 `true` .</span><span class="sxs-lookup"><span data-stu-id="9d50c-150">Therefore, you should not set this attribute to `Srmp` or `Srmps` when the `useActiveDirectory` attribute is set to `true`.</span></span>|  
|`receiveErrorHandling`|<span data-ttu-id="9d50c-151">포이즌 메시지 및 디스패치할 수 없는 메시지의 처리 방법을 지정하는 <xref:System.ServiceModel.ReceiveErrorHandling> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-151">A <xref:System.ServiceModel.ReceiveErrorHandling> value that specifies how poison and nondispatchable messages are handled.</span></span>|  
|`receiveRetryCount`|<span data-ttu-id="9d50c-152">메시지를 재시도 큐로 전송하기 전에 큐 관리자가 메시지 전송을 시도하는 최대 횟수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-152">An integer that specifies the maximum number of times the queue manager should attempt to send a message before transferring it to the retry queue.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="9d50c-153">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-153">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="9d50c-154">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-154">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9d50c-155">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-155">The default is 00:10:00.</span></span>|  
|`retryCycleDelay`|<span data-ttu-id="9d50c-156">전달하지 못한 메시지를 즉시 다시 전달하려고 시도할 때 재시도 주기 사이의 지연 시간을 지정하는 TimeSpan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-156">A TimeSpan value that specifies the time delay between retry cycles when attempting to deliver a message that could not be delivered immediately.</span></span> <span data-ttu-id="9d50c-157">실제 대기 시간이 더 길 수 있으므로 이 값은 최소 대기 시간만 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-157">The value defines only the minimum wait time because actual wait time can be longer.</span></span> <span data-ttu-id="9d50c-158">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-158">The default value is 00:10:00.</span></span> <span data-ttu-id="9d50c-159">자세한 내용은 <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d50c-159">For more information, see <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A>.</span></span>|  
|`sendTimeout`|<span data-ttu-id="9d50c-160">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-160">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="9d50c-161">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-161">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9d50c-162">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-162">The default is 00:01:00.</span></span>|  
|`timeToLive`|<span data-ttu-id="9d50c-163">메시지가 만료되어 배달 못 한 큐에 추가되기 전에 메시지가 유효한 기간을 지정하는 TimeSpan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-163">A TimeSpan value that specifies how long the messages are valid before they are expired and put into the dead-letter queue.</span></span> <span data-ttu-id="9d50c-164">기본값은 1.00:00:00입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-164">The default is 1.00:00:00.</span></span><br /><br /> <span data-ttu-id="9d50c-165">이 특성은 시간을 다투는 메시지가 수신 애플리케이션에서 처리되기 전에 무효화되지 않도록 하기 위해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-165">This attribute is set to ensure that time-sensitive messages do not become stale before they are processed by the receiving applications.</span></span> <span data-ttu-id="9d50c-166">지정된 시간 간격 내에 수신 애플리케이션에서 사용하지 않은 큐의 메시지는 만료된 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-166">A message in a queue that is not consumed by the receiving application within the time interval specified is said to be expired.</span></span> <span data-ttu-id="9d50c-167">만료된 메시지는 배달 못한 편지 큐라는 특수 큐로 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-167">Expired messages are sent to special queue called the dead letter queue.</span></span> <span data-ttu-id="9d50c-168">배달 못 한 편지 큐의 위치는 보증에 따라 `DeadLetterQueue` 특성으로 설정되거나 해당 기본값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-168">The location of the dead letter queue is set with the `DeadLetterQueue` attribute or to the appropriate default, based on assurances.</span></span>|  
|`usingActiveDirectory`|<span data-ttu-id="9d50c-169">Active Directory를 사용하여 큐 주소를 변환해야 하는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-169">A Boolean value that specifies if queue addresses should be converted using Active Directory.</span></span><br /><br /> <span data-ttu-id="9d50c-170">MSMQ 큐 주소는 경로 이름이나 직접 형식 이름으로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-170">MSMQ queue addresses can consist of path names or direct format names.</span></span> <span data-ttu-id="9d50c-171">직접 형식 이름을 사용할 경우 MSMQ는 DNS, NetBIOS 또는 IP를 사용하여 컴퓨터 이름을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-171">With a direct format name, MSMQ resolves the computer name using DNS, NetBIOS or IP.</span></span> <span data-ttu-id="9d50c-172">경로 이름을 사용할 경우 MSMQ는 Active Directory를 사용하여 컴퓨터 이름을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-172">With a path name, MSMQ resolves the computer name using Active Directory.</span></span><br /><br /> <span data-ttu-id="9d50c-173">기본적으로 Windows Communication Foundation (WCF) 대기 중인 전송은 메시지 큐의 URI를 직접 형식 이름으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-173">By default, Windows Communication Foundation (WCF) queued transport converts the URI of a message queue to a direct format name.</span></span> <span data-ttu-id="9d50c-174">`UseActiveDirectory` 속성을 true로 설정하면 대기 중 전송이 DNS, NetBIOS 또는 IP 대신 Active Directory를 사용하여 컴퓨터 이름을 확인하도록 애플리케이션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-174">By setting the `UseActiveDirectory` property to true, an application can specify that the queued transport should resolve the computer name using Active Directory rather than DNS, NetBIOS, or IP.</span></span>|  
|`useMsmqTracing`|<span data-ttu-id="9d50c-175">이 바인딩이 처리하는 메시지를 추적할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-175">A Boolean value that specifies whether messages processed by this binding should be traced.</span></span> <span data-ttu-id="9d50c-176">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-176">The default is `false`.</span></span> <span data-ttu-id="9d50c-177">추적 기능을 사용하면 메시지가 메시지 큐 컴퓨터에 들어가거나 나올 때마다 보고서 메시지가 만들어진 후 보고서 큐로 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-177">When tracing is enabled, report messages are created and sent to the report queue each time the message leaves or arrives at a Message Queuing computer.</span></span>|  
|`useSourceJournal`|<span data-ttu-id="9d50c-178">이 바인딩에서 처리하는 메시지의 복사본을 소스 업무 일지에 저장할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-178">A Boolean value that specifies copies of messages processed by this binding should be stored in the source journal.</span></span> <span data-ttu-id="9d50c-179">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-179">The default is `false`.</span></span><br /><br /> <span data-ttu-id="9d50c-180">대기 중 애플리케이션에서 컴퓨터의 나가는 큐를 떠난 메시지의 레코드를 보존해야 할 경우 메시지를 업무 일지 큐에 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-180">Queued applications that want to keep a record of messages that have left the computer's outgoing queue can copy the messages to a journal queue.</span></span> <span data-ttu-id="9d50c-181">메시지가 보내는 큐를 떠난 후 대상 컴퓨터에 수신되었다는 승인을 받으면 해당 메시지의 복사본이 보낸 컴퓨터의 시스템 업무 일지 큐에 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-181">Once a message leaves the outgoing queue and an acknowledgment is received that the message was received on the destination computer, a copy of the message is kept in the sending computer's system journal queue.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d50c-182">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9d50c-182">Child Elements</span></span>  
  
|<span data-ttu-id="9d50c-183">요소</span><span class="sxs-lookup"><span data-stu-id="9d50c-183">Element</span></span>|<span data-ttu-id="9d50c-184">설명</span><span class="sxs-lookup"><span data-stu-id="9d50c-184">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="9d50c-185">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-185">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="9d50c-186">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-186">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<security>](security-of-netmsmqbinding.md)|<span data-ttu-id="9d50c-187">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-187">Defines the security settings for the binding.</span></span> <span data-ttu-id="9d50c-188">이 요소는 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-188">This element is of type <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9d50c-189">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9d50c-189">Parent Elements</span></span>  
  
|<span data-ttu-id="9d50c-190">요소</span><span class="sxs-lookup"><span data-stu-id="9d50c-190">Element</span></span>|<span data-ttu-id="9d50c-191">설명</span><span class="sxs-lookup"><span data-stu-id="9d50c-191">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="9d50c-192">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-192">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d50c-193">설명</span><span class="sxs-lookup"><span data-stu-id="9d50c-193">Remarks</span></span>  

 <span data-ttu-id="9d50c-194">`netMsmqBinding` 바인딩은 MSMQ(Microsoft Message Queuing)를 전송으로 활용하면서 큐에 대한 지원을 제공하며, 느슨하게 결합된 애플리케이션, 실패 격리, 로드 조정 및 연결이 끊긴 작업을 지원할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d50c-194">The `netMsmqBinding` binding provides support for queuing by leveraging Microsoft Message Queuing (MSMQ) as a transport and enables support for loosely coupled applications, failure isolation, load leveling and disconnected operations.</span></span> <span data-ttu-id="9d50c-195">이러한 기능에 대 한 설명은 [WCF의 큐](../../../wcf/feature-details/queues-in-wcf.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d50c-195">For a discussion of these features, see [Queues in WCF](../../../wcf/feature-details/queues-in-wcf.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d50c-196">예제</span><span class="sxs-lookup"><span data-stu-id="9d50c-196">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9d50c-197">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d50c-197">See also</span></span>

- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement>
- [\<binding>](bindings.md)
- [<span data-ttu-id="9d50c-198">바인딩</span><span class="sxs-lookup"><span data-stu-id="9d50c-198">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9d50c-199">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="9d50c-199">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9d50c-200">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="9d50c-200">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9d50c-201">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="9d50c-201">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
