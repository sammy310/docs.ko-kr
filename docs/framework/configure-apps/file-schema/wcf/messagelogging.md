---
title: <messageLogging>
ms.date: 03/30/2017
ms.assetid: 1d06a7e6-9633-4a12-8c5d-123adbbc19c5
ms.openlocfilehash: fd4d678b1e861a47762d8a64f85dcc052a30fe2b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204803"
---
# \<messageLogging>

<span data-ttu-id="f6bed-101">이 요소는 WCF(Windows Communication Foundation)의 메시지 로깅 기능 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-101">This element defines the settings for the message-logging capabilities of Windows Communication Foundation (WCF).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageLogging>**  
  
## <a name="syntax"></a><span data-ttu-id="f6bed-102">구문</span><span class="sxs-lookup"><span data-stu-id="f6bed-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6bed-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f6bed-103">Attributes and Elements</span></span>  

 <span data-ttu-id="f6bed-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6bed-105">특성</span><span class="sxs-lookup"><span data-stu-id="f6bed-105">Attributes</span></span>  
  
|<span data-ttu-id="f6bed-106">attribute</span><span class="sxs-lookup"><span data-stu-id="f6bed-106">Attribute</span></span>|<span data-ttu-id="f6bed-107">설명</span><span class="sxs-lookup"><span data-stu-id="f6bed-107">Description</span></span>|  
|---------------|-----------------|  
|`logEntireMessage`|<span data-ttu-id="f6bed-108">전체 메시지(메시지 헤더 및 본문)를 로깅할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-108">A Boolean value that specifies whether the entire message (message header and body) is logged.</span></span> <span data-ttu-id="f6bed-109">기본값은 `false`로, 메시지 헤더만 로깅됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-109">The default is `false`, which means that only the message header is logged.</span></span> <span data-ttu-id="f6bed-110">이 설정은 모든 메시지 로깅 수준(서비스, 전송 및 잘못된 형식)에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-110">This setting affects all message logging levels (service, transport, and malformed).</span></span>|  
|`logMalformedMessages`|<span data-ttu-id="f6bed-111">잘못된 형식의 메시지를 로깅할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-111">A Boolean value that specifies whether malformed messages are logged.</span></span> <span data-ttu-id="f6bed-112">잘못된 형식의 메시지는 `maxMessagesToLog`에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-112">Malformed messages do not count toward the `maxMessagesToLog`.</span></span> <span data-ttu-id="f6bed-113">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-113">The default is `false`.</span></span>|  
|`logMessagesAtServiceLevel`|<span data-ttu-id="f6bed-114">암호화 및 전송 관련 변형 전에 메시지를 서비스 수준에서 추적할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-114">A Boolean value that specifies whether messages are traced at the service level (before encryption- and transport-related transforms).</span></span> <span data-ttu-id="f6bed-115">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-115">The default is `false`.</span></span>|  
|`logMessagesAtTransportLevel`|<span data-ttu-id="f6bed-116">전송 수준에서 메시지를 추적하는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-116">A Boolean value that specifies whether messages are traced at the transport level.</span></span> <span data-ttu-id="f6bed-117">구성 파일에 지정된 모든 필터가 적용되며, 필터와 일치하는 메시지만 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-117">Any filters specified in the config file are applied, and only messages that match the filters are traced.</span></span> <span data-ttu-id="f6bed-118">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-118">The default is `false`.</span></span>|  
|`maxMessagesToLog`|<span data-ttu-id="f6bed-119">로깅할 최대 메시지 수를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-119">A positive integer that specifies the maximum number of messages to log.</span></span> <span data-ttu-id="f6bed-120">기본값은 1000입니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-120">The default is 1000.</span></span>|  
|`maxSizeOfMessageToLog`|<span data-ttu-id="f6bed-121">로깅할 최대 메시지 크기(바이트)를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-121">A positive integer that specifies the maximum size, in bytes, of a message to log.</span></span> <span data-ttu-id="f6bed-122">이 한도를 초과하는 메시지는 로깅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-122">Messages larger than the limit will not be logged.</span></span> <span data-ttu-id="f6bed-123">이 설정은 모든 추적 수준에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-123">This setting affects all trace levels.</span></span> <span data-ttu-id="f6bed-124">기본값은 262144(0x4000)입니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-124">The default is 262144(0x4000).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f6bed-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f6bed-125">Child Elements</span></span>  
  
