---
description: '자세한 정보: 메시지 로그 보기'
title: 메시지 로그 보기
ms.date: 03/30/2017
ms.assetid: 3012fa13-f650-45fb-aaea-c5cca8c7d372
ms.openlocfilehash: c640b2c3793839be4a31123701865fa944eaebc8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99758036"
---
# <a name="viewing-message-logs"></a><span data-ttu-id="69017-103">메시지 로그 보기</span><span class="sxs-lookup"><span data-stu-id="69017-103">Viewing Message Logs</span></span>

<span data-ttu-id="69017-104">이 항목에서는 메시지 로그를 볼 수 있는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="69017-104">This topic describes how you can view message logs.</span></span>  
  
## <a name="viewing-message-logs-in-the-service-trace-viewer"></a><span data-ttu-id="69017-105">Service Trace Viewer에서 메시지 로그 보기</span><span class="sxs-lookup"><span data-stu-id="69017-105">Viewing Message Logs in the Service Trace Viewer</span></span>  

 <span data-ttu-id="69017-106">메시지는 WCF에서 처리 될 때 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69017-106">A message will be transformed as it is processed by WCF.</span></span> <span data-ttu-id="69017-107">그러므로 기록되는 메시지는 기록되는 시점의 메시지 내용만을 반영하며, 통신 중의 내용은 반영하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69017-107">Therefore, a message being logged reflects only the message's content at the point it was logged, not the content on the wire.</span></span>  
  
 <span data-ttu-id="69017-108">메시지 로깅 출력은 메시지 전송 형식과 관계가 없으므로 메시지 로깅은 항상 디코딩된 메시지를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="69017-108">Since the output of message logging has no relationship to the transfer format of the message, message logging always outputs the decoded message.</span></span> <span data-ttu-id="69017-109">메시지 로깅을 올바로 구성한 경우 메시지는 일반 텍스트로 기록되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69017-109">If you have configured message logging properly, any logged message should be in plain text.</span></span> <span data-ttu-id="69017-110">예를 들어 기록된 메시지 형식(일반 텍스트)은 이진 메시지 인코더 사용에 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69017-110">For example, the format (plain text) of the logged messages is not affected by the usage of a binary message encoder.</span></span>  
  
 <span data-ttu-id="69017-111">XmlWriterTraceListener의 출력은 XML 단편의 시퀀스가 포함된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="69017-111">The output of the XmlWriterTraceListener is a file that contains a sequence of XML fragments.</span></span> <span data-ttu-id="69017-112">해당 파일은 유효한 XML 파일이 아님을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69017-112">You should be aware that the file is not a valid XML file.</span></span> <span data-ttu-id="69017-113">[서비스 추적 뷰어 도구 (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) 를 사용 하 여 메시지 로그 파일을 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="69017-113">It is recommended that you use the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) to view the message log files.</span></span> <span data-ttu-id="69017-114">이 도구를 사용 하는 방법에 대 한 자세한 내용은 [서비스 추적 뷰어를 사용 하 여 상호 관련 된 추적 보기 및 문제 해결](./tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="69017-114">For more information on how to use this tool, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](./tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span></span>  
  
 <span data-ttu-id="69017-115">서비스 추적 뷰어에서 메시지는 **메시지** 탭에 나열 됩니다. 오류의 심각도에 따라 처리 오류가 발생 했거나 관련 된 메시지는 노란색 (경고 수준) 또는 빨간색 (오류 수준)으로 강조 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69017-115">In the Service Trace Viewer, messages are listed in the **Message** tab. Messages that have caused, or are related to, a processing error are highlighted in yellow (warning level) or red (error level), depending on the severity of the error.</span></span> <span data-ttu-id="69017-116">해당 메시지를 두 번 클릭하면 처리 요청에 따라 메시지 추적이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="69017-116">Double-clicking on the message brings up the message trace in the context of the processing request.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69017-117">메시지에 헤더가 없으면 `<header/>` 태그가 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69017-117">If a message has no header, no `<header/>` tag is logged.</span></span>  
  
## <a name="viewing-messages-logged-by-a-client-a-relay-and-a-service"></a><span data-ttu-id="69017-118">클라이언트, 릴레이 및 서비스에 의해 기록된 메시지 보기</span><span class="sxs-lookup"><span data-stu-id="69017-118">Viewing Messages Logged by a Client, a Relay, and a Service</span></span>  

 <span data-ttu-id="69017-119">사용자 환경에는 메시지를 릴레이로 보내고, 이후에 해당 메시지를 서비스로 전달하는 클라이언트가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69017-119">Your environment may contain a client, which sends a message to a relay, that subsequently forwards the message to the service.</span></span> <span data-ttu-id="69017-120">세 위치 모두에서 메시지 로깅을 사용 하도록 설정 하 고 [서비스 추적 뷰어 도구 (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) 에서 세 메시지 로그가 모두 동시에 표시 되는 경우 메시지 로그 교환은 잘못 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69017-120">When message logging is enabled on all three locations, and all three message logs are viewed in [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) simultaneously, the message log exchanges will be incorrectly rendered.</span></span> <span data-ttu-id="69017-121">이는 메시지 헤더의 `CorrelationId` 및 `ActivityId`가 모든 전송-수신 쌍에 대해 고유하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="69017-121">This is because the `CorrelationId` and `ActivityId` in the Message header are not unique for every send-receive pair.</span></span>  
  
 <span data-ttu-id="69017-122">다음 방법 중 하나를 사용하여 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69017-122">You can use either one of the following methods to resolve this problem.</span></span>  
  
