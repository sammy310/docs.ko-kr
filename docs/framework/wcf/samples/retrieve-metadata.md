---
title: 메타데이터 검색
ms.date: 03/30/2017
ms.assetid: e8a6ef8c-a195-495a-a15e-7d92bdf0b28c
ms.openlocfilehash: a7a30fee36b14d0414f2f5bed513c21a694f3484
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255405"
---
# <a name="retrieve-metadata"></a>메타데이터 검색

이 샘플에서는 통신할 엔드포인트를 선택하기 위해 서비스에서 메타데이터를 동적으로 검색하는 클라이언트를 구현하는 방법을 보여 줍니다. 이 샘플은 [시작](getting-started-sample.md)을 기반으로 합니다. 서비스는 두 개의 끝점, 즉 바인딩을 사용 하는 기본 주소에 있는 끝점과 `basicHttpBinding` 바인딩을 사용 하는 {*baseaddress*}/secure의 보안 끝점을 노출 하도록 수정 되었습니다 `wsHttpBinding` . 엔드포인트 주소와 바인딩을 사용하여 클라이언트를 구성하는 대신에 클라이언트는 <xref:System.ServiceModel.Description.MetadataExchangeClient> 클래스를 사용하여 서비스에 대한 메타데이터를 동적으로 검색한 다음 <xref:System.ServiceModel.Description.ServiceEndpointCollection> 클래스를 사용하여 메타데이터를 <xref:System.ServiceModel.Description.WsdlImporter>으로 가져옵니다.  
  
> [!NOTE]
> 이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 클라이언트 애플리케이션은 가져온 <xref:System.ServiceModel.Description.ServiceEndpointCollection>을 사용하여 서비스와 통신하기 위한 클라이언트를 만듭니다. 클라이언트 애플리케이션은 검색된 각 엔드포인트를 반복하고 `ICalculator` 계약을 구현하는 각 엔드포인트와 통신합니다. 다음 샘플 코드와 같이 적절한 주소와 바인딩이 검색된 엔드포인트와 함께 제공되므로 클라이언트는 각 엔드포인트와 통신하도록 구성됩니다.  
  
```csharp
// Create a MetadataExchangeClient for retrieving metadata.  
EndpointAddress mexAddress = new EndpointAddress(ConfigurationManager.AppSettings["mexAddress"]);  
MetadataExchangeClient mexClient = new MetadataExchangeClient(mexAddress);  
  
// Retrieve the metadata for all endpoints using metadata exchange protocol (mex).  
MetadataSet metadataSet = mexClient.GetMetadata();  
  
//Convert the metadata into endpoints.  
WsdlImporter importer = new WsdlImporter(metadataSet);  
ServiceEndpointCollection endpoints = importer.ImportAllEndpoints();  
  
CalculatorClient client = null;  
ContractDescription contract = ContractDescription.GetContract(typeof(ICalculator));  
// Communicate with each endpoint that supports the ICalculator contract.  
foreach (ServiceEndpoint ep in endpoints)  
{  
    if (ep.Contract.Namespace.Equals(contract.Namespace) && ep.Contract.Name.Equals(contract.Name))  
    {  
        // Create a client using the endpoint address and binding.  
        client = new CalculatorClient(ep.Binding, new EndpointAddress(ep.Address.Uri));  
        Console.WriteLine("Communicate with endpoint: ");  
        Console.WriteLine("   AddressPath={0}", ep.Address.Uri.PathAndQuery);  
        Console.WriteLine("   Binding={0}", ep.Binding.Name);  
        // Call operations.  
        DoCalculations(client);  
  
        //Closing the client gracefully closes the connection and cleans up resources.  
        client.Close();  
    }  
}  
```  
  
 클라이언트 콘솔 창에는 주소 경로와 바인딩 이름을 포함하여 각 엔드포인트에 보내진 작업이 표시됩니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1. [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.  
  
2. C #, c + + 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](building-the-samples.md)의 지침을 따르세요.  
  
3. 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.  
  
> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다. 이 샘플은 다음 디렉터리에 있습니다.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\RetrieveMetadata`  
