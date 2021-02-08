---
description: '다음에 대 한 자세한 정보: WebContentTypeMapper 샘플'
title: WebContentTypeMapper 샘플
ms.date: 03/30/2017
ms.assetid: a4fe59e7-44d8-43c6-a1f8-40c45223adca
ms.openlocfilehash: 274672bb8db1dc845b1cc1ced58b4c4a92232e9b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798149"
---
# <a name="webcontenttypemapper-sample"></a><span data-ttu-id="914e3-103">WebContentTypeMapper 샘플</span><span class="sxs-lookup"><span data-stu-id="914e3-103">WebContentTypeMapper Sample</span></span>

<span data-ttu-id="914e3-104">이 샘플에서는 Windows Communication Foundation (WCF) 메시지 본문 형식에 새 콘텐츠 형식을 매핑하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-104">This sample demonstrates how to map new content types to Windows Communication Foundation (WCF) message body formats.</span></span>  
  
 <span data-ttu-id="914e3-105"><xref:System.ServiceModel.Description.WebHttpEndpoint>요소는 WCF가 동일한 끝점에서 JSON, XML 또는 원시 이진 메시지를 수신할 수 있도록 웹 메시지 인코더에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-105">The <xref:System.ServiceModel.Description.WebHttpEndpoint> element plugs in the Web message encoder, which allows WCF to receive JSON, XML, or raw binary messages at the same endpoint.</span></span> <span data-ttu-id="914e3-106">인코더는 요청의 HTTP 콘텐츠 형식을 확인하여 메시지의 본문 형식을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-106">The encoder determines the body format of the message by looking at the HTTP content-type of the request.</span></span> <span data-ttu-id="914e3-107">이 샘플에서는 콘텐츠 형식과 본문 형식 간의 매핑을 사용자가 제어할 수 있게 하는 <xref:System.ServiceModel.Channels.WebContentTypeMapper> 클래스를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-107">This sample introduces the <xref:System.ServiceModel.Channels.WebContentTypeMapper> class, which allows the user to control the mapping between content type and body format.</span></span>  
  
 <span data-ttu-id="914e3-108">WCF는 콘텐츠 형식에 대 한 기본 매핑 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-108">WCF provides a set of default mappings for content types.</span></span> <span data-ttu-id="914e3-109">예를 들어, `application/json`은  JSON에 매핑되고 `text/xml`은 XML에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-109">For example, `application/json` maps to JSON and `text/xml` maps to XML.</span></span> <span data-ttu-id="914e3-110">JSON 또는 XML에 매핑되지 않는 모든 콘텐츠 형식은 원시 이진 형식에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-110">Any content type that is not mapped to JSON or XML is mapped to raw binary format.</span></span>  
  
 <span data-ttu-id="914e3-111">푸시 스타일 API와 같은 일부 시나리오에서 서비스 개발자는 클라이언트가 반환하는 콘텐츠 형식을 제어하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-111">In some scenarios (for example, push-style APIs), the service developer does not control the content type returned by the client.</span></span> <span data-ttu-id="914e3-112">예를 들어, 클라이언트가 JSON을 `text/javascript` 대신에 `application/json`로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-112">For example, clients might return JSON as `text/javascript` instead of `application/json`.</span></span> <span data-ttu-id="914e3-113">이 경우 서비스 개발자는 다음 샘플 코드와 같이 지정된 콘텐츠 형식을 올바르게 처리하기 위해 <xref:System.ServiceModel.Channels.WebContentTypeMapper>에서 파생되는 형식을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-113">In this case, the service developer must provide a type that derives from <xref:System.ServiceModel.Channels.WebContentTypeMapper> to handle the given content type correctly, as shown in the following sample code.</span></span>  
  
```csharp  
public class JsonContentTypeMapper : WebContentTypeMapper  
{  
    public override WebContentFormat  
               GetMessageFormatForContentType(string contentType)  
    {  
        if (contentType == "text/javascript")  
        {  
            return WebContentFormat.Json;  
        }  
        else  
        {  
            return WebContentFormat.Default;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="914e3-114">이 형식은 <xref:System.ServiceModel.Channels.WebContentTypeMapper.GetMessageFormatForContentType%28System.String%29> 메서드를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-114">The type must override the <xref:System.ServiceModel.Channels.WebContentTypeMapper.GetMessageFormatForContentType%28System.String%29> method.</span></span> <span data-ttu-id="914e3-115">이 메서드는 `contentType` 인수를 평가하고 <xref:System.ServiceModel.Channels.WebContentFormat.Json>, <xref:System.ServiceModel.Channels.WebContentFormat.Xml>, <xref:System.ServiceModel.Channels.WebContentFormat.Raw> 또는 <xref:System.ServiceModel.Channels.WebContentFormat.Default> 값 중 하나를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-115">The method must evaluate the `contentType` argument and return one of the following values: <xref:System.ServiceModel.Channels.WebContentFormat.Json>, <xref:System.ServiceModel.Channels.WebContentFormat.Xml>, <xref:System.ServiceModel.Channels.WebContentFormat.Raw>, or <xref:System.ServiceModel.Channels.WebContentFormat.Default>.</span></span> <span data-ttu-id="914e3-116"><xref:System.ServiceModel.Channels.WebContentFormat.Default> 반환은 기본 웹 메시지 인코더 매핑을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-116">Returning <xref:System.ServiceModel.Channels.WebContentFormat.Default> defers to the default Web message encoder mappings.</span></span> <span data-ttu-id="914e3-117">위의 샘플 코드에서 `text/javascript` 콘텐츠 형식은 JSON에 매핑되고 다른 모든 매핑은 변경되지 않은 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-117">In the previous sample code, the `text/javascript` content type is mapped to JSON, and all other mappings remain unchanged.</span></span>  
  
 <span data-ttu-id="914e3-118">`JsonContentTypeMapper` 클래스를 사용하여 Web.config에서 다음을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-118">To use the `JsonContentTypeMapper` class, use the following in your Web.config:</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <standardEndpoint name="" contentTypeMapper="Microsoft.Samples.WebContentTypeMapper.JsonContentTypeMapper, JsonContentTypeMapper, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="914e3-119">JsonContentTypeMapper 사용을 위한 요구 사항을 확인하려면 위의 구성 파일에서 contentTypeMapper 특성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-119">To verify the requirement for using the JsonContentTypeMapper, remove the contentTypeMapper attribute from the above configuration file.</span></span> <span data-ttu-id="914e3-120">그러면 `text/javascript`를 사용하여 JSON 콘텐츠를 보내려고 할 때 클라이언트 페이지를 로드하는 데 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-120">The client page fails to load when attempting to use `text/javascript` to send JSON content.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="914e3-121">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="914e3-121">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="914e3-122">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-122">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="914e3-123">[Windows Communication Foundation 샘플 빌드](building-the-samples.md)에 설명 된 대로 WebContentTypeMapperSample 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-123">Build the solution WebContentTypeMapperSample.sln as described in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="914e3-124">로 이동 `http://localhost/ServiceModelSamples/JCTMClientPage.htm` 합니다 (프로젝트 디렉터리 내에서 브라우저의 JCTMClientPage.htm 열지 않음).</span><span class="sxs-lookup"><span data-stu-id="914e3-124">Navigate to `http://localhost/ServiceModelSamples/JCTMClientPage.htm` (do not open JCTMClientPage.htm in the browser from within the project directory).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="914e3-125">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="914e3-126">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="914e3-126">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="914e3-127">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="914e3-128">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="914e3-128">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Ajax\WebContentTypeMapper`  
