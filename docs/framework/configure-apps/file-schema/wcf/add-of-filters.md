---
description: '다음에 대 한 자세한 정보:: <add><filters>'
title: <filters>의 <add>
ms.date: 03/30/2017
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
ms.openlocfilehash: 546ff41fddfd8a48e14508e27f09236c67c9abc9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802348"
---
# <a name="add-of-filters"></a><span data-ttu-id="d79c7-103">\<filters>의 \<add></span><span class="sxs-lookup"><span data-stu-id="d79c7-103">\<add> of \<filters></span></span>

<span data-ttu-id="d79c7-104">로깅할 메시지 종류를 지정하는 XPath 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="d79c7-104">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<messageLogging>**](messagelogging.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="d79c7-105">구문</span><span class="sxs-lookup"><span data-stu-id="d79c7-105">Syntax</span></span>  
  
```xml  
<filters>
  <add filter="String" />
</filters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d79c7-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d79c7-106">Attributes and Elements</span></span>  

 <span data-ttu-id="d79c7-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d79c7-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d79c7-108">특성</span><span class="sxs-lookup"><span data-stu-id="d79c7-108">Attributes</span></span>  
  
|<span data-ttu-id="d79c7-109">attribute</span><span class="sxs-lookup"><span data-stu-id="d79c7-109">Attribute</span></span>|<span data-ttu-id="d79c7-110">설명</span><span class="sxs-lookup"><span data-stu-id="d79c7-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d79c7-111">filter</span><span class="sxs-lookup"><span data-stu-id="d79c7-111">filter</span></span>|<span data-ttu-id="d79c7-112">XPath 1.0 식에서 정의하는 XML 문서에 대한 쿼리를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d79c7-112">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="d79c7-113">자세한 내용은 <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d79c7-113">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d79c7-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d79c7-114">Child Elements</span></span>  

 <span data-ttu-id="d79c7-115">없음</span><span class="sxs-lookup"><span data-stu-id="d79c7-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d79c7-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d79c7-116">Parent Elements</span></span>  
  
|<span data-ttu-id="d79c7-117">요소</span><span class="sxs-lookup"><span data-stu-id="d79c7-117">Element</span></span>|<span data-ttu-id="d79c7-118">설명</span><span class="sxs-lookup"><span data-stu-id="d79c7-118">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters.md)|<span data-ttu-id="d79c7-119">로깅할 메시지 종류를 제어하는 데 사용되는 XPath 필터 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d79c7-119">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d79c7-120">설명</span><span class="sxs-lookup"><span data-stu-id="d79c7-120">Remarks</span></span>  

 <span data-ttu-id="d79c7-121">필터는 전송 계층에서만 적용됩니다(`logMessagesAtTransportLevel` = `true`).</span><span class="sxs-lookup"><span data-stu-id="d79c7-121">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="d79c7-122">서비스 수준 및 잘못된 형식의 메시지 로깅은 필터의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d79c7-122">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="d79c7-123">컬렉션에 필터를 추가하려면 `add` 키워드를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d79c7-123">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="d79c7-124">하나 이상의 필터가 정의되면 그 중 최소한 하나의 필터와 일치하는 메시지만 로깅됩니다.</span><span class="sxs-lookup"><span data-stu-id="d79c7-124">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="d79c7-125">정의된 필터가 없으면 모든 메시지가 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="d79c7-125">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="d79c7-126">필터는 모든 XPath 구문을 지원하며, 구성 파일에 표시되는 순서대로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d79c7-126">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="d79c7-127">필터 구문에 오류가 있으면 구성 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d79c7-127">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="d79c7-128">다음은 SOAP 헤더 섹션이 있는 메시지만 기록하는 필터 구성 방법에 대한 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d79c7-128">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d79c7-129">예제</span><span class="sxs-lookup"><span data-stu-id="d79c7-129">Example</span></span>  

 <span data-ttu-id="d79c7-130">다음은 SOAP 헤더 섹션이 있는 메시지만 기록하는 필터 구성 방법에 대한 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d79c7-130">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d79c7-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d79c7-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="d79c7-132">메시지 로깅 구성</span><span class="sxs-lookup"><span data-stu-id="d79c7-132">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
- [\<messageLogging>](messagelogging.md)
