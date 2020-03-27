---
title: 메시지 로깅 구성
ms.date: 03/30/2017
helpviewer_keywords:
- message logging [WCF]
ms.assetid: 0ff4c857-8f09-4b85-9dc0-89084706e4c9
ms.openlocfilehash: 283f43239d6cf5aea5ea668397a52313ff526e2a
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345191"
---
# <a name="configuring-message-logging"></a><span data-ttu-id="1d6bf-102">메시지 로깅 구성</span><span class="sxs-lookup"><span data-stu-id="1d6bf-102">Configuring Message Logging</span></span>

<span data-ttu-id="1d6bf-103">이 항목에서는 다양한 시나리오에서 메시지 로깅을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-103">This topic describes how you can configure message logging for different scenarios.</span></span>

## <a name="enabling-message-logging"></a><span data-ttu-id="1d6bf-104">메시지 로깅 활성화</span><span class="sxs-lookup"><span data-stu-id="1d6bf-104">Enabling Message Logging</span></span>

<span data-ttu-id="1d6bf-105">WCF(Windows 통신 재단)는 기본적으로 메시지를 기록하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-105">Windows Communication Foundation (WCF) does not log messages by default.</span></span> <span data-ttu-id="1d6bf-106">메시지 로깅을 활성화하려면 추적 수신기를 `System.ServiceModel.MessageLogging` 추적 소스에 추가하고 구성 파일에서 `<messagelogging>` 요소의 특성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-106">To activate message logging, you must add a trace listener to the `System.ServiceModel.MessageLogging` trace source and set attributes for the `<messagelogging>` element in the configuration file.</span></span>

<span data-ttu-id="1d6bf-107">다음 예제에서는 로깅을 활성화하고 추가 옵션을 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-107">The following example shows how to enable logging and specify additional options.</span></span>

```xml
<system.diagnostics>
  <sources>
    <source name="System.ServiceModel.MessageLogging">
      <listeners>
         <add name="messages"
              type="System.Diagnostics.XmlWriterTraceListener"
              initializeData="c:\logs\messages.svclog" />
        </listeners>
    </source>
  </sources>
</system.diagnostics>

<system.serviceModel>
  <diagnostics>
    <messageLogging
         logEntireMessage="true"
         logMalformedMessages="false"
         logMessagesAtServiceLevel="true"
         logMessagesAtTransportLevel="false"
         maxMessagesToLog="3000"
         maxSizeOfMessageToLog="2000"/>
  </diagnostics>
</system.serviceModel>
```

