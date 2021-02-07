---
description: 다음에 대해 자세히 알아보세요. <messageLogging>
title: <messageLogging>
ms.date: 03/30/2017
ms.assetid: 1d06a7e6-9633-4a12-8c5d-123adbbc19c5
ms.openlocfilehash: e26a616bb7974a8fbad9a7f920a28e06422e09c1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749287"
---
# \<messageLogging>

<span data-ttu-id="2cb49-102">이 요소는 WCF(Windows Communication Foundation)의 메시지 로깅 기능 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-102">This element defines the settings for the message-logging capabilities of Windows Communication Foundation (WCF).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageLogging>**  
  
## <a name="syntax"></a><span data-ttu-id="2cb49-103">구문</span><span class="sxs-lookup"><span data-stu-id="2cb49-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <messageLogging logEntireMessage="Boolean"
                    logMalformedMessages="Boolean"
                    logMessagesAtServiceLevel="Boolean"
                    logMessagesAtTransportLevel="Boolean"
                    maxMessagesToLog="Integer"
                    maxSizeOfMessageToLog="Integer">
      <filters>
        <clear />
      </filters>
    </messageLogging>
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2cb49-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2cb49-104">Attributes and Elements</span></span>  

 <span data-ttu-id="2cb49-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2cb49-106">특성</span><span class="sxs-lookup"><span data-stu-id="2cb49-106">Attributes</span></span>  
  
|<span data-ttu-id="2cb49-107">attribute</span><span class="sxs-lookup"><span data-stu-id="2cb49-107">Attribute</span></span>|<span data-ttu-id="2cb49-108">설명</span><span class="sxs-lookup"><span data-stu-id="2cb49-108">Description</span></span>|  
|---------------|-----------------|  
|`logEntireMessage`|<span data-ttu-id="2cb49-109">전체 메시지(메시지 헤더 및 본문)를 로깅할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-109">A Boolean value that specifies whether the entire message (message header and body) is logged.</span></span> <span data-ttu-id="2cb49-110">기본값은 `false`로, 메시지 헤더만 로깅됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-110">The default is `false`, which means that only the message header is logged.</span></span> <span data-ttu-id="2cb49-111">이 설정은 모든 메시지 로깅 수준(서비스, 전송 및 잘못된 형식)에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-111">This setting affects all message logging levels (service, transport, and malformed).</span></span>|  
|`logMalformedMessages`|<span data-ttu-id="2cb49-112">잘못된 형식의 메시지를 로깅할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-112">A Boolean value that specifies whether malformed messages are logged.</span></span> <span data-ttu-id="2cb49-113">잘못된 형식의 메시지는 `maxMessagesToLog`에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-113">Malformed messages do not count toward the `maxMessagesToLog`.</span></span> <span data-ttu-id="2cb49-114">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-114">The default is `false`.</span></span>|  
|`logMessagesAtServiceLevel`|<span data-ttu-id="2cb49-115">암호화 및 전송 관련 변형 전에 메시지를 서비스 수준에서 추적할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-115">A Boolean value that specifies whether messages are traced at the service level (before encryption- and transport-related transforms).</span></span> <span data-ttu-id="2cb49-116">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-116">The default is `false`.</span></span>|  
|`logMessagesAtTransportLevel`|<span data-ttu-id="2cb49-117">전송 수준에서 메시지를 추적하는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-117">A Boolean value that specifies whether messages are traced at the transport level.</span></span> <span data-ttu-id="2cb49-118">구성 파일에 지정된 모든 필터가 적용되며, 필터와 일치하는 메시지만 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-118">Any filters specified in the config file are applied, and only messages that match the filters are traced.</span></span> <span data-ttu-id="2cb49-119">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-119">The default is `false`.</span></span>|  
|`maxMessagesToLog`|<span data-ttu-id="2cb49-120">로깅할 최대 메시지 수를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-120">A positive integer that specifies the maximum number of messages to log.</span></span> <span data-ttu-id="2cb49-121">기본값은 1000입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-121">The default is 1000.</span></span>|  
|`maxSizeOfMessageToLog`|<span data-ttu-id="2cb49-122">로깅할 최대 메시지 크기(바이트)를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-122">A positive integer that specifies the maximum size, in bytes, of a message to log.</span></span> <span data-ttu-id="2cb49-123">이 한도를 초과하는 메시지는 로깅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-123">Messages larger than the limit will not be logged.</span></span> <span data-ttu-id="2cb49-124">이 설정은 모든 추적 수준에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-124">This setting affects all trace levels.</span></span> <span data-ttu-id="2cb49-125">기본값은 262144(0x4000)입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-125">The default is 262144(0x4000).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2cb49-126">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2cb49-126">Child Elements</span></span>  
  
