---
title: 관리되는 애플리케이션에서의 호스팅
ms.date: 03/30/2017
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
ms.openlocfilehash: 0f220b3eb249a9615024adbd798db49ea94376eb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289943"
---
# <a name="hosting-in-a-managed-application"></a><span data-ttu-id="c1ac7-102">관리되는 애플리케이션에서의 호스팅</span><span class="sxs-lookup"><span data-stu-id="c1ac7-102">Hosting in a Managed Application</span></span>

<span data-ttu-id="c1ac7-103">WCF (Windows Communication Foundation) 서비스는 모든 .NET Framework 응용 프로그램에서 호스팅될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ac7-103">Windows Communication Foundation (WCF) services can be hosted in any .NET Framework application.</span></span> <span data-ttu-id="c1ac7-104">자체 호스팅 서비스는 배포하는 데 최소한의 인프라를 필요로 하기 때문에 가장 유연한 호스팅 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="c1ac7-104">Self-hosting services is the most flexible hosting option because it requires the least infrastructure to deploy.</span></span> <span data-ttu-id="c1ac7-105">그러나 관리 되는 응용 프로그램은 인터넷 정보 서비스 (IIS) 및 Windows 서비스와 같은 WCF의 다른 호스팅 옵션에 대 한 고급 호스팅 및 관리 기능을 제공 하지 않기 때문에 가장 강력한 호스팅 옵션 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ac7-105">However, it is also the least robust hosting option, because managed applications do not provide the advanced hosting and management features of other hosting options in WCF, such as Internet Information Services (IIS) and Windows services.</span></span>  
  
 <span data-ttu-id="c1ac7-106">자체 호스팅 서비스를 만들려면 <xref:System.ServiceModel.ServiceHost>의 인스턴스를 만들고 열어, 여기서 서비스의 메시지 수신 대기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ac7-106">To create a self-hosted service, create and open an instance of the <xref:System.ServiceModel.ServiceHost>, which starts a service listening for messages.</span></span> <span data-ttu-id="c1ac7-107">자세한 내용은 [방법: 관리 되는 응용 프로그램에서 WCF 서비스 호스팅](../how-to-host-a-wcf-service-in-a-managed-application.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c1ac7-107">For more information, see [How to: Host a WCF Service in a Managed Application](../how-to-host-a-wcf-service-in-a-managed-application.md).</span></span>  
  
 <span data-ttu-id="c1ac7-108">계약을 정의 하 고, 계약을 구현 하 고, 관리 되는 응용 프로그램 내에서 서비스를 호스트 하는 방법에 대 한 전체 예제는 [시작 자습서](../getting-started-tutorial.md) 및 [자체 호스트](../samples/self-host.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c1ac7-108">For a complete example on how to define a contract, implement the contract, and host a service inside of a managed application see the [Getting Started Tutorial](../getting-started-tutorial.md) and the [Self-Host](../samples/self-host.md).</span></span>  
  
 <span data-ttu-id="c1ac7-109">다음 단원에서는 이 호스팅 옵션을 사용하는 일반적인 시나리오에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ac7-109">The following sections describe common scenarios that use this hosting option.</span></span>  
  
## <a name="console-applications"></a><span data-ttu-id="c1ac7-110">콘솔 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="c1ac7-110">Console Applications</span></span>  

 <span data-ttu-id="c1ac7-111">자체 호스팅을 사용 하는 일반적인 시나리오는 콘솔 응용 프로그램 내에서 실행 되는 WCF 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="c1ac7-111">Common scenarios that self-hosting enables are WCF services running inside console applications.</span></span> <span data-ttu-id="c1ac7-112">콘솔 응용 프로그램 내에서 WCF 서비스를 호스트 하는 것은 일반적으로 서비스의 개발 단계에서 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ac7-112">Hosting a WCF service inside a console application is typically useful during the development phase of the service.</span></span> <span data-ttu-id="c1ac7-113">이 경우 쉽게 디버깅을 수행할 수 있으며, 애플리케이션 내에서 발생하는 상황을 확인하기 위한 추적 정보를 손쉽게 얻을 수 있으며, 새 위치에 서비스를 복사하여 이동하기 용이합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ac7-113">This makes them easy to debug, easy to get trace information from to find out what is happening inside of the application, and easy to move around by copying them to new locations.</span></span>  
  
## <a name="rich-client-applications"></a><span data-ttu-id="c1ac7-114">리치 클라이언트 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="c1ac7-114">Rich Client Applications</span></span>  

 <span data-ttu-id="c1ac7-115">자체 호스팅을 사용 하는 다른 일반적인 시나리오는 Windows Presentation Foundation (WPF) 또는 Windows Forms (WinForms)를 기반으로 하는 클라이언트 응용 프로그램 등 다양 한 클라이언트 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="c1ac7-115">Other common scenarios that self-hosting enables are rich client applications, such as those based on Windows Presentation Foundation (WPF) or Windows Forms (WinForms).</span></span> <span data-ttu-id="c1ac7-116">이 호스팅 옵션을 사용 하면 WPF 및 WinForms 응용 프로그램과 같은 리치 클라이언트 응용 프로그램에서 외부 대상과 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ac7-116">This hosting option also makes it easy for rich client applications, such as WPF and WinForms applications, to communicate with the outside world.</span></span> <span data-ttu-id="c1ac7-117">예를 들어, 사용자 인터페이스에 WPF를 사용 하 고 다른 클라이언트가이 서비스에 연결 하 여 정보를 공유할 수 있도록 하는 WCF 서비스를 호스트 하는 피어 투 피어 공동 작업 클라이언트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ac7-117">For example, a peer-to-peer collaboration client that uses WPF for its user interface and also hosts a WCF service that allows other clients to connect to it and share information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ac7-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1ac7-118">See also</span></span>

- [<span data-ttu-id="c1ac7-119">서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="c1ac7-119">Hosting Services</span></span>](../hosting-services.md)
- [<span data-ttu-id="c1ac7-120">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="c1ac7-120">Getting Started Tutorial</span></span>](../getting-started-tutorial.md)
