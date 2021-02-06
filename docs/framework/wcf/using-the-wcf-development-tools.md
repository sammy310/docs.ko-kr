---
description: '자세한 정보: WCF 개발 도구 사용'
title: WCF 개발 도구 사용
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: c96644fb66006447f6a05f6c08ea84fe2ed99ce8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631699"
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="7159c-103">WCF 개발 도구 사용</span><span class="sxs-lookup"><span data-stu-id="7159c-103">Using the WCF Development Tools</span></span>

<span data-ttu-id="7159c-104">이 섹션에서는 WCFservice 개발에 도움이 될 수 있는 Visual Studio 개발 도구에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7159c-104">This section describes the Visual Studio development tools that can assist you in developing your WCFservice.</span></span>  
  
 <span data-ttu-id="7159c-105">Visual Studio 템플릿을 기반으로 사용 하 여 서비스를 신속 하 게 빌드한 다음 WCF 서비스 자동 호스트 및 WCF 테스트 클라이언트를 사용 하 여 서비스를 디버깅 하 고 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7159c-105">You can use the Visual Studio templates as a foundation to quickly build your own service, then use WCF Service Auto Host and WCF Test Client to debug and test your service.</span></span> <span data-ttu-id="7159c-106">이러한 도구를 함께 사용하면 디버그 및 테스트를 원활하고 빠르게 수행할 수 있으며 초기 단계에서 호스팅 모델에 주력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7159c-106">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  

 > [!NOTE]
 > <span data-ttu-id="7159c-107">Visual Studio 2017부터 WCF 개발 도구는 기본적으로 설치 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7159c-107">Starting with Visual Studio 2017, the WCF development tools are not installed by default.</span></span> <span data-ttu-id="7159c-108">이러한 기능을 사용 하려면 Visual Studio 설치 관리자에서 Windows Communication Foundation 구성 요소가 선택 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7159c-108">In order to use these features, you must ensure the Windows Communication Foundation component is selected in the Visual Studio installer.</span></span>
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="7159c-109">WCF 개발자 도구</span><span class="sxs-lookup"><span data-stu-id="7159c-109">The WCF Developer Tools</span></span>  

 [<span data-ttu-id="7159c-110">WCF Visual Studio 템플릿</span><span class="sxs-lookup"><span data-stu-id="7159c-110">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)  
  
 <span data-ttu-id="7159c-111">Visual Studio에서 미리 정의 된 Visual Studio 프로젝트 및 항목 템플릿을 사용 하 여 WCF 서비스와 주변 응용 프로그램을 빠르게 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7159c-111">You can use the predefined Visual Studio project and item templates in Visual Studio to quickly build WCF services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="7159c-112">WCF 서비스 호스트(WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="7159c-112">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="7159c-113">WCF 서비스 자동 호스트 (WcfSvcHost.exe)를 사용 하 여 Visual Studio 디버거 (F5)를 시작 하 여 구현한 서비스를 자동으로 호스트 하 고 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7159c-113">The WCF Service Auto Host (WcfSvcHost.exe) allows you to launch the Visual Studio debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="7159c-114">그런 다음 WCF 테스트 클라이언트 (wcfTestClient.exe) 또는 자체 클라이언트를 사용 하 여 서비스를 테스트 하 여 잠재적인 오류를 찾아 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7159c-114">You can then test the service using the WCF Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="7159c-115">WCF 테스트 클라이언트(WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="7159c-115">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)  
  
 <span data-ttu-id="7159c-116">WCF 테스트 클라이언트 (WcfTestClient.exe)는 임의의 형식의 매개 변수를 입력 하 고, 해당 입력을 서비스에 제출 하 고, 서비스가 다시 보내는 응답을 볼 수 있는 GUI 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="7159c-116">WCF Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="7159c-117">WCF 서비스 자동 호스트와 결합 될 때 원활한 서비스 테스트 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7159c-117">It provides a seamless service testing experience when combined with WCF Service Auto Host.</span></span>  
  
 [<span data-ttu-id="7159c-118">XML에서 데이터 형식 클래스 생성</span><span class="sxs-lookup"><span data-stu-id="7159c-118">Generating Data Type Classes from XML</span></span>](generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="7159c-119">클립보드에 저장된 XML 데이터는 코드 페이지로 붙여 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7159c-119">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="7159c-120">데이터에 정의된 클래스는 코드 형식으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7159c-120">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="7159c-121">관리자 권한 없이 도구 사용</span><span class="sxs-lookup"><span data-stu-id="7159c-121">Using the Tools without Administrator privilege</span></span>  

 <span data-ttu-id="7159c-122">관리자 권한이 없는 사용자가 WCF 서비스를 개발할 수 있도록 Visual Studio를 설치 하는 동안 네임 스페이스 ""에 대 한 ACL (Access Control 목록)이 만들어집니다 http://+:8731/Design_Time_Addresses .</span><span class="sxs-lookup"><span data-stu-id="7159c-122">To enable users without administrator privilege to develop WCF services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of Visual Studio.</span></span> <span data-ttu-id="7159c-123">ACL은 (UI)로 설정되며 시스템에 로그온한 모든 대화식 사용자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7159c-123">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="7159c-124">관리자는 이 ACL에서 사용자를 추가 또는 제거하거나 추가 포트를 열 수 있습니다. WCF 또는 WF 템플릿에서 이 ACL을 사용하여 데이터를 기본 구성으로 보내거나 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7159c-124">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="7159c-125">또한 사용자가 관리자 권한을 부여 하지 않고 WCF 서비스 자동 호스트 (wcfSvcHost.exe)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7159c-125">It also enables users to use the WCF Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="7159c-126">관리자 권한으로 Windows Vista의 Netsh.exe 도구를 사용 하 여 액세스 권한을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7159c-126">You can modify access using the Netsh.exe tool in Windows Vista under the elevated administrator account.</span></span> <span data-ttu-id="7159c-127">다음은 Netsh.exe를 사용하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7159c-127">The following is an example of using Netsh.exe.</span></span>  
  
```console  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 <span data-ttu-id="7159c-128">Netsh.exe에 대 한 자세한 내용은 [Netsh.exe 도구 사용 방법 및 Command-Line 스위치](/previous-versions/tn-archive/bb490939(v=technet.10))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7159c-128">For more information about Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](/previous-versions/tn-archive/bb490939(v=technet.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7159c-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7159c-129">See also</span></span>

- [<span data-ttu-id="7159c-130">WCF Visual Studio 템플릿</span><span class="sxs-lookup"><span data-stu-id="7159c-130">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)
- [<span data-ttu-id="7159c-131">WCF 서비스 호스트(WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="7159c-131">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)
- [<span data-ttu-id="7159c-132">WCF 테스트 클라이언트(WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="7159c-132">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)