|<span data-ttu-id="2cb49-127">요소</span><span class="sxs-lookup"><span data-stu-id="2cb49-127">Element</span></span>|<span data-ttu-id="2cb49-128">설명</span><span class="sxs-lookup"><span data-stu-id="2cb49-128">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2cb49-129">filters</span><span class="sxs-lookup"><span data-stu-id="2cb49-129">filters</span></span>|<span data-ttu-id="2cb49-130">`filters` 요소는 XPath 필터 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-130">The `filters` element holds a collection of XPath filters.</span></span> <span data-ttu-id="2cb49-131">`logMessagesAtTransportLevel`이 `true`로 설정되어 전송 메시지 로깅을 사용할 경우 필터와 일치하는 메시지만 로깅됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-131">When transport message logging is enabled (`logMessagesAtTransportLevel` is `true`), only messages matching the filters will be logged.</span></span><br /><br /> <span data-ttu-id="2cb49-132">필터는 전송 레이어에서만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-132">Filters are applied only at the transport layer.</span></span> <span data-ttu-id="2cb49-133">서비스 수준 및 잘못된 형식의 메시지 로깅은 필터의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-133">Service level and malformed message logging are not affected by filters.</span></span><br /><br /> <span data-ttu-id="2cb49-134">이 요소의 유일한 특성인 `filter`는 XpathFilter입니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-134">The only attribute for this element, `filter`, is an XpathFilter.</span></span><br /><br /> `<filters>     <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">/soap:Envelope</add> </filters>`|  
  
### <a name="parent-elements"></a><span data-ttu-id="2cb49-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2cb49-135">Parent Elements</span></span>  
  
|<span data-ttu-id="2cb49-136">요소</span><span class="sxs-lookup"><span data-stu-id="2cb49-136">Element</span></span>|<span data-ttu-id="2cb49-137">설명</span><span class="sxs-lookup"><span data-stu-id="2cb49-137">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2cb49-138">진단</span><span class="sxs-lookup"><span data-stu-id="2cb49-138">diagnostics</span></span>|<span data-ttu-id="2cb49-139">관리자의 런타임 검사 및 제어를 위한 WCF 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-139">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2cb49-140">설명</span><span class="sxs-lookup"><span data-stu-id="2cb49-140">Remarks</span></span>  

 <span data-ttu-id="2cb49-141">메시지는 스택에서 서비스, 전송 및 잘못된 형식의 3가지 다른 수준에서 로깅됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-141">Messages are logged at three different levels in the stack: service, transport, and malformed.</span></span> <span data-ttu-id="2cb49-142">각 수준은 별도로 활성화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-142">Each level can be activated separately.</span></span>  
  
 <span data-ttu-id="2cb49-143">XPath 필터를 추가하여 전송 및 서비스 수준에서 특정 메시지를 로깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-143">XPath filters can be added to log specific messages at the transport and service levels.</span></span> <span data-ttu-id="2cb49-144">정의된 필터가 없으면 모든 메시지가 로깅됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-144">If no filters are defined, all messages are logged.</span></span> <span data-ttu-id="2cb49-145">필터는 메시지의 헤더에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-145">Filters are applied only to the headers of the message.</span></span> <span data-ttu-id="2cb49-146">본문은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-146">The body is ignored.</span></span> <span data-ttu-id="2cb49-147">WCF는 성능 향상을 위해 메시지 본문을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-147">WCF ignores the message body to improve performance.</span></span> <span data-ttu-id="2cb49-148">본문의 내용을 기반으로 필터링하려면 해당 작업을 수행하는 필터를 갖춘 사용자 지정 수신기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-148">If you want to filter based on the content of the body, you can create a custom listener with a filter that does so.</span></span>  
  
 <span data-ttu-id="2cb49-149">메시지 추적을 활성화하려면 추적 수신기를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-149">You need to create a trace listener to activate message tracing.</span></span> <span data-ttu-id="2cb49-150">수신기는 <xref:System.Diagnostics> 추적 아키텍처에서 작동하는 수신기일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-150">The listener itself can be any listener that works with the <xref:System.Diagnostics> tracing architecture.</span></span> <span data-ttu-id="2cb49-151">다음 예에서는 이러한 수신기를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2cb49-151">The following example demonstrates how to create such a listener.</span></span>  
  
```xml  
<system.diagnostics>
  <sources>
    <source name="System.ServiceModel"
            switchValue="Verbose">
      <listeners>
        <clear />
        <add type="System.Diagnostics.DefaultTraceListener"
             name="Default"
             traceOutputOptions="None" />
        <add name="ServiceModel Listener"
             traceOutputOptions="None" />
      </listeners>
    </source>
    <source name="System.ServiceModel.MessageLogging">
      <listeners>
        <clear />
        <add type="System.Diagnostics.DefaultTraceListener"
             name="Default"
             traceOutputOptions="None" />
        <add name="MessageLogging Listener"
             traceOutputOptions="None" />
      </listeners>
    </source>
  </sources>
  <sharedListeners>
    <add initializeData="C:\ItProTools\TraceLog.xml"
         type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         name="ServiceModel Listener"
         traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />
    <add initializeData="C:\ItProTools\MessageLog.log"
         type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         name="MessageLogging Listener"
         traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />
  </sharedListeners>
</system.diagnostics>
```  
  
## <a name="example"></a><span data-ttu-id="2cb49-152">예제</span><span class="sxs-lookup"><span data-stu-id="2cb49-152">Example</span></span>  
  
```xml  
<messageLogging logEntireMessage="true"
                logMalformedMessages="true"
                logMessagesAtServiceLevel="true"
                logMessagesAtTransportLevel="true"
                maxMessagesToLog="42"
                maxSizeOfMessageToLog="42">
  <filters>
    <clear />
  </filters>
</messageLogging>
```  
  
## <a name="see-also"></a><span data-ttu-id="2cb49-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2cb49-153">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- [<span data-ttu-id="2cb49-154">메시지 로깅 구성</span><span class="sxs-lookup"><span data-stu-id="2cb49-154">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
