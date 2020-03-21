---
title: 메시지 수준의 프로그래밍으로 JSON으로 serialize
ms.date: 03/30/2017
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
ms.openlocfilehash: 36459dbc0ddee883678a98a27f9abb74fde78e86
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184493"
---
# <a name="serializing-in-json-with-message-level-programming"></a><span data-ttu-id="ebfa4-102">메시지 수준의 프로그래밍으로 JSON으로 serialize</span><span class="sxs-lookup"><span data-stu-id="ebfa4-102">Serializing in Json with Message Level Programming</span></span>
<span data-ttu-id="ebfa4-103">WCF는 JSON 형식의 데이터 serialize를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ebfa4-103">WCF supports serializing data in JSON format.</span></span> <span data-ttu-id="ebfa4-104">이 항목에서는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 사용하여 WCF가 형식을 serialize하도록 하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ebfa4-104">This topic describes how to tell WCF to serialize your types using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
## <a name="typed-message-programming"></a><span data-ttu-id="ebfa4-105">형식화된 메시지 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="ebfa4-105">Typed Message Programming</span></span>  
 <span data-ttu-id="ebfa4-106">서비스 작업에 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 또는 <xref:System.ServiceModel.Web.WebGetAttribute>가 적용되면 <xref:System.ServiceModel.Web.WebInvokeAttribute>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebfa4-106">The <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> is used when the <xref:System.ServiceModel.Web.WebGetAttribute> or the <xref:System.ServiceModel.Web.WebInvokeAttribute> is applied to a service operation.</span></span> <span data-ttu-id="ebfa4-107">두 특성을 사용하여 `RequestFormat` 및 `ResponseFormat`을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebfa4-107">Both of these attributes allow you to specify the `RequestFormat` and `ResponseFormat`.</span></span> <span data-ttu-id="ebfa4-108">요청 및 응답에 JSON을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebfa4-108">To use JSON for requests and responses.</span></span> <span data-ttu-id="ebfa4-109">이 두 가지를 `WebMessageFormat.Json`모두 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ebfa4-109">set both of these to `WebMessageFormat.Json`.</span></span>  <span data-ttu-id="ebfa4-110">JSON을 사용하려면 <xref:System.ServiceModel.WebHttpBinding>을 자동으로 구성하는 을 사용해야 합니다. <xref:System.ServiceModel.Description.WebHttpBehavior></span><span class="sxs-lookup"><span data-stu-id="ebfa4-110">In order to use JSON, you must use the <xref:System.ServiceModel.WebHttpBinding>, which automatically configures the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span> <span data-ttu-id="ebfa4-111">WCF 직렬화에 대한 자세한 내용은 [직렬화 및 직렬화](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebfa4-111">For more information about WCF serialization, see [Serialization and Deserialization](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md).</span></span> <span data-ttu-id="ebfa4-112">JSON 및 WCF에 대한 자세한 내용은 [서비스 스테이션 - WCF를 사용하여 RESTful 서비스에 대한 소개를](https://docs.microsoft.com/archive/msdn-magazine/2009/january/service-station-an-introduction-to-restful-services-with-wcf)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebfa4-112">For more information about JSON and WCF, see [Service Station - An Introduction To RESTful Services With WCF](https://docs.microsoft.com/archive/msdn-magazine/2009/january/service-station-an-introduction-to-restful-services-with-wcf).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ebfa4-113">JSON을 사용하려면 SOAP 통신을 지원하지 않는 <xref:System.ServiceModel.WebHttpBinding> 및 <xref:System.ServiceModel.Description.WebHttpBehavior>를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebfa4-113">Using JSON requires use of <xref:System.ServiceModel.WebHttpBinding> and <xref:System.ServiceModel.Description.WebHttpBehavior> which do not support SOAP communication.</span></span> <span data-ttu-id="ebfa4-114">Visual Studio의 <xref:System.ServiceModel.WebHttpBinding> 서비스 참조 추가 기능 또는 svcutil 명령줄 도구를 사용하여 클라이언트 쪽 프록시를 생성할 수 없도록 서비스 메타데이터 노출을 지원하지 않는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="ebfa4-114">Services that communicate with the <xref:System.ServiceModel.WebHttpBinding> do not support exposing service metadata so you will not be able to use Visual Studio’s Add Service Reference functionality or the svcutil command-line tool to generate a client-side proxy.</span></span> <span data-ttu-id="ebfa4-115">프로그래밍 방식으로 서비스를 호출하는 방법에 대한 <xref:System.ServiceModel.WebHttpBinding>자세한 내용은 [WCF를](https://docs.microsoft.com/archive/blogs/pedram/how-to-consume-rest-services-with-wcf)사용하여 REST 서비스를 사용하는 방법을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebfa4-115">For more information how you can programmatically call services that use <xref:System.ServiceModel.WebHttpBinding>, see [How to Consume REST Services with WCF](https://docs.microsoft.com/archive/blogs/pedram/how-to-consume-rest-services-with-wcf).</span></span>  
  
## <a name="untyped-message-programming"></a><span data-ttu-id="ebfa4-116">형식화되지 않은 메시지 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="ebfa4-116">Untyped Message Programming</span></span>  
 <span data-ttu-id="ebfa4-117">형식화되지 않은 메시기 개체로 직접 작업할 때는 형식화되지 않은 메시지의 속성을 명시적으로 설정하여 JSON으로 serialize해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebfa4-117">When working directly with untyped Message objects, you must explicitly set the properties on the untyped message to serialize it as JSON.</span></span> <span data-ttu-id="ebfa4-118">다음 코드 조각에서는 이를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ebfa4-118">The following code snippet shows how to do this.</span></span>  
  
```csharp
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
```  
  
## <a name="see-also"></a><span data-ttu-id="ebfa4-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ebfa4-119">See also</span></span>

- [<span data-ttu-id="ebfa4-120">AJAX 통합 및 JSON 지원</span><span class="sxs-lookup"><span data-stu-id="ebfa4-120">AJAX Integration and JSON Support</span></span>](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="ebfa4-121">독립 실행형 JSON Serialization</span><span class="sxs-lookup"><span data-stu-id="ebfa4-121">Stand-Alone JSON Serialization</span></span>](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)
- [<span data-ttu-id="ebfa4-122">JSON 직렬화</span><span class="sxs-lookup"><span data-stu-id="ebfa4-122">JSON Serialization</span></span>](../../../../docs/framework/wcf/samples/json-serialization.md)
