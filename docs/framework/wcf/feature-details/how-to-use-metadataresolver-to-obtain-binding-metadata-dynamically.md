---
title: '방법: MetadataResolver를 사용하여 동적으로 바인딩 메타데이터 가져오기'
ms.date: 03/30/2017
ms.assetid: 56ffcb99-fff0-4479-aca0-e3909009f605
ms.openlocfilehash: 3fe09699304de42ed00312f50f3b9e0edb20615d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59298931"
---
# <a name="how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically"></a><span data-ttu-id="e45ff-102">방법: MetadataResolver를 사용하여 동적으로 바인딩 메타데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="e45ff-102">How to: Use MetadataResolver to Obtain Binding Metadata Dynamically</span></span>
<span data-ttu-id="e45ff-103">이 항목에서는 <xref:System.ServiceModel.Description.MetadataResolver> 클래스를 사용하여 바인딩 메타데이터를 동적으로 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e45ff-103">This topic shows you how to use the <xref:System.ServiceModel.Description.MetadataResolver> class to dynamically obtain binding metadata.</span></span>  
  
### <a name="to-dynamically-obtain-binding-metadata"></a><span data-ttu-id="e45ff-104">바인딩 메타데이터를 동적으로 가져오려면</span><span class="sxs-lookup"><span data-stu-id="e45ff-104">To dynamically obtain binding metadata</span></span>  
  
1. <span data-ttu-id="e45ff-105">메타데이터 엔드포인트 주소를 사용하여 <xref:System.ServiceModel.EndpointAddress> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e45ff-105">Create an <xref:System.ServiceModel.EndpointAddress> object with the address of the metadata endpoint.</span></span>  
  
    ```  
    EndpointAddress metaAddress  
      = new EndpointAddress(new   Uri("http://localhost:8080/SampleService/mex"));  
    ```  
  
2. <span data-ttu-id="e45ff-106">서비스 유형 및 메타데이터 엔드포인트 주소를 전달하는 <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e45ff-106">Call <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29>, which passes in the service type and the metadata endpoint address.</span></span> <span data-ttu-id="e45ff-107">지정된 계약을 구현하는 엔드포인트의 컬렉션이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e45ff-107">This returns a collection of endpoints that implement the specified contract.</span></span> <span data-ttu-id="e45ff-108">바인딩 정보만 메타데이터에서 가져오고, 계약 정보는 가져오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e45ff-108">Only binding information is imported from the metadata; contract information is not imported.</span></span> <span data-ttu-id="e45ff-109">제공된 계약이 대신 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e45ff-109">The supplied contract is used instead.</span></span>  
  
    ```  
    ServiceEndpointCollection endpoints = MetadataResolver.Resolve(typeof(SampleServiceClient),metaAddress);  
    ```  
  
3. <span data-ttu-id="e45ff-110">서비스 엔드포인트의 컬렉션을 반복하여 필요한 바인딩 정보를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e45ff-110">You can then iterate through the collection of service endpoints to extract the binding information you need.</span></span> <span data-ttu-id="e45ff-111">다음 코드에서는 엔드포인트를 반복하고, 현재 엔드포인트와 연결된 바인딩 및 주소로 전달되는 서비스 클라이언트 개체를 만든 다음 서비스에 대한 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e45ff-111">The following code iterates through the endpoints, creates a service client object that passes in the binding and address associated with the current endpoint, and then calls a method on the service.</span></span>  
  
    ```  
    foreach (ServiceEndpoint point in endpoints)  
    {  
       if (point != null)  
       {  
          // Create a new wcfClient using retrieved endpoints.  
          using (wcfClient = new SampleServiceClient(point.Binding, point.Address))  
          {  
             Console.WriteLine(  
               wcfClient.SampleMethod("Client used the "  
               + point.Address.ToString() + " address."));  
          }  
      }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e45ff-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="e45ff-112">See also</span></span>

- [<span data-ttu-id="e45ff-113">메타데이터</span><span class="sxs-lookup"><span data-stu-id="e45ff-113">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)
