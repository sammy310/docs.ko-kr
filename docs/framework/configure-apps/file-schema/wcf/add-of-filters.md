---
title: <filters>의 <add>
ms.date: 03/30/2017
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
ms.openlocfilehash: 280c516b17a133930bc4b6621a8c9bc7f4781085
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850555"
---
# <a name="add-of-filters"></a><span data-ttu-id="2ec03-102">\<\<필터 > 추가 ></span><span class="sxs-lookup"><span data-stu-id="2ec03-102">\<add> of \<filters></span></span>
<span data-ttu-id="2ec03-103">로깅할 메시지 종류를 지정하는 XPath 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="2ec03-103">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
<span data-ttu-id="2ec03-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2ec03-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2ec03-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2ec03-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2ec03-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<진단 >** ](diagnostics.md)</span><span class="sxs-lookup"><span data-stu-id="2ec03-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)</span></span>\
<span data-ttu-id="2ec03-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<messageLogging >** ](messagelogging.md)</span><span class="sxs-lookup"><span data-stu-id="2ec03-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<messageLogging>**](messagelogging.md)</span></span>\
<span data-ttu-id="2ec03-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<필터 >** ](filters.md)</span><span class="sxs-lookup"><span data-stu-id="2ec03-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters.md)</span></span>\
<span data-ttu-id="2ec03-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**</span><span class="sxs-lookup"><span data-stu-id="2ec03-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ec03-110">구문</span><span class="sxs-lookup"><span data-stu-id="2ec03-110">Syntax</span></span>  
  
```xml  
<filters>
  <add filter="String" />
</filters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ec03-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2ec03-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2ec03-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2ec03-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ec03-113">특성</span><span class="sxs-lookup"><span data-stu-id="2ec03-113">Attributes</span></span>  
  
|<span data-ttu-id="2ec03-114">특성</span><span class="sxs-lookup"><span data-stu-id="2ec03-114">Attribute</span></span>|<span data-ttu-id="2ec03-115">Description</span><span class="sxs-lookup"><span data-stu-id="2ec03-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ec03-116">filter</span><span class="sxs-lookup"><span data-stu-id="2ec03-116">filter</span></span>|<span data-ttu-id="2ec03-117">XPath 1.0 식에서 정의하는 XML 문서에 대한 쿼리를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2ec03-117">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="2ec03-118">자세한 내용은 <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ec03-118">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ec03-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2ec03-119">Child Elements</span></span>  
 <span data-ttu-id="2ec03-120">없음</span><span class="sxs-lookup"><span data-stu-id="2ec03-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ec03-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2ec03-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2ec03-122">요소</span><span class="sxs-lookup"><span data-stu-id="2ec03-122">Element</span></span>|<span data-ttu-id="2ec03-123">설명</span><span class="sxs-lookup"><span data-stu-id="2ec03-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ec03-124">\<필터></span><span class="sxs-lookup"><span data-stu-id="2ec03-124">\<filters></span></span>](filters.md)|<span data-ttu-id="2ec03-125">로깅할 메시지 종류를 제어하는 데 사용되는 XPath 필터 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2ec03-125">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ec03-126">설명</span><span class="sxs-lookup"><span data-stu-id="2ec03-126">Remarks</span></span>  
 <span data-ttu-id="2ec03-127">필터는 전송 계층에서만 적용됩니다(`logMessagesAtTransportLevel` = `true`).</span><span class="sxs-lookup"><span data-stu-id="2ec03-127">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="2ec03-128">서비스 수준 및 잘못된 형식의 메시지 로깅은 필터의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ec03-128">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="2ec03-129">컬렉션에 필터를 추가하려면 `add` 키워드를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="2ec03-129">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="2ec03-130">하나 이상의 필터가 정의되면 그 중 최소한 하나의 필터와 일치하는 메시지만 로깅됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ec03-130">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="2ec03-131">정의된 필터가 없으면 모든 메시지가 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="2ec03-131">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="2ec03-132">필터는 모든 XPath 구문을 지원하며, 구성 파일에 표시되는 순서대로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ec03-132">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="2ec03-133">필터 구문에 오류가 있으면 구성 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2ec03-133">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="2ec03-134">다음은 SOAP 헤더 섹션이 있는 메시지만 기록하는 필터 구성 방법에 대한 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="2ec03-134">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ec03-135">예제</span><span class="sxs-lookup"><span data-stu-id="2ec03-135">Example</span></span>  
 <span data-ttu-id="2ec03-136">다음은 SOAP 헤더 섹션이 있는 메시지만 기록하는 필터 구성 방법에 대한 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="2ec03-136">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2ec03-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="2ec03-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="2ec03-138">메시지 로깅 구성</span><span class="sxs-lookup"><span data-stu-id="2ec03-138">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
- [<span data-ttu-id="2ec03-139">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="2ec03-139">\<messageLogging></span></span>](messagelogging.md)
