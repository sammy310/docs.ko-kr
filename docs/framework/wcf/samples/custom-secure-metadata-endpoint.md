---
title: Custom Secure Metadata Endpoint
ms.date: 03/30/2017
ms.assetid: 9e369e99-ea4a-49ff-aed2-9fdf61091a48
ms.openlocfilehash: 6e392f396b62ad2a3d3cda6e7d6ff31f186f0964
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592439"
---
# <a name="custom-secure-metadata-endpoint"></a><span data-ttu-id="deb27-102">Custom Secure Metadata Endpoint</span><span class="sxs-lookup"><span data-stu-id="deb27-102">Custom Secure Metadata Endpoint</span></span>
<span data-ttu-id="deb27-103">이 샘플에서는 비 메타 데이터 교환 바인딩 중 하나를 사용 하는 보안 메타 데이터 끝점을 사용 하 여 서비스를 구현 하는 방법과 이러한 메타 데이터 끝점에서 메타 데이터를 인출 하도록 [ServiceModel Metadata 유틸리티 도구 (svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) 또는 클라이언트를 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-103">This sample demonstrates how to implement a service with a secure metadata endpoint that uses one of the non-metadata exchange bindings, and how to configure [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) or clients to fetch the metadata from such a metadata endpoint.</span></span> <span data-ttu-id="deb27-104">메타데이터 엔드포인트를 노출하는 데 시스템에서 제공한 두 가지 바인딩, mexHttpBinding 및 mexHttpsBinding을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-104">There are two system-provided bindings available for exposing metadata endpoints: mexHttpBinding and mexHttpsBinding.</span></span> <span data-ttu-id="deb27-105">mexHttpBinding은 HTTP를 통해 비보안 방식으로 메타데이터 엔드포인트를 노출하는 데 사용되고,</span><span class="sxs-lookup"><span data-stu-id="deb27-105">mexHttpBinding is used to expose a metadata endpoint over HTTP in a non-secure manner.</span></span> <span data-ttu-id="deb27-106">mexHttpsBinding은 HTTPS를 통해 보안 방식으로 메타데이터 엔드포인트를 노출하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-106">mexHttpsBinding is used to expose a metadata endpoint over HTTPS in a secure manner.</span></span> <span data-ttu-id="deb27-107">이 샘플에서는 <xref:System.ServiceModel.WSHttpBinding>을 사용하여 보안 메타데이터 엔드포인트를 노출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-107">This sample illustrates how to expose a secure metadata endpoint using the <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="deb27-108">바인딩의 보안 설정을 변경하려고 하지만 HTTPS를 사용하지 않으려는 경우 이 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-108">You would want to do this when you want to change the security settings on the binding, but you do not want to use HTTPS.</span></span> <span data-ttu-id="deb27-109">mexHttpsBinding을 사용하면 메타데이터 엔드포인트가 보안되지만 바인딩 설정은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-109">If you use the mexHttpsBinding your metadata endpoint will be secure, but there is no way to modify the binding settings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="deb27-110">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="service"></a><span data-ttu-id="deb27-111">서비스</span><span class="sxs-lookup"><span data-stu-id="deb27-111">Service</span></span>  
 <span data-ttu-id="deb27-112">이 샘플의 서비스에는 두 개의 엔드포인트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-112">The service in this sample has two endpoints.</span></span> <span data-ttu-id="deb27-113">애플리케이션 엔드포인트에서는 인증서를 통한 `ICalculator` 보안 및 `WSHttpBinding`이 설정된 `ReliableSession`에서 `Message` 계약을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-113">The application endpoint serves the `ICalculator` contract on a `WSHttpBinding` with `ReliableSession` enabled and `Message` security using certificates.</span></span> <span data-ttu-id="deb27-114">메타데이터 엔드포인트에서는 보안 설정은 동일하지만 `WSHttpBinding`이 없는 `ReliableSession`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-114">The metadata endpoint also uses `WSHttpBinding`, with the same security settings but with no `ReliableSession`.</span></span> <span data-ttu-id="deb27-115">관련 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-115">Here is the relevant configuration:</span></span>  
  
```xml  
<services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
     <!-- use base address provided by host -->  
     <endpoint address=""  
       binding="wsHttpBinding"  
       bindingConfiguration="Binding2"  
       contract="Microsoft.ServiceModel.Samples.ICalculator" />  
     <endpoint address="mex"  
       binding="wsHttpBinding"  
       bindingConfiguration="Binding1"  
       contract="IMetadataExchange" />  
     </service>  
 </services>  
 <bindings>  
   <wsHttpBinding>  
     <binding name="Binding1">  
       <security mode="Message">  
         <message clientCredentialType="Certificate" />  
       </security>  
     </binding>  
     <binding name="Binding2">  
       <reliableSession inactivityTimeout="00:01:00" enabled="true" />  
       <security mode="Message">  
         <message clientCredentialType="Certificate" />  
       </security>  
     </binding>  
   </wsHttpBinding>  
 </bindings>  
```  
  
 <span data-ttu-id="deb27-116">대부분의 다른 샘플에서는 메타데이터 엔드포인트에 보안되지 않은 기본 `mexHttpBinding`을 사용하지만</span><span class="sxs-lookup"><span data-stu-id="deb27-116">In many of the other samples, the metadata endpoint uses the default `mexHttpBinding`, which is not secure.</span></span> <span data-ttu-id="deb27-117">여기서는 `WSHttpBinding` 보안이 설정된 `Message`을 사용하여 메타데이터를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-117">Here the metadata is secured using `WSHttpBinding` with `Message` security.</span></span> <span data-ttu-id="deb27-118">메타데이터 클라이언트가 이 메타데이터를 검색하려면 일치하는 바인딩으로 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-118">In order for metadata clients to retrieve this metadata, they must be configured with a matching binding.</span></span> <span data-ttu-id="deb27-119">이 샘플에서는 이러한 두 개의 클라이언트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-119">This sample demonstrates two such clients.</span></span>  
  
 <span data-ttu-id="deb27-120">첫 번째 클라이언트는 디자인 타임에 Svcutil.exe를 사용하여 메타데이터를 페치하고 클라이언트 코드 및 구성을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-120">The first client uses Svcutil.exe to fetch the metadata and generate client code and configuration at design time.</span></span> <span data-ttu-id="deb27-121">서비스에서 기본 바인딩이 아닌 바인딩을 메타데이터에 사용하므로 Svcutil.exe 도구는 해당 바인딩을 사용하는 서비스에서 메타데이터를 가져올 수 있도록 특수하게 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-121">Because the service uses a non-default binding for the metadata, the Svcutil.exe tool must be specifically configured so that it can get the metadata from the service using that binding.</span></span>  
  
 <span data-ttu-id="deb27-122">두 번째 클라이언트는 `MetadataResolver`를 사용하여 알려진 계약에 대한 메타데이터를 동적으로 페치한 다음 동적으로 생성된 클라이언트에서 작업을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-122">The second client uses the `MetadataResolver` to dynamically fetch the metadata for a known contract and then invoke operations on the dynamically generated client.</span></span>  
  
## <a name="svcutil-client"></a><span data-ttu-id="deb27-123">Svcutil 클라이언트</span><span class="sxs-lookup"><span data-stu-id="deb27-123">Svcutil client</span></span>  
 <span data-ttu-id="deb27-124">ph x="1" /&gt; 엔드포인트를 호스팅하기 위해 기본 바인딩을 사용할 경우 해당 엔드포인트의 주소와 함께 Svcutil.exe를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-124">When using the default binding to host your `IMetadataExchange` endpoint, you can run Svcutil.exe with the address of that endpoint:</span></span>  
  
```console  
svcutil http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 <span data-ttu-id="deb27-125">그러나 이 샘플에서</span><span class="sxs-lookup"><span data-stu-id="deb27-125">and it works.</span></span> <span data-ttu-id="deb27-126">서버는 기본값이 아닌 엔드포인트를 사용하여 메타데이터를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-126">But in this sample, the server uses a non-default endpoint to host the metadata.</span></span> <span data-ttu-id="deb27-127">따라서 올바른 바인딩을 사용하도록 Svcutil.exe에 지시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-127">So Svcutil.exe must be instructed to use the correct binding.</span></span> <span data-ttu-id="deb27-128">이렇게 하려면 Svcutil.exe.config 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-128">This can be done using a Svcutil.exe.config file.</span></span>  
  
 <span data-ttu-id="deb27-129">Svcutil.exe.config 파일은 클라이언트 끝점 이름과 계약이 추가된다는 것을 제외하면</span><span class="sxs-lookup"><span data-stu-id="deb27-129">The Svcutil.exe.config file looks like a normal client configuration file.</span></span> <span data-ttu-id="deb27-130">일반적인 클라이언트 엔드포인트 이름 및 계약과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-130">The only unusual aspects are the client endpoint name and contract:</span></span>  
  
```xml  
<endpoint name="http"  
          binding="wsHttpBinding"  
          bindingConfiguration="Binding1"  
          behaviorConfiguration="ClientCertificateBehavior"  
          contract="IMetadataExchange" />  
```  
  
 <span data-ttu-id="deb27-131">엔드포인트 이름은 메타데이터가 호스팅된 주소 체계의 이름이어야 하고 엔드포인트 계약은 `IMetadataExchange`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-131">The endpoint name must be the name of the scheme of the address where the metadata is hosted and the endpoint contract must be `IMetadataExchange`.</span></span> <span data-ttu-id="deb27-132">따라서 Svcutil.exe를 다음과 같은 명령줄로 실행하면</span><span class="sxs-lookup"><span data-stu-id="deb27-132">Thus, when Svcutil.exe is run with a command-line such as the following:</span></span>  
  
```console  
svcutil http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 <span data-ttu-id="deb27-133">Svcutil.exe는 "http"라는 엔드포인트와 `IMetadataExchange` 계약을 찾아 메타데이터 엔드포인트와의 통신 교환에 사용할 바인딩 및 동작을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-133">it looks for the endpoint named "http" and contract `IMetadataExchange` to configure the binding and behavior of the communication exchange with the metadata endpoint.</span></span> <span data-ttu-id="deb27-134">샘플에서 Svcutil.exe.config 파일의 나머지 부분은 서버의 메타데이터 엔드포인트 구성과 일치하도록 바인딩 구성 및 동작 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-134">The rest of the Svcutil.exe.config file in the sample specifies the binding configuration and behavior credentials to match the server's configuration of the metadata endpoint.</span></span>  
  
 <span data-ttu-id="deb27-135">Svcutil.exe가 Svcutil.exe.config에서 구성을 선택하려면 이 구성 파일과 동일한 디렉터리에 Svcutil.exe가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-135">In order for Svcutil.exe to pick up the configuration in Svcutil.exe.config, Svcutil.exe must be in the same directory as the configuration file.</span></span> <span data-ttu-id="deb27-136">결과적으로 Svcutil.exe를 해당 설치 위치에서 Svcutil.exe.config 파일이 있는 디렉터리에 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-136">As a result, you must copy Svcutil.exe from its install location to the directory that contains the Svcutil.exe.config file.</span></span> <span data-ttu-id="deb27-137">그런 다음 해당 디렉터리에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-137">Then from that directory, run the following command:</span></span>  
  
```console  
.\svcutil.exe http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 <span data-ttu-id="deb27-138">선행 ". \\ " 이 디렉터리의 Svcutil.exe 복사본 (해당 Svcutil.exe가 있는)이 실행 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-138">The leading ".\\" ensures that the copy of Svcutil.exe in this directory (the one which has a corresponding Svcutil.exe.config) is run.</span></span>  
  
## <a name="metadataresolver-client"></a><span data-ttu-id="deb27-139">MetadataResolver 클라이언트</span><span class="sxs-lookup"><span data-stu-id="deb27-139">MetadataResolver client</span></span>  
 <span data-ttu-id="deb27-140">클라이언트는 계약을 알고 있고 디자인 타임에 메타데이터에 통신하는 방법을 알고 있는 경우 `MetadataResolver`를 사용하여 애플리케이션 엔드포인트의 바인딩과 주소를 동적으로 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-140">If the client knows the contract and how to talk to the metadata at design time, the client can dynamically find out the binding and address of application endpoints using the `MetadataResolver`.</span></span> <span data-ttu-id="deb27-141">이 작업을 보여 주기 위해 이 샘플 클라이언트에서는 `MetadataResolver`를 만들고 구성하여 `MetadataExchangeClient`에 사용되는 바인딩과 자격 증명을 구성하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-141">This sample client demonstrates this, showing how to configure the binding and credentials used by `MetadataResolver` by creating and configuring a `MetadataExchangeClient`.</span></span>  
  
 <span data-ttu-id="deb27-142">Svcutil.exe.config에 표시된 것과 동일한 바인딩 및 인증서 정보를 `MetadataExchangeClient`에서 명령 형식으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-142">The same binding and certificate information that appeared in Svcutil.exe.config can be specified imperatively on the `MetadataExchangeClient`:</span></span>  
  
```csharp  
// Specify the Metadata Exchange binding and its security mode  
WSHttpBinding mexBinding = new WSHttpBinding(SecurityMode.Message);  
mexBinding.Security.Message.ClientCredentialType = MessageCredentialType.Certificate;  
  
// Create a MetadataExchangeClient for retrieving metadata, and set the // certificate details  
MetadataExchangeClient mexClient = new MetadataExchangeClient(mexBinding);  
mexClient.SoapCredentials.ClientCertificate.SetCertificate(    StoreLocation.CurrentUser, StoreName.My,  
    X509FindType.FindBySubjectName, "client.com");  
mexClient.SoapCredentials.ServiceCertificate.Authentication.CertificateValidationMode = X509CertificateValidationMode.PeerOrChainTrust;  
mexClient.SoapCredentials.ServiceCertificate.SetDefaultCertificate(    StoreLocation.CurrentUser, StoreName.TrustedPeople,  
    X509FindType.FindBySubjectName, "localhost");  
```  
  
 <span data-ttu-id="deb27-143">`mexClient`가 구성된 상태에서 원하는 계약을 열거하고 `MetadataResolver`를 사용하여 이러한 계약과 함께 엔드포인트 목록을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-143">With the `mexClient` configured, we can enumerate the contracts we are interested in, and use `MetadataResolver` to fetch a list of endpoints with those contracts:</span></span>  
  
```csharp  
// The contract we want to fetch metadata for  
Collection<ContractDescription> contracts = new Collection<ContractDescription>();  
ContractDescription contract = ContractDescription.GetContract(typeof(ICalculator));  
contracts.Add(contract);  
// Find endpoints for that contract  
EndpointAddress mexAddress = new EndpointAddress(ConfigurationManager.AppSettings["mexAddress"]);  
ServiceEndpointCollection endpoints = MetadataResolver.Resolve(contracts, mexAddress, mexClient);  
```  
  
 <span data-ttu-id="deb27-144">마지막으로 이러한 엔드포인트의 정보를 사용하여 애플리케이션 엔드포인트와 통신하기 위한 채널을 만드는 데 사용되는 `ChannelFactory`의 바인딩과 주소를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-144">Finally we can use the information from those endpoints to initialize the binding and address of a `ChannelFactory` used to create channels to communicate with the application endpoints.</span></span>  
  
```csharp  
ChannelFactory<ICalculator> cf = new ChannelFactory<ICalculator>(endpoint.Binding, endpoint.Address);  
```  
  
 <span data-ttu-id="deb27-145">이 샘플 클라이언트의 요점은 `MetadataResolver`를 사용하는 중이고 메타데이터 교환 통신을 위한 사용자 지정 바인딩이나 동작을 지정해야 할 경우 `MetadataExchangeClient`를 사용하여 이러한 사용자 지정 설정을 지정할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-145">The key point of this sample client is to demonstrate that, if you are using `MetadataResolver`, and you must specify custom bindings or behaviors for the metadata exchange communication, you can use a `MetadataExchangeClient` to specify those custom settings.</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="deb27-146">샘플을 설치하고 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="deb27-146">To set up and build the sample</span></span>  
  
1. <span data-ttu-id="deb27-147">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-147">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="deb27-148">솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](building-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="deb27-148">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="deb27-149">단일 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="deb27-149">To run the sample on the same machine</span></span>  
  
1. <span data-ttu-id="deb27-150">샘플 설치 폴더에서 Setup.bat를 실행하여</span><span class="sxs-lookup"><span data-stu-id="deb27-150">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="deb27-151">이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-151">This installs all the certificates required for running the sample.</span></span> <span data-ttu-id="deb27-152">FindPrivateKey는 [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)에서 setupcerttool을 실행 하 여 설치 되는 도구를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-152">Note that Setup.bat uses the FindPrivateKey.exe tool, which is installed by running setupCertTool.bat from [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="deb27-153">\MetadataResolverClient\bin 또는 \SvcutilClient\bin에서 클라이언트 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-153">Run the client application from \MetadataResolverClient\bin or \SvcutilClient\bin.</span></span> <span data-ttu-id="deb27-154">클라이언트 콘솔 애플리케이션에 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-154">Client activity is displayed on the client console application.</span></span>  
  
3. <span data-ttu-id="deb27-155">클라이언트와 서비스가 통신할 수 없는 경우 [WCF 샘플에 대 한 문제 해결 팁](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="deb27-155">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
4. <span data-ttu-id="deb27-156">샘플 사용을 마치면 Cleanup.bat를 실행하여 인증서를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-156">Remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="deb27-157">다른 보안 샘플에도 동일한 인증서가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-157">Other security samples use the same certificates.</span></span>  
  
#### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="deb27-158">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="deb27-158">To run the sample across machines</span></span>  
  
1. <span data-ttu-id="deb27-159">서버에서 `setup.bat service`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-159">On the server, run `setup.bat service`.</span></span> <span data-ttu-id="deb27-160">`setup.bat`인수를 사용 하 여를 실행 하면 컴퓨터의 정규화 된 `service` 도메인 이름으로 서비스 인증서가 생성 되 고 서비스 인증서가 이름이 .cer 인 파일로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-160">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the machine and exports the service certificate to a file named Service.cer.</span></span>  
  
2. <span data-ttu-id="deb27-161">서버에서 Web.config를 편집하여 새 인증서 이름을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-161">On the server, edit Web.config to reflect the new certificate name.</span></span> <span data-ttu-id="deb27-162">즉, `findValue` 요소의 특성을 [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) 컴퓨터의 정규화 된 도메인 이름으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-162">That is, change the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) element to the fully-qualified domain name of the machine.</span></span>  
  
3. <span data-ttu-id="deb27-163">서비스 디렉터리에서 클라이언트 컴퓨터의 클라이언트 디렉터리로 Service.cer 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-163">Copy the Service.cer file from the service directory to the client directory on the client machine.</span></span>  
  
4. <span data-ttu-id="deb27-164">클라이언트에서 `setup.bat client`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-164">On the client, run `setup.bat client`.</span></span> <span data-ttu-id="deb27-165">`setup.bat`인수를 사용 하 여를 실행 `client` 하면 이름이 Client.com 인 클라이언트 인증서가 만들어지고 클라이언트 인증서가 client.msi 이라는 파일로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-165">Running `setup.bat` with the `client` argument creates a client certificate named Client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
5. <span data-ttu-id="deb27-166">클라이언트 컴퓨터에 있는 `MetadataResolverClient`의 App.config 파일에서 mex 엔드포인트의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-166">In the App.config file of the `MetadataResolverClient` on the client machine, change the address value of the mex endpoint to match the new address of your service.</span></span> <span data-ttu-id="deb27-167">이 작업을 수행하려면 localhost를 서버의 정규화된 도메인 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-167">You do this by replacing localhost with the fully-qualified domain name of the server.</span></span> <span data-ttu-id="deb27-168">또한 metadataResolverClient.cs 파일의 "localhost" 항목을 새 서비스 인증서 이름(서버의 정규화된 도메인 이름)으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-168">Also change the occurrence of "localhost" in the metadataResolverClient.cs file to the new service certificate name (the fully-qualified domain name of the server).</span></span> <span data-ttu-id="deb27-169">SvcutilClient 프로젝트의 App.config에도 동일한 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-169">Do the same thing for the App.config of the SvcutilClient project.</span></span>  
  
6. <span data-ttu-id="deb27-170">클라이언트 디렉터리에서 서버의 서비스 디렉터리로 Client.cer 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-170">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
7. <span data-ttu-id="deb27-171">클라이언트에서 `ImportServiceCert.bat`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-171">On the client, run `ImportServiceCert.bat`.</span></span> <span data-ttu-id="deb27-172">이 작업은 Service.cer 파일의 서비스 인증서를 CurrentUser - TrustedPeople 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-172">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
8. <span data-ttu-id="deb27-173">서버에서 `ImportClientCert.bat`를 실행하여 Client.cer 파일에서 LocalMachine - TrustedPeople 저장소로 클라이언트 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-173">On the server, run `ImportClientCert.bat`, This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
9. <span data-ttu-id="deb27-174">서비스 컴퓨터의 Visual Studio에서 서비스 프로젝트를 빌드하고 웹 브라우저에서 도움말 페이지를 선택하여 해당 서비스 프로젝트가 실행 중인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-174">On the service machine, build the service project in Visual Studio and select the help page in a web browser to verify that it is running.</span></span>  
  
10. <span data-ttu-id="deb27-175">클라이언트 컴퓨터의 VS에서 MetadataResolverClient 또는 SvcutilClient를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-175">On the client machine, run the MetadataResolverClient or the SvcutilClient from VS.</span></span>  
  
    1. <span data-ttu-id="deb27-176">클라이언트와 서비스가 통신할 수 없는 경우 [WCF 샘플에 대 한 문제 해결 팁](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="deb27-176">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="deb27-177">샘플 실행 후 정리를 수행하려면</span><span class="sxs-lookup"><span data-stu-id="deb27-177">To clean up after the sample</span></span>  
  
- <span data-ttu-id="deb27-178">샘플 실행을 완료했으면 샘플 폴더에서 Cleanup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-178">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="deb27-179">다중 컴퓨터 구성에서 이 샘플을 실행할 경우에는 이 스크립트로 서비스 인증서를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-179">This script does not remove service certificates on a client when running this sample across machines.</span></span> <span data-ttu-id="deb27-180">컴퓨터에서 인증서를 사용 하는 WCF (Windows Communication Foundation) 샘플을 실행 한 경우 CurrentUser-비트 사용자 저장소에 설치 된 서비스 인증서를 지워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-180">If you have run Windows Communication Foundation (WCF) samples that use certificates across machines, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="deb27-181">이렇게 하려면 `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-181">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`.</span></span> <span data-ttu-id="deb27-182">예: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="deb27-182">For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="deb27-183">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-183">The samples may already be installed on your machine.</span></span> <span data-ttu-id="deb27-184">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="deb27-184">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="deb27-185">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-185">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="deb27-186">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deb27-186">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Metadata\CustomMexEndpoint`  
