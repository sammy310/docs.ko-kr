---
title: WCF 개발 도구 사용
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 82bb7e225492bcdba4d2e611de405a09571355c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183076"
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="57efc-102">WCF 개발 도구 사용</span><span class="sxs-lookup"><span data-stu-id="57efc-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="57efc-103">이 섹션에서는 WCFservice 개발에 도움이 되는 Visual Studio 개발 도구에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="57efc-103">This section describes the Visual Studio development tools that can assist you in developing your WCFservice.</span></span>  
  
 <span data-ttu-id="57efc-104">Visual Studio 템플릿을 기반으로 사용하여 자체 서비스를 신속하게 빌드한 다음 WCF 서비스 자동 호스트 및 WCF 테스트 클라이언트를 사용하여 서비스를 디버깅하고 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57efc-104">You can use the Visual Studio templates as a foundation to quickly build your own service, then use WCF Service Auto Host and WCF Test Client to debug and test your service.</span></span> <span data-ttu-id="57efc-105">이러한 도구를 함께 사용하면 디버그 및 테스트를 원활하고 빠르게 수행할 수 있으며 초기 단계에서 호스팅 모델에 주력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57efc-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  

 > [!NOTE]
 > <span data-ttu-id="57efc-106">Visual Studio 2017부터 WCF 개발 도구는 기본적으로 설치되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57efc-106">Starting with Visual Studio 2017, the WCF development tools are not installed by default.</span></span> <span data-ttu-id="57efc-107">이러한 기능을 사용하려면 Visual Studio 설치 관리자에서 Windows 통신 기반 구성 요소가 선택되었는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57efc-107">In order to use these features, you must ensure the Windows Communication Foundation component is selected in the Visual Studio installer.</span></span>
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="57efc-108">WCF 개발자 도구</span><span class="sxs-lookup"><span data-stu-id="57efc-108">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="57efc-109">WCF Visual Studio 템플릿</span><span class="sxs-lookup"><span data-stu-id="57efc-109">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)  
  
 <span data-ttu-id="57efc-110">Visual Studio에서 미리 정의된 Visual Studio 프로젝트 및 항목 템플릿을 사용하여 WCF 서비스 및 주변 응용 프로그램을 신속하게 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57efc-110">You can use the predefined Visual Studio project and item templates in Visual Studio to quickly build WCF services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="57efc-111">WCF 서비스 호스트(WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="57efc-111">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="57efc-112">WCF 서비스 자동 호스트(WcfSvcHost.exe)를 사용하면 Visual Studio 디버거(F5)를 시작하여 구현한 서비스를 자동으로 호스팅하고 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57efc-112">The WCF Service Auto Host (WcfSvcHost.exe) allows you to launch the Visual Studio debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="57efc-113">그런 다음 WCF 테스트 클라이언트(wcfTestClient.exe) 또는 사용자 고유의 클라이언트를 사용하여 서비스를 테스트하여 잠재적인 오류를 찾아 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57efc-113">You can then test the service using the WCF Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="57efc-114">WCF 테스트 클라이언트(WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="57efc-114">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)  
  
 <span data-ttu-id="57efc-115">WCF 테스트 클라이언트(WcfTestClient.exe)는 임의의 형식의 매개 변수를 입력하고, 해당 입력을 서비스에 제출하고, 서비스가 다시 보내는 응답을 볼 수 있는 GUI 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="57efc-115">WCF Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="57efc-116">WCF 서비스 자동 호스트와 결합하면 원활한 서비스 테스트 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="57efc-116">It provides a seamless service testing experience when combined with WCF Service Auto Host.</span></span>  
  
 [<span data-ttu-id="57efc-117">XML에서 데이터 형식 클래스 생성</span><span class="sxs-lookup"><span data-stu-id="57efc-117">Generating Data Type Classes from XML</span></span>](generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="57efc-118">클립보드에 저장된 XML 데이터는 코드 페이지로 붙여 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57efc-118">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="57efc-119">데이터에 정의된 클래스는 코드 형식으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="57efc-119">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="57efc-120">관리자 권한 없이 도구 사용</span><span class="sxs-lookup"><span data-stu-id="57efc-120">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="57efc-121">관리자 권한이 없는 사용자가 WCF 서비스를 개발할 수 있도록 Visual Studio를 설치하는 동안http://+:8731/Design_Time_Addresses네임스페이스 "에 대한 ACL(액세스 제어 목록)이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="57efc-121">To enable users without administrator privilege to develop WCF services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of Visual Studio.</span></span> <span data-ttu-id="57efc-122">ACL은 (UI)로 설정되며 시스템에 로그온한 모든 대화식 사용자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="57efc-122">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="57efc-123">관리자는 이 ACL에서 사용자를 추가 또는 제거하거나 추가 포트를 열 수 있습니다. WCF 또는 WF 템플릿에서 이 ACL을 사용하여 데이터를 기본 구성으로 보내거나 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57efc-123">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="57efc-124">또한 사용자가 관리자 권한을 부여하지 않고 WCF 서비스 자동 호스트(wcfSvcHost.exe)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57efc-124">It also enables users to use the WCF Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="57efc-125">높은 관리자 계정 아래 Windows Vista의 Netsh.exe 도구를 사용하여 액세스를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57efc-125">You can modify access using the Netsh.exe tool in Windows Vista under the elevated administrator account.</span></span> <span data-ttu-id="57efc-126">다음은 Netsh.exe를 사용하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="57efc-126">The following is an example of using Netsh.exe.</span></span>  
  
```console  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 <span data-ttu-id="57efc-127">Netsh.exe에 대한 자세한 내용은 [Netsh.exe 도구 및 명령줄 스위치를 사용하는 방법을](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10))참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="57efc-127">For more information about Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57efc-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="57efc-128">See also</span></span>

- [<span data-ttu-id="57efc-129">WCF Visual Studio 템플릿</span><span class="sxs-lookup"><span data-stu-id="57efc-129">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)
- [<span data-ttu-id="57efc-130">WCF 서비스 호스트(WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="57efc-130">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)
- [<span data-ttu-id="57efc-131">WCF 테스트 클라이언트(WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="57efc-131">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)
