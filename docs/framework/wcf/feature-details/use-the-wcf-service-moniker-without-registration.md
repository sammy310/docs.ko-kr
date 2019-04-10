---
title: '방법: 등록하지 않고 Windows Communication Foundation 서비스 모니커 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], service monikers without registration
ms.assetid: ee3cf5c0-24f0-4ae7-81da-73a60de4a1a8
ms.openlocfilehash: be4798663d0b39301ec496df45a4a7a5bf9c88e5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203979"
---
# <a name="how-to-use-the-windows-communication-foundation-service-moniker-without-registration"></a><span data-ttu-id="436bd-102">방법: 등록하지 않고 Windows Communication Foundation 서비스 모니커 사용</span><span class="sxs-lookup"><span data-stu-id="436bd-102">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>
<span data-ttu-id="436bd-103">연결 하 고 Windows Communication Foundation (WCF) 서비스와 통신을 WCF 클라이언트 응용 프로그램 서비스 주소, 바인딩 구성 및 서비스 계약 세부 정보가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="436bd-103">To connect to and communicate with a Windows Communication Foundation (WCF) service, a WCF client application must have the details of the service address, the binding configuration, and the service contract.</span></span>  
  
 <span data-ttu-id="436bd-104">일반적으로 WCF 서비스 모니커에 필수 특성 형식의 이전 등록을 통해 필수 계약 가져오지만 적합 하지 않은 경우 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="436bd-104">The WCF service moniker typically obtains the required contract through prior registration of the required attribute types, but there might be cases where this is not feasible.</span></span> <span data-ttu-id="436bd-105">등록 대신 모니커는 `wsdl` 매개 변수 사용, 메타데이터 교환 또는 `mexAddress` 매개 변수 사용을 통해 계약 정의를 WSDL(웹 서비스 기술 언어) 문서의 형태로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="436bd-105">In place of registration, the moniker can obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document, through the use of the `wsdl` parameter or through Metadata Exchange, through the use of the `mexAddress` parameter.</span></span>  
  
 <span data-ttu-id="436bd-106">이 경우 웹 서비스 상호 작용을 통해 일부 셀 값을 계산하는 Excel 스프레드시트를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="436bd-106">This enables scenarios such as the distribution of an Excel spreadsheet where some of the cell values are calculated through Web service interactions.</span></span> <span data-ttu-id="436bd-107">이 시나리오에서는 문서를 열 수 있는 모든 클라이언트에서 서비스 계약 어셈블리를 등록하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="436bd-107">In this scenario, it might not be feasible to register the service contract assembly on all clients that might open the document.</span></span> <span data-ttu-id="436bd-108">`wsdl` 매개 변수 또는 `mexAddress` 매개 변수가 자체 포함된 솔루션을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="436bd-108">The `wsdl` parameter or the `mexAddress` parameter enables a self-contained solution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="436bd-109">요청 및 응답 훼손 또는 스푸핑을 방지하려면 상호 인증을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="436bd-109">Mutual authentication must be used to protect against request and response tampering or spoofing.</span></span> <span data-ttu-id="436bd-110">특히 클라이언트는 응답하는 메타 데이터 교환 엔드포인트가 신뢰할 수 있는 당사자가 맞는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="436bd-110">Specifically, it is important for clients to be assured that the Metadata Exchange endpoint that is responding is the intended trusted party.</span></span>  
  
## <a name="example"></a><span data-ttu-id="436bd-111">예제</span><span class="sxs-lookup"><span data-stu-id="436bd-111">Example</span></span>  
 <span data-ttu-id="436bd-112">이 예제에서는 MEX 계약에서 서비스 모니커를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="436bd-112">This example shows the use of the service moniker with a MEX contract.</span></span> <span data-ttu-id="436bd-113">다음 계약에서 서비스는 wsHttpBinding을 통해 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="436bd-113">A service with the following contract is exposed with a wsHttpBinding.</span></span>  
  
```  
using System.ServiceModel;  
  
...  
  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Demo")]  
public interface IAffiliate  
{  
    [OperationContract]  
    bool NewAffiliate(string ID, string company, string fullname, string accountsCode);  
    [OperationContract]  
    bool RemoveAffiliate(string ID);  
    [OperationContract]  
    double RevenueCheckMonthly(ref string ID);  
    [OperationContract]  
    double RevenueCheckTotal(ref string ID);  
}  
```  
  
 <span data-ttu-id="436bd-114">다음 예제 모니커 문자열 원격 서비스에 대 한 WCF 클라이언트 생성에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="436bd-114">To construct a WCF client for the remote service the following example moniker string can be used.</span></span>  
  
```  
service4:mexAddress="http://servername/Affiliates/service.svc/mex",  
address="http://servername/Affiliates/service.svc",  
contract=IAffiliate, contractNamespace=http://Microsoft.ServiceModel.Demo,  
binding=WSHttpBinding_IAffiliate, bindingNamespace=http://tempuri.org/  
```  
  
 <span data-ttu-id="436bd-115">클라이언트 응용 프로그램을 실행하는 동안 클라이언트는 제공된 `WS-MetadataExchange`를 사용하여 `mexAddress`를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="436bd-115">During the execution of the client application, the client performs a `WS-MetadataExchange` with the provided `mexAddress`.</span></span> <span data-ttu-id="436bd-116">그러면 다양한 서비스에 대한 주소, 바인딩 및 계약 정보가 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="436bd-116">This might return the address, binding and contract details for a number of services.</span></span> <span data-ttu-id="436bd-117">`address`, `contract`, `contractNamespace`, `binding` 및 `bindingNamespace` 매개 변수는 필요한 서비스를 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="436bd-117">The `address`, `contract`, `contractNamespace`, `binding` and `bindingNamespace` parameters are used to identify the intended service.</span></span> <span data-ttu-id="436bd-118">이러한 매개 변수 일치 된 모니커를 적절 한 계약 정의 사용 하 여 WCF 클라이언트 생성 후 다음를 호출 하려면 WCF 클라이언트를 사용 하 여 형식화 된 계약에서와 마찬가지로 합니다.</span><span class="sxs-lookup"><span data-stu-id="436bd-118">Once those parameters have been matched, the moniker constructs a WCF client with the appropriate contract definition and calls can then be made using the WCF client, as with the typed contract.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="436bd-119">모니커 형식이 잘못되었거나 서비스를 사용할 수 없는 경우 `GetObject`를 호출하면 "구문이 잘못되었습니다."라는 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="436bd-119">If the moniker is malformed or if the service is unavailable, the call to `GetObject` returns an error saying "Invalid Syntax".</span></span> <span data-ttu-id="436bd-120">이 오류가 발생하면 사용하고 있는 모니커가 올바르고 서비스를 사용할 수 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="436bd-120">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="436bd-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="436bd-121">See also</span></span>

- [<span data-ttu-id="436bd-122">방법: 서비스 모니커 등록 및 구성</span><span class="sxs-lookup"><span data-stu-id="436bd-122">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)