|<span data-ttu-id="f6bed-126">요소</span><span class="sxs-lookup"><span data-stu-id="f6bed-126">Element</span></span>|<span data-ttu-id="f6bed-127">설명</span><span class="sxs-lookup"><span data-stu-id="f6bed-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f6bed-128">filters</span><span class="sxs-lookup"><span data-stu-id="f6bed-128">filters</span></span>|<span data-ttu-id="f6bed-129">`filters` 요소는 XPath 필터 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-129">The `filters` element holds a collection of XPath filters.</span></span> <span data-ttu-id="f6bed-130">`logMessagesAtTransportLevel`이 `true`로 설정되어 전송 메시지 로깅을 사용할 경우 필터와 일치하는 메시지만 로깅됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-130">When transport message logging is enabled (`logMessagesAtTransportLevel` is `true`), only messages matching the filters will be logged.</span></span><br /><br /> <span data-ttu-id="f6bed-131">필터는 전송 레이어에서만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-131">Filters are applied only at the transport layer.</span></span> <span data-ttu-id="f6bed-132">서비스 수준 및 잘못된 형식의 메시지 로깅은 필터의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-132">Service level and malformed message logging are not affected by filters.</span></span><br /><br /> <span data-ttu-id="f6bed-133">이 요소의 유일한 특성인 `filter`는 XpathFilter입니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-133">The only attribute for this element, `filter`, is an XpathFilter.</span></span><br /><br /> `<filters>     <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">/soap:Envelope</add> </filters>`|  
  
### <a name="parent-elements"></a><span data-ttu-id="f6bed-134">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f6bed-134">Parent Elements</span></span>  
  
|<span data-ttu-id="f6bed-135">요소</span><span class="sxs-lookup"><span data-stu-id="f6bed-135">Element</span></span>|<span data-ttu-id="f6bed-136">설명</span><span class="sxs-lookup"><span data-stu-id="f6bed-136">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f6bed-137">진단</span><span class="sxs-lookup"><span data-stu-id="f6bed-137">diagnostics</span></span>|<span data-ttu-id="f6bed-138">관리자의 런타임 검사 및 제어를 위한 WCF 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-138">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6bed-139">설명</span><span class="sxs-lookup"><span data-stu-id="f6bed-139">Remarks</span></span>  

 <span data-ttu-id="f6bed-140">메시지는 스택에서 서비스, 전송 및 잘못된 형식의 3가지 다른 수준에서 로깅됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-140">Messages are logged at three different levels in the stack: service, transport, and malformed.</span></span> <span data-ttu-id="f6bed-141">각 수준은 별도로 활성화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-141">Each level can be activated separately.</span></span>  
  
 <span data-ttu-id="f6bed-142">XPath 필터를 추가하여 전송 및 서비스 수준에서 특정 메시지를 로깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-142">XPath filters can be added to log specific messages at the transport and service levels.</span></span> <span data-ttu-id="f6bed-143">정의된 필터가 없으면 모든 메시지가 로깅됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-143">If no filters are defined, all messages are logged.</span></span> <span data-ttu-id="f6bed-144">필터는 메시지의 헤더에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-144">Filters are applied only to the headers of the message.</span></span> <span data-ttu-id="f6bed-145">본문은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-145">The body is ignored.</span></span> <span data-ttu-id="f6bed-146">WCF는 성능 향상을 위해 메시지 본문을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-146">WCF ignores the message body to improve performance.</span></span> <span data-ttu-id="f6bed-147">본문의 내용을 기반으로 필터링하려면 해당 작업을 수행하는 필터를 갖춘 사용자 지정 수신기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-147">If you want to filter based on the content of the body, you can create a custom listener with a filter that does so.</span></span>  
  
 <span data-ttu-id="f6bed-148">메시지 추적을 활성화하려면 추적 수신기를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-148">You need to create a trace listener to activate message tracing.</span></span> <span data-ttu-id="f6bed-149">수신기는 <xref:System.Diagnostics> 추적 아키텍처에서 작동하는 수신기일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-149">The listener itself can be any listener that works with the <xref:System.Diagnostics> tracing architecture.</span></span> <span data-ttu-id="f6bed-150">다음 예에서는 이러한 수신기를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6bed-150">The following example demonstrates how to create such a listener.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="f6bed-151">예제</span><span class="sxs-lookup"><span data-stu-id="f6bed-151">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f6bed-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6bed-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- [<span data-ttu-id="f6bed-153">메시지 로깅 구성</span><span class="sxs-lookup"><span data-stu-id="f6bed-153">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
