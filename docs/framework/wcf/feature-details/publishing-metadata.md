---
title: 메타데이터 게시
description: WCF 서비스가 하나 이상의 메타 데이터 끝점을 게시 하 여 메타 데이터를 게시 하 여 표준 프로토콜을 통해 메타 데이터를 사용할 수 있도록 하는 방법을 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WCF], publishing
ms.assetid: 3a56831a-cabc-45c0-bd02-12e2e9bd7313
ms.openlocfilehash: 3ea2377870a37e7dee6f4253503d70167d021a0d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244732"
---
# <a name="publishing-metadata"></a><span data-ttu-id="77457-103">메타데이터 게시</span><span class="sxs-lookup"><span data-stu-id="77457-103">Publishing Metadata</span></span>

<span data-ttu-id="77457-104">WCF (Windows Communication Foundation) 서비스는 하나 이상의 메타 데이터 끝점을 게시 하 여 메타 데이터를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="77457-104">Windows Communication Foundation (WCF) services publish metadata by publishing one or more metadata endpoints.</span></span> <span data-ttu-id="77457-105">서비스 메타데이터를 게시하면 WS-MetadataExchange(MEX) 및 HTTP/GET 요청과 같이 표준화된 프로토콜을 통해 메타데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77457-105">Publishing service metadata makes the metadata available using standardized protocols, such as WS-MetadataExchange (MEX) and HTTP/GET requests.</span></span> <span data-ttu-id="77457-106">메타데이터 엔드포인트는 주소, 바인딩 및 계약에 포함된 다른 서비스 엔드포인트와 유사하며 구성 또는 명령 코드를 통해 서비스 호스트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77457-106">Metadata endpoints are similar to other service endpoints in that they have an address, a binding, and a contract, and they can be added to a service host through configuration or imperative code.</span></span>  
  