- <span data-ttu-id="69017-123">[서비스 추적 뷰어 도구 (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) 에서는 언제 든 지 세 개의 메시지 로그 중 두 개를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="69017-123">Only view two of the three message logs in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) at any time.</span></span>  
  
- <span data-ttu-id="69017-124">[서비스 추적 뷰어 도구 (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) 에서 세 로그를 모두 동시에 확인 해야 하는 경우에는 새 인스턴스를 만들어 릴레이 서비스를 수정할 수 있습니다 <xref:System.ServiceModel.Channels.Message> .</span><span class="sxs-lookup"><span data-stu-id="69017-124">If you must view all three logs in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) at the same time, you can modify the relay service by creating a new <xref:System.ServiceModel.Channels.Message> instance.</span></span> <span data-ttu-id="69017-125">이 인스턴스는 들어오는 메시지 본문의 복사본이어야 하며, `ActivityId` 및 `Action` 헤더를 제외한 모든 헤더여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69017-125">This instance should be a copy of the body of the incoming message, plus all the headers except for the `ActivityId` and `Action` headers.</span></span> <span data-ttu-id="69017-126">다음 예제 코드에서는 이 작업을 수행하는 방법에 대해 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="69017-126">The following example code demonstrates how to do this.</span></span>  
  
```csharp
Message outgoingMessage = Message.CreateMessage(incomingMessage.Version, incomingMessage.Headers.Action, incomingMessage.GetReaderAtBodyContents());  
  
for (int i = 0; i < incomingMessage.Headers.Count; i++)  
{  
   if (incomingMessage.Headers[i].Name.Equals("ActivityId", StringComparison.InvariantCultureIgnoreCase) ||  
incomingMessage.Headers[i].Name.Equals("Action", StringComparison.InvariantCultureIgnoreCase))  
   {  
      continue;  
    }  
    outgoingMessage.Headers.CopyHeaderFrom(incomingMessage, i);  
}  
```  
  
## <a name="exceptional-cases-for-inaccurate-message-logging-content"></a><span data-ttu-id="69017-127">부정확한 메시지 로깅 콘텐츠의 예외 사례</span><span class="sxs-lookup"><span data-stu-id="69017-127">Exceptional Cases for Inaccurate Message Logging Content</span></span>  

 <span data-ttu-id="69017-128">다음 조건에서는 기록되는 메시지가 통신상에 표시되는 8진수 스트림의 정확한 표현이 아닐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69017-128">Under the following conditions, messages being logged might not be the exact representation of the octet stream present on the wire.</span></span>  
  
- <span data-ttu-id="69017-129">BasicHttpBinding의 경우에는 들어오는 메시지에 대해 봉투 헤더가 /addressing/none 네임스페이스에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="69017-129">For BasicHttpBinding, envelope headers are logged for the incoming messages in the /addressing/none namespace.</span></span>  
  
- <span data-ttu-id="69017-130">공백은 일치 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69017-130">White spaces can be mismatched.</span></span>  
  
- <span data-ttu-id="69017-131">들어오는 메시지의 경우 빈 요소가 다르게 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69017-131">For incoming messages, empty elements can be represented differently.</span></span> <span data-ttu-id="69017-132">예를 들어 \<tag> \</tag> 대신\<tag/></span><span class="sxs-lookup"><span data-stu-id="69017-132">For example, \<tag>\</tag> instead of  \<tag/></span></span>  
  
- <span data-ttu-id="69017-133">알려진 PII 로깅이 기본값 또는 명시적인 설정인 enableLoggingKnownPii="true"에 의해서 사용하지 않도록 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="69017-133">When known PII logging is disabled either by default or explicit setting enableLoggingKnownPii="true".</span></span>  
  
- <span data-ttu-id="69017-134">UTF-8로 변환하기 위해 인코딩을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="69017-134">Encoding is enabled for transforming to UTF-8.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69017-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69017-135">See also</span></span>

- [<span data-ttu-id="69017-136">Service Trace Viewer 도구(SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="69017-136">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../service-trace-viewer-tool-svctraceviewer-exe.md)
- [<span data-ttu-id="69017-137">Service Trace Viewer를 사용하여 상호 관련된 추적 보기 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="69017-137">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](./tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="69017-138">메시지 로깅</span><span class="sxs-lookup"><span data-stu-id="69017-138">Message Logging</span></span>](message-logging.md)