<span data-ttu-id="1d6bf-108">메시지 로깅 설정에 대한 자세한 내용은 [추적 및 메시지 로깅에 대한 권장 설정을](./tracing/recommended-settings-for-tracing-and-message-logging.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-108">For more information about message logging settings, see [Recommended Settings for Tracing and Message Logging](./tracing/recommended-settings-for-tracing-and-message-logging.md).</span></span>

<span data-ttu-id="1d6bf-109">`add`를 사용하여 사용할 수신기의 이름과 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-109">You can use `add` to specify the name and type of the listener you want to use.</span></span> <span data-ttu-id="1d6bf-110">예제 구성에서는 수신기 이름을 "messages"로 지정하고 표준 .NET Framework 추적 수신기(`System.Diagnostics.XmlWriterTraceListener`)를 사용할 형식으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-110">In the example configuration, the Listener is named "messages" and adds the standard .NET Framework trace listener (`System.Diagnostics.XmlWriterTraceListener`) as the type to use.</span></span> <span data-ttu-id="1d6bf-111">`System.Diagnostics.XmlWriterTraceListener`를 사용하려면 출력 파일의 위치와 이름을 구성 파일에 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-111">If you use `System.Diagnostics.XmlWriterTraceListener`, you must specify the output file location and name in the configuration file.</span></span> <span data-ttu-id="1d6bf-112">이 작업을 수행하려면 `initializeData`를 로그 파일의 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-112">This is done by setting `initializeData` to the name of the log file.</span></span> <span data-ttu-id="1d6bf-113">그렇지 않으면 시스템에서 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-113">Otherwise, the system throws an exception.</span></span> <span data-ttu-id="1d6bf-114">로그를 기본 파일에 내보내는 사용자 지정 수신기를 구현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-114">You can also implement a custom listener that emits logs to a default file.</span></span>

> [!NOTE]
> <span data-ttu-id="1d6bf-115">메시지 로깅 시 디스크 공간에 액세스하므로 특정 서비스에 대해 디스크에 기록되는 메시지 수를 제한해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-115">Because message logging accesses disk space, you should limit the number of messages that are written to disk for a particular service.</span></span> <span data-ttu-id="1d6bf-116">메시지 제한에 도달하면 정보 수준의 추적이 생성되고 모든 메시지 로깅 동작이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-116">When the message limit is reached, a trace at the Information level is produced and all message logging activities stop.</span></span>

<span data-ttu-id="1d6bf-117">로깅 수준 및 추가 옵션에 대한 자세한 내용은 로깅 수준 및 옵션 단원에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-117">The logging level, as well as the additional options, are discussed in the Logging Level and Options section.</span></span>

<span data-ttu-id="1d6bf-118">`switchValue`의 `source` 특성은 추적용으로만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-118">The `switchValue` attribute of a `source` is only valid for tracing.</span></span> <span data-ttu-id="1d6bf-119">다음과 같이 `switchValue`에 `System.ServiceModel.MessageLogging` 특성을 지정해도 아무런 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-119">If you specify a `switchValue` attribute for the `System.ServiceModel.MessageLogging` trace source as follows, it has no effect.</span></span>

```xml
<source name="System.ServiceModel.MessageLogging" switchValue="Verbose">
</source>
```

<span data-ttu-id="1d6bf-120">추적 소스를 비활성화하려면 대신에 `logMessagesAtServiceLevel` 요소의 `logMalformedMessages`, `logMessagesAtTransportLevel` 및 `messageLogging` 특성을 사용하고,</span><span class="sxs-lookup"><span data-stu-id="1d6bf-120">If you want to disable the trace source, you should use the `logMessagesAtServiceLevel`, `logMalformedMessages`, and `logMessagesAtTransportLevel` attributes of the `messageLogging` element instead.</span></span> <span data-ttu-id="1d6bf-121">이러한 모든 특성을 `false`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-121">You should set all these attributes to `false`.</span></span> <span data-ttu-id="1d6bf-122">이 작업은 구성 편집기 UI 인터페이스나 WMI를 통해 이전 코드 예제의 구성 파일을 사용하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-122">This can be done by using the configuration file in the previous code example, through the Configuration Editor UI interface, or using WMI.</span></span> <span data-ttu-id="1d6bf-123">구성 편집기 도구에 대한 자세한 내용은 [구성 편집기 도구(SvcConfigEditor.exe)를](../configuration-editor-tool-svcconfigeditor-exe.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-123">For more information about the Configuration Editor tool, see [Configuration Editor Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md).</span></span> <span data-ttu-id="1d6bf-124">WMI에 대한 자세한 내용은 [진단용 Windows 관리 계측 사용을](./wmi/index.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-124">For more information about WMI, see [Using Windows Management Instrumentation for Diagnostics](./wmi/index.md).</span></span>

## <a name="logging-levels-and-options"></a><span data-ttu-id="1d6bf-125">로깅 수준 및 옵션</span><span class="sxs-lookup"><span data-stu-id="1d6bf-125">Logging Levels and Options</span></span>

<span data-ttu-id="1d6bf-126">들어오는 메시지의 경우 로깅은 메시지가 형성된 직후, 메시지가 서비스 수준에서 사용자 코드에 도달하기 직전 그리고 잘못된 형식의 메시지가 감지될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-126">For incoming messages, logging happens immediately after the message is formed, immediately before the message gets to user code in the service level, and when malformed messages are detected.</span></span>

<span data-ttu-id="1d6bf-127">나가는 메시지의 경우 로깅은 메시지가 사용자 코드를 벗어난 직후 및 메시지가 송신되기 직전에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-127">For outgoing messages, logging happens immediately after the message leaves user code and immediately before the message goes on the wire.</span></span>

<span data-ttu-id="1d6bf-128">WCF는 서비스 및 전송의 두 가지 수준에서 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-128">WCF logs messages at two different levels, service and transport.</span></span> <span data-ttu-id="1d6bf-129">잘못된 형식의 메시지도 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-129">Malformed messages are also logged.</span></span> <span data-ttu-id="1d6bf-130">이 세 가지 범주는 서로 연관이 없으며 구성에서 별도로 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-130">The three categories are independent from each other and can be activated separately in configuration.</span></span>

<span data-ttu-id="1d6bf-131">로깅 수준은 `logMessagesAtServiceLevel` 요소의 `logMalformedMessages`, `logMessagesAtTransportLevel` 및 `messageLogging` 특성을 설정하여 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-131">You can control the logging level by setting the `logMessagesAtServiceLevel`, `logMalformedMessages`, and `logMessagesAtTransportLevel` attributes of the `messageLogging` element.</span></span>

### <a name="service-level"></a><span data-ttu-id="1d6bf-132">서비스 수준</span><span class="sxs-lookup"><span data-stu-id="1d6bf-132">Service Level</span></span>

<span data-ttu-id="1d6bf-133">이 계층에서 기록되는 메시지는 수신 시와 송신 시에 각각 사용자 코드를 가져오거나 남기게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-133">Messages logged at this layer are about to enter (on receiving) or leave (on sending) user code.</span></span> <span data-ttu-id="1d6bf-134">필터가 정의된 경우에는 해당 필터에 맞는 메시지만 기록되며</span><span class="sxs-lookup"><span data-stu-id="1d6bf-134">If filters have been defined, only messages that match the filters are logged.</span></span> <span data-ttu-id="1d6bf-135">그 이외에는 서비스 수준의 모든 메시지가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-135">Otherwise, all messages at the service level are logged.</span></span> <span data-ttu-id="1d6bf-136">신뢰할 수 있는 메시징 메시지를 제외한 인프라 메시지(트랜잭션, 피어 채널 및 보안)도 이 수준에서 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-136">Infrastructure messages (transactions, peer channel, and security) are also logged at this level, except for Reliable Messaging messages.</span></span> <span data-ttu-id="1d6bf-137">스트리밍된 메시지의 경우는 헤더만 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-137">On streamed messages, only the headers are logged.</span></span> <span data-ttu-id="1d6bf-138">또한 이 수준에서 해독된 보안 메시지도 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-138">In addition, secure messages are logged decrypted at this level.</span></span>

### <a name="transport-level"></a><span data-ttu-id="1d6bf-139">전송 수준</span><span class="sxs-lookup"><span data-stu-id="1d6bf-139">Transport Level</span></span>

<span data-ttu-id="1d6bf-140">이 계층에서 기록된 메시지는 통신 전송 동안 또는 그 이후에 인코딩이나 디코딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-140">Messages logged at this layer are ready to be encoded or decoded for or after transportation on the wire.</span></span> <span data-ttu-id="1d6bf-141">필터가 정의된 경우에는 해당 필터에 맞는 메시지만 기록되며</span><span class="sxs-lookup"><span data-stu-id="1d6bf-141">If filters have been defined, only messages that match the filters are logged.</span></span> <span data-ttu-id="1d6bf-142">그 이외에는 전송 계층의 모든 메시지가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-142">Otherwise, all messages at the transport layer are logged.</span></span> <span data-ttu-id="1d6bf-143">신뢰할 수 있는 메시징 메시지를 포함한 모든 인프라 메시지도 이 계층에서 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-143">All infrastructure messages are logged at this layer, including reliable messaging messages.</span></span> <span data-ttu-id="1d6bf-144">스트리밍된 메시지의 경우는 헤더만 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-144">On streamed messages, only the headers are logged.</span></span> <span data-ttu-id="1d6bf-145">또한 보안 메시지는 이 수준에서 암호화된 채로 기록되는데 HTTPS와 같은 보안 전송이 사용되는 경우는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-145">In addition, secure messages are logged as encrypted at this level, except if a secure transport such as HTTPS is used.</span></span>

### <a name="malformed-level"></a><span data-ttu-id="1d6bf-146">잘못된 형식의 수준</span><span class="sxs-lookup"><span data-stu-id="1d6bf-146">Malformed Level</span></span>

<span data-ttu-id="1d6bf-147">잘못된 메시지는 모든 처리 단계에서 WCF 스택에 의해 거부되는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-147">Malformed messages are messages that are rejected by the WCF stack at any stage of processing.</span></span> <span data-ttu-id="1d6bf-148">이러한 잘못된 형식의 메시지는 암호화된 상태라면 암호화된 상태로, 적절하지 않은 XML로 된 상태라면 그 상태 그대로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-148">Malformed messages are logged as-is: encrypted if they are so, with non-proper XML, and so on.</span></span> <span data-ttu-id="1d6bf-149">`maxSizeOfMessageToLog`는 CDATA로 기록될 메시지 크기를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-149">`maxSizeOfMessageToLog` defined the size of the message to be logged as CDATA.</span></span> <span data-ttu-id="1d6bf-150">기본적으로 `maxSizeOfMessageToLog`는256K입니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-150">By default, `maxSizeOfMessageToLog` is equal to 256K.</span></span> <span data-ttu-id="1d6bf-151">이 특성에 대한 자세한 내용은 기타 옵션 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-151">For more information about this attribute, see the Other Options section.</span></span>

### <a name="other-options"></a><span data-ttu-id="1d6bf-152">다른 옵션</span><span class="sxs-lookup"><span data-stu-id="1d6bf-152">Other Options</span></span>

<span data-ttu-id="1d6bf-153">로깅 수준 이외에 다음과 같은 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-153">In addition to the logging levels, the user can specify the following options:</span></span>

- <span data-ttu-id="1d6bf-154">전체 메시지 기록(`logEntireMessage` 특성): 이 값은 전체 메시지(메시지 헤더 및 본문)를 기록할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-154">Log Entire Message (`logEntireMessage` attribute): This value specifies whether the entire message (message header and body) is logged.</span></span> <span data-ttu-id="1d6bf-155">기본값은 `false`로, 메시지 헤더만 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-155">The default value is `false`, meaning that only the header is logged.</span></span> <span data-ttu-id="1d6bf-156">이 설정은 서비스 및 전송 메시지 로깅 수준에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-156">This setting affects service and transport message logging levels..</span></span>

- <span data-ttu-id="1d6bf-157">기록할 최대 메시지 수(`maxMessagesToLog` 특성): 이 값은 기록할 최대 메시지 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-157">Max messages to log (`maxMessagesToLog` attribute): This value specifies the maximum number of messages to log.</span></span> <span data-ttu-id="1d6bf-158">모든 메시지(서비스, 전송 및 잘못된 형식의 메시지)가 이 할당량에 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-158">All messages (service, transport, and malformed messages) are counted towards this quota.</span></span> <span data-ttu-id="1d6bf-159">할당량에 도달하면 추적을 내보내고 추가 메시지는 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-159">When the quota is reached, a trace is emitted and no additional message is logged.</span></span> <span data-ttu-id="1d6bf-160">기본값은 10000입니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-160">The default value is 10000.</span></span>

- <span data-ttu-id="1d6bf-161">기록할 메시지 최대 크기(`maxSizeOfMessageToLog` 특성): 이 값은 기록할 최대 메시지 크기(바이트)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-161">Max size of message to log (`maxSizeOfMessageToLog` attribute): This value specifies the maximum size of messages to log in bytes.</span></span> <span data-ttu-id="1d6bf-162">이 크기 제한을 초과하는 메시지는 기록되지 않으며 해당 메시지에 대해 아무런 동작이 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-162">Messages that exceed the size limit are not logged, and no other activity is performed for that message.</span></span> <span data-ttu-id="1d6bf-163">이 설정은 모든 추적 수준에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-163">This setting affects all trace levels.</span></span> <span data-ttu-id="1d6bf-164">ServiceModel 추적을 사용하도록 설정된 경우, 경고 수준 추적을 첫 번째 로깅 지점(ServiceModelSend\* 또는 TransportReceive)에서 내보내어 사용자에게 통보합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-164">If ServiceModel tracing is on, a Warning level trace is emitted at the first logging point (ServiceModelSend\* or TransportReceive) to notify the user.</span></span> <span data-ttu-id="1d6bf-165">서비스 수준 및 전송 수준 메시지의 기본값은 256K며 잘못된 형식의 메시지에 대한 기본값은 4K입니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-165">The default value for service level and transport level messages is 256K, while the default value for malformed messages is 4K.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="1d6bf-166">`maxSizeOfMessageToLog`와 비교하기 위해 계산되는 메시지 크기는 serialization 이전의 메모리에 있는 메시지 크기로,</span><span class="sxs-lookup"><span data-stu-id="1d6bf-166">The message size that is computed to compare against `maxSizeOfMessageToLog` is the message size in memory before serialization.</span></span> <span data-ttu-id="1d6bf-167">이 크기는 기록되는 메시지 문자열의 실제 길이와 다를 수 있으며 대부분의 경우 실제 크기보다 더 큽니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-167">This size can differ from the actual length of the message string that is being logged, and in many occasions is bigger than the actual size.</span></span> <span data-ttu-id="1d6bf-168">따라서 메시지가 기록되지 않을 수 있으므로</span><span class="sxs-lookup"><span data-stu-id="1d6bf-168">As a result, messages may not be logged.</span></span> <span data-ttu-id="1d6bf-169">이를 감안하여`maxSizeOfMessageToLog` 특성을 필요한 메시지 크기보다 10% 더 크게 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-169">You can account for this fact by specifying the `maxSizeOfMessageToLog` attribute to be 10% larger than the expected message size.</span></span> <span data-ttu-id="1d6bf-170">또한 잘못된 형식의 메시지가 기록될 경우 메시지 로그에 사용되는 실제 디스크 공간은 `maxSizeOfMessageToLog`에 지정된 값의 최대 5배가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-170">In addition, if malformed messages are logged, the actual disk space utilized by the message logs can be up to 5 times the size of the value specified by `maxSizeOfMessageToLog`.</span></span>

<span data-ttu-id="1d6bf-171">구성 파일에 추적 수신기가 정의되어 있지 않으면 지정된 로깅 수준과 관계없이 로깅 출력이 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-171">If no trace listener is defined in the configuration file, no logging output is generated regardless of the specified logging level.</span></span>

<span data-ttu-id="1d6bf-172">이 단원에 설명된 특성과 같은 메시지 로깅 옵션은 WMI(Windows Management Instrumentation)를 사용하여 런타임에 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-172">Message logging options, such as the attributes described in this section, can be changed at runtime using Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="1d6bf-173">이 작업은 이러한 부울 속성을 `LogMessagesAtServiceLevel` `LogMessagesAtTransportLevel` `LogMalformedMessages`노출하는 [AppDomainInfo](./wmi/appdomaininfo.md) 인스턴스에 액세스하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-173">This can be done by accessing the [AppDomainInfo](./wmi/appdomaininfo.md) instance, which exposes these Boolean properties: `LogMessagesAtServiceLevel`, `LogMessagesAtTransportLevel`, and `LogMalformedMessages`.</span></span> <span data-ttu-id="1d6bf-174">따라서 메시지 로깅을 위한 추적 수신기를 구성하지만 이러한 옵션을 구성에서 `false`로 설정해도, 이후에 애플리케이션 실행 시 `true`로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-174">Therefore, if you configure a trace listener for message logging, but set these options to `false` in configuration, you can later change them to `true` when the application is running.</span></span> <span data-ttu-id="1d6bf-175">이를 통해 메시지 로깅을 런타임에 효과적으로 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-175">This effectively enables message logging at runtime.</span></span> <span data-ttu-id="1d6bf-176">마찬가지로 구성 파일에 메시지 로깅을 활성화하더라도, WMI를 사용하여 런타임에 메시지 로깅을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-176">Similarly, if you enable message logging in your configuration file, you can disable it at runtime using WMI.</span></span> <span data-ttu-id="1d6bf-177">자세한 내용은 [진단용 Windows 관리 계측 사용을](./wmi/index.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-177">For more information, see [Using Windows Management Instrumentation for Diagnostics](./wmi/index.md).</span></span>

<span data-ttu-id="1d6bf-178">메시지 로그의 `source` 필드에서는 메시지가 기록되는 컨텍스트를 지정합니다. 즉, 요청 메시지를 보내거나 받을 때 요청-회신을 위한 것인지 단방향 요청인지, 그리고 위치가 서비스 모델 또는 전송 계층인지, 또는 잘못된 형식의 메시지인지 등을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-178">The `source` field in a message log specifies in which context the message is logged: when sending/receiving a request message, for a request-reply or 1-way request, at service model or transport layer, or in the case of a malformed message.</span></span>

<span data-ttu-id="1d6bf-179">잘못된 형식의 `source` 메시지의 `Malformed`경우 와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-179">For malformed messages, `source`  is equal to `Malformed`.</span></span> <span data-ttu-id="1d6bf-180">그렇지 않으면 소스는 컨텍스트에 따라 다음 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-180">Otherwise, source has the following values based on the context.</span></span>

<span data-ttu-id="1d6bf-181">요청/회신의 경우</span><span class="sxs-lookup"><span data-stu-id="1d6bf-181">For Request/Reply</span></span>

||<span data-ttu-id="1d6bf-182">요청 보내기</span><span class="sxs-lookup"><span data-stu-id="1d6bf-182">Send Request</span></span>|<span data-ttu-id="1d6bf-183">요청 받기</span><span class="sxs-lookup"><span data-stu-id="1d6bf-183">Receive Request</span></span>|<span data-ttu-id="1d6bf-184">회신 보내기</span><span class="sxs-lookup"><span data-stu-id="1d6bf-184">Send Reply</span></span>|<span data-ttu-id="1d6bf-185">회신 받기</span><span class="sxs-lookup"><span data-stu-id="1d6bf-185">Receive Reply</span></span>|
|-|------------------|---------------------|----------------|-------------------|
|<span data-ttu-id="1d6bf-186">서비스 모델 계층</span><span class="sxs-lookup"><span data-stu-id="1d6bf-186">Service Model layer</span></span>|<span data-ttu-id="1d6bf-187">서비스</span><span class="sxs-lookup"><span data-stu-id="1d6bf-187">Service</span></span><br /><br /> <span data-ttu-id="1d6bf-188">Level</span><span class="sxs-lookup"><span data-stu-id="1d6bf-188">Level</span></span><br /><br /> <span data-ttu-id="1d6bf-189">보내기</span><span class="sxs-lookup"><span data-stu-id="1d6bf-189">Send</span></span><br /><br /> <span data-ttu-id="1d6bf-190">요청</span><span class="sxs-lookup"><span data-stu-id="1d6bf-190">Request</span></span>|<span data-ttu-id="1d6bf-191">서비스</span><span class="sxs-lookup"><span data-stu-id="1d6bf-191">Service</span></span><br /><br /> <span data-ttu-id="1d6bf-192">Level</span><span class="sxs-lookup"><span data-stu-id="1d6bf-192">Level</span></span><br /><br /> <span data-ttu-id="1d6bf-193">수신</span><span class="sxs-lookup"><span data-stu-id="1d6bf-193">Receive</span></span><br /><br /> <span data-ttu-id="1d6bf-194">요청</span><span class="sxs-lookup"><span data-stu-id="1d6bf-194">Request</span></span>|<span data-ttu-id="1d6bf-195">서비스</span><span class="sxs-lookup"><span data-stu-id="1d6bf-195">Service</span></span><br /><br /> <span data-ttu-id="1d6bf-196">Level</span><span class="sxs-lookup"><span data-stu-id="1d6bf-196">Level</span></span><br /><br /> <span data-ttu-id="1d6bf-197">보내기</span><span class="sxs-lookup"><span data-stu-id="1d6bf-197">Send</span></span><br /><br /> <span data-ttu-id="1d6bf-198">회신</span><span class="sxs-lookup"><span data-stu-id="1d6bf-198">Reply</span></span>|<span data-ttu-id="1d6bf-199">서비스</span><span class="sxs-lookup"><span data-stu-id="1d6bf-199">Service</span></span><br /><br /> <span data-ttu-id="1d6bf-200">Level</span><span class="sxs-lookup"><span data-stu-id="1d6bf-200">Level</span></span><br /><br /> <span data-ttu-id="1d6bf-201">수신</span><span class="sxs-lookup"><span data-stu-id="1d6bf-201">Receive</span></span><br /><br /> <span data-ttu-id="1d6bf-202">회신</span><span class="sxs-lookup"><span data-stu-id="1d6bf-202">Reply</span></span>|
|<span data-ttu-id="1d6bf-203">전송 계층</span><span class="sxs-lookup"><span data-stu-id="1d6bf-203">Transport layer</span></span>|<span data-ttu-id="1d6bf-204">전송</span><span class="sxs-lookup"><span data-stu-id="1d6bf-204">Transport</span></span><br /><br /> <span data-ttu-id="1d6bf-205">보내기</span><span class="sxs-lookup"><span data-stu-id="1d6bf-205">Send</span></span>|<span data-ttu-id="1d6bf-206">전송</span><span class="sxs-lookup"><span data-stu-id="1d6bf-206">Transport</span></span><br /><br /> <span data-ttu-id="1d6bf-207">수신</span><span class="sxs-lookup"><span data-stu-id="1d6bf-207">Receive</span></span>|<span data-ttu-id="1d6bf-208">전송</span><span class="sxs-lookup"><span data-stu-id="1d6bf-208">Transport</span></span><br /><br /> <span data-ttu-id="1d6bf-209">보내기</span><span class="sxs-lookup"><span data-stu-id="1d6bf-209">Send</span></span>|<span data-ttu-id="1d6bf-210">전송</span><span class="sxs-lookup"><span data-stu-id="1d6bf-210">Transport</span></span><br /><br /> <span data-ttu-id="1d6bf-211">수신</span><span class="sxs-lookup"><span data-stu-id="1d6bf-211">Receive</span></span>|

<span data-ttu-id="1d6bf-212">단방향 요청의 경우</span><span class="sxs-lookup"><span data-stu-id="1d6bf-212">For One-way Request</span></span>

||<span data-ttu-id="1d6bf-213">요청 보내기</span><span class="sxs-lookup"><span data-stu-id="1d6bf-213">Send Request</span></span>|<span data-ttu-id="1d6bf-214">요청 받기</span><span class="sxs-lookup"><span data-stu-id="1d6bf-214">Receive Request</span></span>|
|-|------------------|---------------------|
|<span data-ttu-id="1d6bf-215">서비스 모델 계층</span><span class="sxs-lookup"><span data-stu-id="1d6bf-215">Service Model layer</span></span>|<span data-ttu-id="1d6bf-216">서비스</span><span class="sxs-lookup"><span data-stu-id="1d6bf-216">Service</span></span><br /><br /> <span data-ttu-id="1d6bf-217">Level</span><span class="sxs-lookup"><span data-stu-id="1d6bf-217">Level</span></span><br /><br /> <span data-ttu-id="1d6bf-218">보내기</span><span class="sxs-lookup"><span data-stu-id="1d6bf-218">Send</span></span><br /><br /> <span data-ttu-id="1d6bf-219">데이터그램</span><span class="sxs-lookup"><span data-stu-id="1d6bf-219">Datagram</span></span>|<span data-ttu-id="1d6bf-220">서비스</span><span class="sxs-lookup"><span data-stu-id="1d6bf-220">Service</span></span><br /><br /> <span data-ttu-id="1d6bf-221">Level</span><span class="sxs-lookup"><span data-stu-id="1d6bf-221">Level</span></span><br /><br /> <span data-ttu-id="1d6bf-222">수신</span><span class="sxs-lookup"><span data-stu-id="1d6bf-222">Receive</span></span><br /><br /> <span data-ttu-id="1d6bf-223">데이터그램</span><span class="sxs-lookup"><span data-stu-id="1d6bf-223">Datagram</span></span>|
|<span data-ttu-id="1d6bf-224">전송 계층</span><span class="sxs-lookup"><span data-stu-id="1d6bf-224">Transport layer</span></span>|<span data-ttu-id="1d6bf-225">전송</span><span class="sxs-lookup"><span data-stu-id="1d6bf-225">Transport</span></span><br /><br /> <span data-ttu-id="1d6bf-226">보내기</span><span class="sxs-lookup"><span data-stu-id="1d6bf-226">Send</span></span>|<span data-ttu-id="1d6bf-227">전송</span><span class="sxs-lookup"><span data-stu-id="1d6bf-227">Transport</span></span><br /><br /> <span data-ttu-id="1d6bf-228">수신</span><span class="sxs-lookup"><span data-stu-id="1d6bf-228">Receive</span></span>|

## <a name="message-filters"></a><span data-ttu-id="1d6bf-229">메시지 필터</span><span class="sxs-lookup"><span data-stu-id="1d6bf-229">Message Filters</span></span>

<span data-ttu-id="1d6bf-230">메시지 필터는 `messageLogging` 구성 섹션의 `diagnostics` 구성 요소에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-230">Message filters are defined in the `messageLogging` configuration element of the `diagnostics` configuration section.</span></span> <span data-ttu-id="1d6bf-231">이러한 메시지 필터는 서비스 및 전송 수준에서 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-231">They are applied at the service and transport level.</span></span> <span data-ttu-id="1d6bf-232">하나 이상의 필터가 정의되면 그 중 최소한 하나의 필터와 일치하는 메시지만 로깅됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-232">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="1d6bf-233">정의된 필터가 없으면 모든 메시지가 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-233">If no filter is defined, all messages pass through.</span></span>

<span data-ttu-id="1d6bf-234">필터는 모든 XPath 구문을 지원하며, 구성 파일에 표시되는 순서대로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-234">Filters support the full XPath syntax and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="1d6bf-235">필터 구문에 오류가 있으면 구성 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-235">A syntactically incorrect filter results in a configuration exception.</span></span>

<span data-ttu-id="1d6bf-236">또한 필터에는 `nodeQuota` 특성을 사용하는 안전 기능이 있어, 필터에 맞게 검사할 수 있는 XPath DOM의 최대 노드 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-236">Filters also provide a safety feature using the `nodeQuota` attribute, which limits the maximum number of nodes in the XPath DOM that can be examined to match the filter.</span></span>

<span data-ttu-id="1d6bf-237">다음 예제에서는 SOAP 헤더 섹션이 있는 메시지만 기록하는 필터를 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-237">The following example shows how to configure a filter that records only messages that have a SOAP header section.</span></span>

```xml
<messageLogging logEntireMessage="true"
    logMalformedMessages="true"
    logMessagesAtServiceLevel="true"
    logMessagesAtTransportLevel="true"
    maxMessagesToLog="420">
    <filters>
        <add nodeQuota="10" xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
                 /soap:Envelope/soap:Header
        </add>
     </filters>
</messageLogging>
```

<span data-ttu-id="1d6bf-238">메시지 본문에는 필터가 적용되지 않고,</span><span class="sxs-lookup"><span data-stu-id="1d6bf-238">Filters cannot be applied to the body of a message.</span></span> <span data-ttu-id="1d6bf-239">메시지 본문을 조작하려는 필터는 필터 목록에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-239">Filters that attempt to manipulate the body of a message are removed from the list of filters.</span></span> <span data-ttu-id="1d6bf-240">이를 나타내는 이벤트도 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-240">An event is also emitted that indicates this.</span></span> <span data-ttu-id="1d6bf-241">예를 들어 다음과 같은 필터는 필터 테이블에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-241">For example, the following filter would be removed from the filter table.</span></span>

```xml
<add xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">/s:Envelope/s:Body[contains(text(), "Hello")]</add>
```

## <a name="configuring-a-custom-listener"></a><span data-ttu-id="1d6bf-242">사용자 지정 수신기 구성</span><span class="sxs-lookup"><span data-stu-id="1d6bf-242">Configuring a Custom Listener</span></span>

<span data-ttu-id="1d6bf-243">추가 옵션이 있는 사용자 지정 수신기를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-243">You can also configure a custom listener with additional options.</span></span> <span data-ttu-id="1d6bf-244">사용자 지정 수신기는 메시지를 기록하기 전에 메시지에서 애플리케이션별 PII 요소를 필터링하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-244">A custom listener can be useful in filtering application-specific PII elements from messages before logging.</span></span> <span data-ttu-id="1d6bf-245">다음 예제에서는 사용자 지정 수신기 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-245">The following example demonstrates a custom listener configuration.</span></span>

```xml
<system.diagnostics>
   <sources>
     <source name="System.ServiceModel.MessageLogging">
           <listeners>
             <add name="MyListener"
                    type="YourCustomListener"
                    initializeData="c:\logs\messages.svclog"
                    maxDiskSpace="1000"/>
           </listeners>
     </source>
   </sources>
</system.diagnostics>
```

<span data-ttu-id="1d6bf-246">`type` 특성을 해당 형식의 정규화된 어셈블리 이름으로 설정해야 함에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-246">You should be aware that the `type` attribute should be set to a qualified assembly name of the type.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d6bf-247">참조</span><span class="sxs-lookup"><span data-stu-id="1d6bf-247">See also</span></span>

- [<span data-ttu-id="1d6bf-248">\<메시지 로깅></span><span class="sxs-lookup"><span data-stu-id="1d6bf-248">\<messageLogging></span></span>](../../configure-apps/file-schema/wcf/messagelogging.md)
- [<span data-ttu-id="1d6bf-249">메시지 로깅</span><span class="sxs-lookup"><span data-stu-id="1d6bf-249">Message Logging</span></span>](message-logging.md)
- [<span data-ttu-id="1d6bf-250">추적 및 메시지 로깅에 권장되는 설정</span><span class="sxs-lookup"><span data-stu-id="1d6bf-250">Recommended Settings for Tracing and Message Logging</span></span>](./tracing/recommended-settings-for-tracing-and-message-logging.md)
