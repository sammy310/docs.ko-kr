---
description: '자세한 정보: 방법: 사용자 지정 WS-Metadata Exchange 바인딩 구성'
title: '방법: 사용자 지정 WS-Metadata Exchange 바인딩 구성'
ms.date: 03/30/2017
helpviewer_keywords:
- WS-Metadata Exchange [WCF]
- WS-Metadata Exchange [WCF], configuring a custom binding
ms.assetid: cdba4d73-da64-4805-bc56-9822becfd1e4
ms.openlocfilehash: ae9d1932e7539d25c117a98bd130d1def8e691fe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743735"
---
# <a name="how-to-configure-a-custom-ws-metadata-exchange-binding"></a><span data-ttu-id="defdd-103">방법: 사용자 지정 WS-Metadata Exchange 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="defdd-103">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>

<span data-ttu-id="defdd-104">이 문서에서는 사용자 지정 WS-Metadata exchange 바인딩을 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="defdd-104">This article explains how to configure a custom WS-Metadata exchange binding.</span></span> <span data-ttu-id="defdd-105">WCF (Windows Communication Foundation)에는 네 개의 시스템 정의 메타 데이터 바인딩이 포함 되어 있지만 원하는 바인딩을 사용 하 여 메타 데이터를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="defdd-105">Windows Communication Foundation (WCF) includes four system-defined metadata bindings, but you can publish metadata using any binding you want.</span></span> <span data-ttu-id="defdd-106">이 문서에서는를 사용 하 여 메타 데이터를 게시 하는 방법을 보여 줍니다 `wsHttpBinding` .</span><span class="sxs-lookup"><span data-stu-id="defdd-106">This article shows you how to publish metadata using the `wsHttpBinding`.</span></span> <span data-ttu-id="defdd-107">이 바인딩은 메타데이터를 보안 방법으로 노출하는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="defdd-107">This binding gives you the option of exposing metadata in a secure way.</span></span> <span data-ttu-id="defdd-108">이 문서의 코드는 [시작](../samples/getting-started-sample.md)을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="defdd-108">The code in this article is based on the [Getting Started](../samples/getting-started-sample.md).</span></span>  
  
### <a name="using-a-configuration-file"></a><span data-ttu-id="defdd-109">구성 파일 사용</span><span class="sxs-lookup"><span data-stu-id="defdd-109">Using a configuration file</span></span>  
  
1. <span data-ttu-id="defdd-110">서비스의 구성 파일에서 `serviceMetadata` 태그를 포함하는 서비스 동작을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="defdd-110">In the service's configuration file, add a service behavior that contains the `serviceMetadata` tag:</span></span>  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
           <serviceMetadata httpGetEnabled="True"/>  
         </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
2. <span data-ttu-id="defdd-111">이 새 동작을 참조하는 서비스 태그에 `behaviorConfiguration` 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="defdd-111">Add a `behaviorConfiguration` attribute to the service tag that references this new behavior:</span></span>  
  
    ```xml  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior" />
    ```  
  
3. <span data-ttu-id="defdd-112">mex를 지정하는 메타데이터 엔드포인트를 주소로, `wsHttpBinding`을 바인딩으로, <xref:System.ServiceModel.Description.IMetadataExchange>를 계약으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="defdd-112">Add a metadata endpoint specifying mex as the address, `wsHttpBinding` as the binding, and <xref:System.ServiceModel.Description.IMetadataExchange> as the contract:</span></span>  
  
    ```xml  
    <endpoint address="mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange" />  
    ```  
  
