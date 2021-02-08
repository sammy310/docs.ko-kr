---
description: '자세히 알아보기: 방법: 사용자 지정 WSDL 가져오기'
title: '방법: 사용자 지정 WSDL 가져오기'
ms.date: 03/30/2017
ms.assetid: ddc3718d-ce60-44f6-92af-a5c67477dd99
ms.openlocfilehash: f21e5cace532bd6d20d409f297480f65bb23cbf4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780741"
---
# <a name="how-to-import-custom-wsdl"></a><span data-ttu-id="755a6-103">방법: 사용자 지정 WSDL 가져오기</span><span class="sxs-lookup"><span data-stu-id="755a6-103">How to: Import Custom WSDL</span></span>

<span data-ttu-id="755a6-104">이 항목에서는 사용자 지정 WSDL을 가져오는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="755a6-104">This topic describes how to import custom WSDL.</span></span> <span data-ttu-id="755a6-105">사용자 지정 WSDL을 처리하려면 <xref:System.ServiceModel.Description.IWsdlImportExtension> 인터페이스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="755a6-105">To handle the custom WSDL, you must implement the <xref:System.ServiceModel.Description.IWsdlImportExtension> interface.</span></span>  
  
### <a name="to-import-custom-wsdl"></a><span data-ttu-id="755a6-106">사용자 지정 WSDL을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="755a6-106">To import custom WSDL</span></span>  
  
1. <span data-ttu-id="755a6-107"><xref:System.ServiceModel.Description.IWsdlImportExtension>를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="755a6-107">Implement <xref:System.ServiceModel.Description.IWsdlImportExtension>.</span></span> <span data-ttu-id="755a6-108"><xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29> 메서드를 구현하여 메타데이터를 가져오기 전에 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="755a6-108">Implement the <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29> method to modify the metadata before it is imported.</span></span> <span data-ttu-id="755a6-109">ph x="1" /&gt; 및 <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> 메서드를 구현하여 메타데이터에서 가져온 계약과 엔드포인트를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="755a6-109">Implement the <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> and <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> methods to modify contracts and endpoints imported from the metadata.</span></span> <span data-ttu-id="755a6-110">가져온 계약이나 엔드포인트에 액세스하려면 해당 컨텍스트 개체(<xref:System.ServiceModel.Description.WsdlContractConversionContext> 또는 <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="755a6-110">To access the imported contract or endpoint, use the corresponding context object (<xref:System.ServiceModel.Description.WsdlContractConversionContext> or <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>):</span></span>  
  
    ```csharp
    public class WsdlDocumentationImporter : IWsdlImportExtension
    {
        public void ImportContract(WsdlImporter importer, WsdlContractConversionContext context)
        {
            // Contract documentation
            if (context.WsdlPortType.Documentation != null)
            {
                context.Contract.Behaviors.Add(new WsdlDocumentationImporter(context.WsdlPortType.Documentation));
            }
            // Operation documentation
            foreach (Operation operation in context.WsdlPortType.Operations)
            {
                if (operation.Documentation != null)
                {
                    OperationDescription operationDescription = context.Contract.Operations.Find(operation.Name);
                    if (operationDescription != null)
                    {
                        operationDescription.Behaviors.Add(new WsdlDocumentationImporter(operation.Documentation));
                    }
                }
            }
        }

        public void BeforeImport(ServiceDescriptionCollection wsdlDocuments, XmlSchemaSet xmlSchemas, ICollection<XmlElement> policy)
        {
            Console.WriteLine("BeforeImport called.");
        }

        public void ImportEndpoint(WsdlImporter importer, WsdlEndpointConversionContext context)
        {
            Console.WriteLine("ImportEndpoint called.");
        }
    }
    ```
  
2. <span data-ttu-id="755a6-111">사용자 지정 WSDL 가져오기를 사용하도록 클라이언트 애플리케이션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="755a6-111">Configure the client application to use the custom WSDL importer.</span></span> <span data-ttu-id="755a6-112">Svcutil.exe를 사용하는 경우 Svcutil.exe(Svcutil.exe.config)의 구성 파일에 이 구성을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="755a6-112">Note that if you are using Svcutil.exe, you should add this configuration to the configuration file for Svcutil.exe (Svcutil.exe.config):</span></span>  
  
    ```xml  
    <system.serviceModel>  
          <client>  
            <endpoint
              address="http://localhost:8000/Fibonacci"
              binding="wsHttpBinding"  
              contract="IFibonacci"  
            />  
            <metadata>  
              <wsdlImporters>  
                <extension type="Microsoft.WCF.Documentation.WsdlDocumentationImporter, WsdlDocumentation" />  
              </wsdlImporters>  
            </metadata>  
          </client>  
        </system.serviceModel>  
    ```  
  
3. <span data-ttu-id="755a6-113">새 <xref:System.ServiceModel.Description.WsdlImporter> 인스턴스(가져올 WSDL 문서를 포함하는 <xref:System.ServiceModel.Description.MetadataSet> 인스턴스에 전달)를 만들고 <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="755a6-113">Create a new <xref:System.ServiceModel.Description.WsdlImporter> instance (passing in the <xref:System.ServiceModel.Description.MetadataSet> instance that contains the WSDL documents that you want to import), and call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>:</span></span>  
  
    ```csharp
    WsdlImporter importer = new WsdlImporter(metaDocs);
    System.Collections.ObjectModel.Collection<ContractDescription> contracts = importer.ImportAllContracts();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="755a6-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="755a6-114">See also</span></span>

- [<span data-ttu-id="755a6-115">메타데이터</span><span class="sxs-lookup"><span data-stu-id="755a6-115">Metadata</span></span>](../feature-details/metadata.md)
- [<span data-ttu-id="755a6-116">메타데이터 내보내기 및 가져오기</span><span class="sxs-lookup"><span data-stu-id="755a6-116">Exporting and Importing Metadata</span></span>](../feature-details/exporting-and-importing-metadata.md)
- [<span data-ttu-id="755a6-117">사용자 지정 WSDL 게시</span><span class="sxs-lookup"><span data-stu-id="755a6-117">Custom WSDL Publication</span></span>](../samples/custom-wsdl-publication.md)
