---
description: 다음에 대해 자세히 알아보세요. <filters>
title: <filters>
ms.date: 03/30/2017
ms.assetid: 37a87222-ec78-4728-8105-9ca1bd961f0c
ms.openlocfilehash: c66dd07c91e78d1ae6e10790014c3d1b25e5538d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664602"
---
# \<filters>

<span data-ttu-id="f20da-102">`filters` 요소는 메시지 로깅 제어에 사용되는 XPath 필터 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="f20da-102">The `filters` element holds a collection of XPath filters used to control what kind of message is logged.</span></span>

<span data-ttu-id="f20da-103">필터는 전송 계층에서만 적용됩니다(`logMessagesAtTransportLevel` = `true`).</span><span class="sxs-lookup"><span data-stu-id="f20da-103">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="f20da-104">서비스 수준 및 잘못된 형식의 메시지 로깅은 필터의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f20da-104">Service level and malformed message logging are not affected by filters.</span></span>

<span data-ttu-id="f20da-105">컬렉션에 필터를 추가하려면 `add` 키워드를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f20da-105">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="f20da-106">하나 이상의 필터가 정의되면 그 중 최소한 하나의 필터와 일치하는 메시지만 로깅됩니다.</span><span class="sxs-lookup"><span data-stu-id="f20da-106">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="f20da-107">정의된 필터가 없으면 모든 메시지가 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="f20da-107">If no filter is defined, all messages pass through.</span></span>

<span data-ttu-id="f20da-108">필터는 모든 XPath 구문을 지원하며, 구성 파일에 표시되는 순서대로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f20da-108">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="f20da-109">필터 구문에 오류가 있으면 구성 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f20da-109">A syntactically incorrect filter results in a configuration exception.</span></span>

<span data-ttu-id="f20da-110">다음은 SOAP 헤더 섹션이 있는 메시지만 기록하는 필터 구성 방법에 대한 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="f20da-110">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>
  
```xml  
<messageLogging logEntireMessage="true"
                logMalformedMessages="true"
                logMessagesAtServiceLevel="true"
                logMessagesAtTransportLevel="true"
                maxMessagesToLog="420">
  <filters>
    <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
      /soap:Envelope/soap:Headers
    </add>
  </filters>
</messageLogging>
```  
  
## <a name="see-also"></a><span data-ttu-id="f20da-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f20da-111">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElementCollection>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="f20da-112">메시지 로깅 구성</span><span class="sxs-lookup"><span data-stu-id="f20da-112">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
- [\<messageLogging>](messagelogging.md)