4. <span data-ttu-id="defdd-113">메타 데이터 교환 끝점이 제대로 작동 하는지 확인 하려면 클라이언트 구성 파일에 끝점 태그를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="defdd-113">To verify the metadata exchange endpoint is working correctly, add an endpoint tag in the client configuration file:</span></span>  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
5. <span data-ttu-id="defdd-114">클라이언트의 Main() 메서드에서 새 <xref:System.ServiceModel.Description.MetadataExchangeClient> 인스턴스를 만들고, 해당 <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> 속성을 `true`로 설정하고, <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>를 호출한 다음 반환된 메타데이터 컬렉션을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="defdd-114">In the client's Main() method, create a new <xref:System.ServiceModel.Description.MetadataExchangeClient> instance, set its <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> property to `true`, call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> and then iterate through the collection of metadata returned:</span></span>  
  
    ```csharp
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
### <a name="configuring-by-code"></a><span data-ttu-id="defdd-115">코드로 구성</span><span class="sxs-lookup"><span data-stu-id="defdd-115">Configuring by code</span></span>  
  
1. <span data-ttu-id="defdd-116"><xref:System.ServiceModel.WSHttpBinding> 바인딩 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="defdd-116">Create a <xref:System.ServiceModel.WSHttpBinding> binding instance:</span></span>  
  
    ```csharp  
    WSHttpBinding binding = new WSHttpBinding();  
    ```  
  
2. <span data-ttu-id="defdd-117"><xref:System.ServiceModel.ServiceHost> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="defdd-117">Create a <xref:System.ServiceModel.ServiceHost> instance:</span></span>  
  
    ```csharp  
    ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress);  
    ```  
  
3. <span data-ttu-id="defdd-118">서비스 엔드포인트를 추가하고 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 인스턴스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="defdd-118">Add a service endpoint and add a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance:</span></span>  
  
    ```csharp  
    serviceHost.AddServiceEndpoint(typeof(ICalculator), binding, baseAddress);  
    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();  
    smb.HttpGetEnabled = true;  
    serviceHost.Description.Behaviors.Add(smb);  
    ```  
  
4. <span data-ttu-id="defdd-119">앞에서 만든 <xref:System.ServiceModel.WSHttpBinding>을 지정하여 메타데이터 교환 엔드포인트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="defdd-119">Add a metadata exchange endpoint, specifying the <xref:System.ServiceModel.WSHttpBinding> created earlier:</span></span>  
  
    ```csharp  
    serviceHost.AddServiceEndpoint(typeof(IMetadataExchange), binding, mexAddress);  
    ```  
  
5. <span data-ttu-id="defdd-120">메타데이터 교환 엔드포인트가 올바로 작동하고 있는지 확인하려면 클라이언트 구성 파일에 엔드포인트 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="defdd-120">To verify that the metadata exchange endpoint is working correctly, add an endpoint tag in the client configuration file:</span></span>  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
6. <span data-ttu-id="defdd-121">클라이언트의 Main() 메서드에서 새 <xref:System.ServiceModel.Description.MetadataExchangeClient> 인스턴스를 만들고, 해당 <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> 속성을 `true`로 설정하고, <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>를 호출한 다음 반환된 메타데이터 컬렉션을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="defdd-121">In the client's Main() method, create a new <xref:System.ServiceModel.Description.MetadataExchangeClient> instance, set the <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> property to `true`, call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> and then iterate through the collection of metadata returned:</span></span>  
  
    ```csharp  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="defdd-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="defdd-122">See also</span></span>

- [<span data-ttu-id="defdd-123">메타데이터 게시 동작</span><span class="sxs-lookup"><span data-stu-id="defdd-123">Metadata Publishing Behavior</span></span>](../samples/metadata-publishing-behavior.md)
- [<span data-ttu-id="defdd-124">메타데이터 검색</span><span class="sxs-lookup"><span data-stu-id="defdd-124">Retrieve Metadata</span></span>](../samples/retrieve-metadata.md)
- [<span data-ttu-id="defdd-125">메타데이터</span><span class="sxs-lookup"><span data-stu-id="defdd-125">Metadata</span></span>](../feature-details/metadata.md)
- [<span data-ttu-id="defdd-126">메타데이터 게시</span><span class="sxs-lookup"><span data-stu-id="defdd-126">Publishing Metadata</span></span>](../feature-details/publishing-metadata.md)
- [<span data-ttu-id="defdd-127">메타데이터 엔드포인트 게시</span><span class="sxs-lookup"><span data-stu-id="defdd-127">Publishing Metadata Endpoints</span></span>](../publishing-metadata-endpoints.md)