## <a name="publishing-metadata-endpoints"></a><span data-ttu-id="77457-107">메타데이터 엔드포인트 게시</span><span class="sxs-lookup"><span data-stu-id="77457-107">Publishing Metadata Endpoints</span></span>  

 <span data-ttu-id="77457-108">WCF 서비스에 대 한 메타 데이터 끝점을 게시 하려면 먼저 서비스 동작을 서비스에 추가 해야 합니다 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> .</span><span class="sxs-lookup"><span data-stu-id="77457-108">To publish metadata endpoints for a WCF service, you first must add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> service behavior to the service.</span></span> <span data-ttu-id="77457-109">ph x="1" /&gt; 인스턴스를 추가하면 서비스가 메타데이터 엔드포인트를 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77457-109">Adding a <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> instance allows your service to expose metadata endpoints.</span></span> <span data-ttu-id="77457-110">ph x="1" /&gt; 서비스 동작을 추가하면 MEX 프로토콜을 지원하거나 HTTP/GET 요청에 응답하는 메타데이터 엔드포인트를 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77457-110">Once you add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> service behavior, you can then expose metadata endpoints that support the MEX protocol or that respond to HTTP/GET requests.</span></span>  
  
 <span data-ttu-id="77457-111"><xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>는 <xref:System.ServiceModel.Description.WsdlExporter>를 사용하여 서비스의 모든 서비스 엔드포인트에 대한 메타데이터를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="77457-111">The <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> uses a <xref:System.ServiceModel.Description.WsdlExporter> to export metadata for all service endpoints in your service.</span></span> <span data-ttu-id="77457-112">서비스에서 메타 데이터를 내보내는 방법에 대 한 자세한 내용은 [메타 데이터 내보내기 및 가져오기](exporting-and-importing-metadata.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="77457-112">For more information about exporting metadata from a service, see [Exporting and Importing Metadata](exporting-and-importing-metadata.md).</span></span>  
  
 <span data-ttu-id="77457-113"><xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>  A <xref:System.ServiceModel.Description.ServiceMetadataExtension> 인스턴스를 서비스 호스트에 대한 확장으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="77457-113">The <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> adds a <xref:System.ServiceModel.Description.ServiceMetadataExtension> instance as an extension to your service host.</span></span> <span data-ttu-id="77457-114"><xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType>은 메타데이터 게시 프로토콜에 대한 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="77457-114">The <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> provides the implementation for the metadata publishing protocols.</span></span> <span data-ttu-id="77457-115">또한 <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType>을 통해 <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A?displayProperty=nameWithType> 속성에 액세스하여 서비스 메타데이터를 런타임에 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77457-115">You can also use the <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> to get the service's metadata at runtime by accessing the <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A?displayProperty=nameWithType> property.</span></span>  
  
### <a name="mex-metadata-endpoints"></a><span data-ttu-id="77457-116">MEX 메타데이터 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="77457-116">MEX Metadata Endpoints</span></span>  

 <span data-ttu-id="77457-117">MEX 프로토콜을 사용하는 메타데이터 엔드포인트를 추가하려면 `IMetadataExchange` 서비스 계약을 사용하는 서비스 호스트에 서비스 엔드포인트를 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="77457-117">To add metadata endpoints that use the MEX protocol, add service endpoints to your service host that use the `IMetadataExchange` service contract.</span></span> <span data-ttu-id="77457-118">WCF에는 <xref:System.ServiceModel.Description.IMetadataExchange> wcf 프로그래밍 모델의 일부로 사용할 수 있는이 서비스 계약 이름을 포함 하는 인터페이스가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77457-118">WCF includes an <xref:System.ServiceModel.Description.IMetadataExchange> interface with this service contract name that you can use as part of the WCF programming model.</span></span> <span data-ttu-id="77457-119">WS-MetadataExchange 끝점 또는 MEX 끝점은 <xref:System.ServiceModel.Description.MetadataExchangeBindings> Svcutil.exe와 같은 WCF 도구에서 사용 하는 기본 바인딩과 일치 하도록 정적 팩터리 메서드가 클래스에서 노출 하는 네 가지 기본 바인딩 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77457-119">WS-MetadataExchange endpoints, or MEX endpoints, can use one of the four default bindings that the static factory methods expose on the <xref:System.ServiceModel.Description.MetadataExchangeBindings> class to match the default bindings used by WCF tools such as Svcutil.exe.</span></span> <span data-ttu-id="77457-120">또한 사용자 지정 바인딩을 사용하여 MEX 메타데이터 엔드포인트를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77457-120">You can also configure MEX metadata endpoints using your own custom binding.</span></span>  
  
### <a name="http-get-metadata-endpoints"></a><span data-ttu-id="77457-121">HTTP GET 메타데이터 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="77457-121">HTTP GET Metadata Endpoints</span></span>  

 <span data-ttu-id="77457-122">HTTP/GET 요청에 응답하는 서비스에 메타데이터 엔드포인트를 추가하려면 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A>의 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="77457-122">To add a metadata endpoint to your service that responds to HTTP/GET requests, set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> to `true`.</span></span> <span data-ttu-id="77457-123">또한 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>의 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> 속성을 `true`로 설정하여 HTTPS를 사용하는 메타데이터 엔드포인트를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77457-123">You can also configure a metadata endpoint that uses HTTPS by setting the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> property on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> to `true`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="77457-124">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="77457-124">In This Section</span></span>  

 [<span data-ttu-id="77457-125">방법: 구성 파일을 사용하여 서비스에 대한 메타데이터 게시</span><span class="sxs-lookup"><span data-stu-id="77457-125">How to: Publish Metadata for a Service Using a Configuration File</span></span>](how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 <span data-ttu-id="77457-126">클라이언트에서 쿼리 문자열을 사용 하 여 WS-MetadataExchange 또는 HTTP/GET 요청을 사용 하 여 메타 데이터를 검색할 수 있도록 WCF 서비스에서 메타 데이터를 게시 하도록 구성 하는 방법을 보여 줍니다 `?wsdl` .</span><span class="sxs-lookup"><span data-stu-id="77457-126">Demonstrates how to configure a WCF service to publish metadata so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
 [<span data-ttu-id="77457-127">방법: 코드를 사용하여 서비스에 대한 메타데이터 게시</span><span class="sxs-lookup"><span data-stu-id="77457-127">How to: Publish Metadata for a Service Using Code</span></span>](how-to-publish-metadata-for-a-service-using-code.md)  
 <span data-ttu-id="77457-128">클라이언트에서 쿼리 문자열을 사용 하 여 WS-MetadataExchange 또는 HTTP/GET 요청을 사용 하 여 메타 데이터를 검색할 수 있도록 코드에서 WCF 서비스에 대 한 메타 데이터 게시를 사용 하도록 설정 하는 방법을 보여 줍니다 `?wsdl` .</span><span class="sxs-lookup"><span data-stu-id="77457-128">Demonstrates how to enable metadata publishing for a WCF service in code so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="77457-129">참고</span><span class="sxs-lookup"><span data-stu-id="77457-129">Reference</span></span>  

 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
  
 <xref:System.ServiceModel.Description.IMetadataExchange>  
  
 <xref:System.ServiceModel.Description.ServiceMetadataExtension>  
  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings>  
  
## <a name="see-also"></a><span data-ttu-id="77457-130">참조</span><span class="sxs-lookup"><span data-stu-id="77457-130">See also</span></span>

- [<span data-ttu-id="77457-131">메타데이터 내보내기 및 가져오기</span><span class="sxs-lookup"><span data-stu-id="77457-131">Exporting and Importing Metadata</span></span>](exporting-and-importing-metadata.md)
