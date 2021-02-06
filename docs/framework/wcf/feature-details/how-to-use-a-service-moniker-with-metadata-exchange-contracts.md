---
description: '자세히 알아보기: 방법: 메타 데이터 교환 계약을 통해 서비스 모니커 사용'
title: '방법: 메타데이터 교환 계약을 통해 서비스 모니커 사용'
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: 220132a10cb637be9e3724232d0ddaf80a13551a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643100"
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a><span data-ttu-id="3fd50-103">방법: 메타데이터 교환 계약을 통해 서비스 모니커 사용</span><span class="sxs-lookup"><span data-stu-id="3fd50-103">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>

<span data-ttu-id="3fd50-104">몇 가지 새로운 WCF 서비스를 개발한 후 스크립트나 Visual Basic 6.0 응용 프로그램에서 이러한 서비스를 호출할 수 있도록 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd50-104">After developing some new WCF services, you may decide that you want to be able to call these services from a script or a Visual Basic 6.0 application.</span></span> <span data-ttu-id="3fd50-105">한 가지 방법은 WCF 클라이언트 어셈블리를 생성 하 고, 어셈블리를 COM에 등록 하 고, GAC에 어셈블리를 설치한 다음 Visual Basic 코드에서 COM 형식을 참조 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3fd50-105">One method would be to generate a WCF client assembly, register the assembly with COM, install the assembly in the GAC, and then reference the COM types from your Visual Basic code.</span></span> <span data-ttu-id="3fd50-106">응용 프로그램을 배포 하는 경우 WCF 클라이언트 어셈블리도 함께 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd50-106">When you distribute the application, you will have to distribute the WCF Client assembly as well.</span></span> <span data-ttu-id="3fd50-107">사용자는 WCF 클라이언트 어셈블리를 COM에 등록하고 GAC에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd50-107">The user will then have to register the WCF client assembly with COM and place it in the GAC.</span></span> <span data-ttu-id="3fd50-108">Wcf COM Interop를 사용 하면 WCF 클라이언트 어셈블리에 의존 하지 않고 동일한 서비스 호출을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd50-108">WCF COM Interop also allows you to make the same service calls without relying on a WCF client assembly.</span></span> <span data-ttu-id="3fd50-109">WCF 모니커를 사용 하면 서비스 모니커가 서비스에 대 한 형식 정보를 추출 하는 데 사용 하는 Mex (metadata exchange) 끝점 URI를 지정 하 여 COM 호환 언어 (Visual Basic, VBScript, Visual Basic for Applications (VBA) 등)에서 WCF 서비스를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd50-109">The WCF moniker allows you to call any WCF service from any COM-compatible language (Visual Basic, VBScript, Visual Basic for Applications (VBA), and so on) by specifying a metadata exchange (Mex) endpoint URI that the service moniker uses to extract type information about the service.</span></span> <span data-ttu-id="3fd50-110">이 항목에서는 Mex 끝점을 지정 하는 WCF 모니커를 사용 하 여 WCF 시작 샘플을 호출 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd50-110">This topic describes how to call the Getting Started WCF sample using a WCF moniker that specifies a Mex endpoint.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3fd50-111">WCF 클라이언트 어셈블리에 의해 정의 된 형식은 실제로 인스턴스화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fd50-111">The types defined by the WCF client assembly are never actually instantiated.</span></span> <span data-ttu-id="3fd50-112">어셈블리는 메타데이터에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fd50-112">The assembly is used only for metadata.</span></span>  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a><span data-ttu-id="3fd50-113">서비스 모니커에 Mex 주소 사용</span><span class="sxs-lookup"><span data-stu-id="3fd50-113">Using the service moniker with a Mex address</span></span>  
  
1. <span data-ttu-id="3fd50-114">시작 샘플을 빌드하고 Internet Explorer를 사용 하 여 해당 URL ()로 이동 하 여 `http://localhost/ServiceModelSamples/Service.svc` 서비스가 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd50-114">Build the Getting Started sample and use Internet Explorer to browse to its URL (`http://localhost/ServiceModelSamples/Service.svc`) to ensure that the service is working.</span></span>  
  
2. <span data-ttu-id="3fd50-115">다음 코드가 포함된 Visual Basic 스크립트 또는 Visual Basic 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3fd50-115">Create a Visual Basic script or Visual Basic application that contains the following code:</span></span>  
  
    ```vb
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3. <span data-ttu-id="3fd50-116">Visual Basic 애플리케이션 또는 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd50-116">Run the Visual Basic application or script.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3fd50-117">모니커가 서비스에서 메타데이터를 읽을 수 있도록 하려면 호출 중인 서비스가 Mex 엔드포인트를 노출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fd50-117">The service you are calling must expose a Mex endpoint for the moniker to be able to read the metadata from the service.</span></span> <span data-ttu-id="3fd50-118">자세한 내용은 [방법: 구성 파일을 사용 하 여 서비스에 대 한 메타 데이터 게시](how-to-publish-metadata-for-a-service-using-a-configuration-file.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3fd50-118">For more information, see [How to: Publish Metadata for a Service Using a Configuration File](how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3fd50-119">모니커의 형식이 잘못되었거나 서비스를 사용할 수 없는 경우 `GetObject`를 호출하면 "구문이 잘못되었습니다."라는 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fd50-119">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span>  <span data-ttu-id="3fd50-120">이 오류가 발생하면 사용하고 있는 모니커가 올바르고 서비스를 사용할 수 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="3fd50-120">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fd50-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3fd50-121">See also</span></span>

- [<span data-ttu-id="3fd50-122">방법: 등록하지 않고 Windows Communication Foundation 서비스 모니커 사용</span><span class="sxs-lookup"><span data-stu-id="3fd50-122">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](use-the-wcf-service-moniker-without-registration.md)
- [<span data-ttu-id="3fd50-123">방법: WSDL 계약을 통해 서비스 모니커 사용</span><span class="sxs-lookup"><span data-stu-id="3fd50-123">How to: Use a Service Moniker with WSDL Contracts</span></span>](how-to-use-a-service-moniker-with-wsdl-contracts.md)
