---
title: '방법: 서비스 애플리케이션에 설치 관리자 추가'
description: 서비스 애플리케이션에 설치 관리자를 추가하는 방법을 참조하세요. Visual Studio에서는 서비스 앱과 관련된 리소스를 설치할 수 있는 설치 구성 요소를 제공합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, deploying
- installation components, adding to services
- installers, adding to services
- Windows Service applications, adding installers
- services, adding installers
- ServiceInstaller class, adding installers to services
- ServiceProcessInstaller class, adding installers to services
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
author: ghogen
ms.openlocfilehash: f82dd6635555ccb8fcbcdf63cba2495084194731
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925646"
---
# <a name="how-to-add-installers-to-your-service-application"></a><span data-ttu-id="ad80b-104">방법: 서비스 애플리케이션에 설치 관리자 추가</span><span class="sxs-lookup"><span data-stu-id="ad80b-104">How to: Add Installers to Your Service Application</span></span>
<span data-ttu-id="ad80b-105">Visual Studio에서는 서비스 애플리케이션과 관련된 리소스를 설치할 수 있는 설치 구성 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-105">Visual Studio ships installation components that can install resources associated with your service applications.</span></span> <span data-ttu-id="ad80b-106">설치 구성 요소는 서비스를 설치하는 시스템에 개별 서비스를 등록하고 서비스 제어 관리자에 서비스가 있음을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-106">Installation components register an individual service on the system to which it is being installed and let the Services Control Manager know that the service exists.</span></span> <span data-ttu-id="ad80b-107">서비스 애플리케이션을 작업할 때 속성 창의 링크를 선택하여 프로젝트에 적절한 설치 관리자를 자동으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-107">When you work with a service application, you can select a link in the Properties window to automatically add the appropriate installers to your project.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ad80b-108">서비스의 속성 값이 서비스 클래스에서 설치 관리자 클래스로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-108">Property values for your service are copied from the service class to the installer class.</span></span> <span data-ttu-id="ad80b-109">서비스 클래스에서 속성 값을 업데이트하는 경우 설치 관리자에서 해당 속성이 자동으로 업데이트되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-109">If you update the property values on the service class, they are not automatically updated in the installer.</span></span>  
  
 <span data-ttu-id="ad80b-110">프로젝트에 설치 관리자를 추가하면 새 클래스(기본적으로 이름은 `ProjectInstaller`)가 프로젝트에 생성되고 이 클래스 안에 적절한 설치 구성 요소의 인스턴스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-110">When you add an installer to your project, a new class (which, by default, is named `ProjectInstaller`) is created in the project, and instances of the appropriate installation components are created within it.</span></span> <span data-ttu-id="ad80b-111">이 클래스는 프로젝트에 필요한 모든 설치 구성 요소의 중심점 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-111">This class acts as a central point for all of the installation components your project needs.</span></span> <span data-ttu-id="ad80b-112">예를 들어 애플리케이션에 두 번째 서비스를 추가하고 설치 관리자 추가 링크를 클릭하면 두 번째 설치 관리자 클래스가 생성되지 않습니다. 대신 두 번째 서비스에 필요한 추가 설치 구성 요소가 기존 클래스에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-112">For example, if you add a second service to your application and click the Add Installer link, a second installer class is not created; instead, the necessary additional installation component for the second service is added to the existing class.</span></span>  
  
 <span data-ttu-id="ad80b-113">서비스를 올바로 설치하도록 하기 위해 설치 관리자 내에서 코딩을 수행할 필요는 특별히 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-113">You do not need to do any special coding within the installers to make your services install correctly.</span></span> <span data-ttu-id="ad80b-114">하지만 가끔은 설치 프로세스에 특수한 기능을 추가해야 하는 경우 설치 관리자의 내용을 수정해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-114">However, you may occasionally need to modify the contents of the installers if you need to add special functionality to the installation process.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ad80b-115">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-115">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ad80b-116">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-116">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ad80b-117">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ad80b-117">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-installers-to-your-service-application"></a><span data-ttu-id="ad80b-118">서비스 애플리케이션에 설치 관리자를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="ad80b-118">To add installers to your service application</span></span>  
  
1. <span data-ttu-id="ad80b-119">**솔루션 탐색기**에서 설치 구성 요소를 추가할 서비스의 **디자인** 뷰에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-119">In **Solution Explorer**, access **Design** view for the service for which you want to add an installation component.</span></span>  
  
2. <span data-ttu-id="ad80b-120">디자이너의 배경을 클릭하여 서비스 내용이 아닌 서비스 자체를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-120">Click the background of the designer to select the service itself, rather than any of its contents.</span></span>  
  
3. <span data-ttu-id="ad80b-121">디자이너에 포커스가 있는 상태에서 **설치 관리자 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-121">With the designer in focus, right-click, and then click **Add Installer**.</span></span>  
  
     <span data-ttu-id="ad80b-122">새 클래스 `ProjectInstaller`와 두 개의 설치 구성 요소 <xref:System.ServiceProcess.ServiceProcessInstaller> 및 <xref:System.ServiceProcess.ServiceInstaller>가 프로젝트에 추가되고 서비스의 속성 값이 이러한 구성 요소에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-122">A new class, `ProjectInstaller`, and two installation components, <xref:System.ServiceProcess.ServiceProcessInstaller> and <xref:System.ServiceProcess.ServiceInstaller>, are added to your project, and property values for the service are copied to the components.</span></span>  
  
4. <span data-ttu-id="ad80b-123"><xref:System.ServiceProcess.ServiceInstaller> 구성 요소를 클릭하고 <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> 속성 값이 서비스 자체의 <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> 속성과 동일한 값으로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-123">Click the <xref:System.ServiceProcess.ServiceInstaller> component and verify that the value of the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to the same value as the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property on the service itself.</span></span>  
  
5. <span data-ttu-id="ad80b-124">서비스 시작 방법을 결정하려면 <xref:System.ServiceProcess.ServiceInstaller> 구성 요소를 클릭하고 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 속성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-124">To determine how your service will be started, click the <xref:System.ServiceProcess.ServiceInstaller> component and set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to the appropriate value.</span></span>  
  
    |<span data-ttu-id="ad80b-125">값</span><span class="sxs-lookup"><span data-stu-id="ad80b-125">Value</span></span>|<span data-ttu-id="ad80b-126">결과</span><span class="sxs-lookup"><span data-stu-id="ad80b-126">Result</span></span>|  
    |-----------|------------|  
    |<xref:System.ServiceProcess.ServiceStartMode.Manual>|<span data-ttu-id="ad80b-127">서비스를 설치 후 수동으로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-127">The service must be manually started after installation.</span></span> <span data-ttu-id="ad80b-128">자세한 내용은 [방법: 서비스 시작](how-to-start-services.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ad80b-128">For more information, see [How to: Start Services](how-to-start-services.md).</span></span>|  
    |<xref:System.ServiceProcess.ServiceStartMode.Automatic>|<span data-ttu-id="ad80b-129">컴퓨터가 재부팅될 때마다 서비스가 저절로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-129">The service will start by itself whenever the computer reboots.</span></span>|  
    |<xref:System.ServiceProcess.ServiceStartMode.Disabled>|<span data-ttu-id="ad80b-130">서비스를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-130">The service cannot be started.</span></span>|  
  
6. <span data-ttu-id="ad80b-131">서비스를 실행할 보안 컨텍스트를 결정하려면 <xref:System.ServiceProcess.ServiceProcessInstaller> 구성 요소를 클릭하고 적절한 속성 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-131">To determine the security context in which your service will run, click the <xref:System.ServiceProcess.ServiceProcessInstaller> component and set the appropriate property values.</span></span> <span data-ttu-id="ad80b-132">자세한 내용은 [방법: 서비스에 대한 보안 컨텍스트 지정](how-to-specify-the-security-context-for-services.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ad80b-132">For more information, see [How to: Specify the Security Context for Services](how-to-specify-the-security-context-for-services.md).</span></span>  
  
7. <span data-ttu-id="ad80b-133">사용자 지정 처리를 수행해야 하는 모든 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-133">Override any methods for which you need to perform custom processing.</span></span>  
  
8. <span data-ttu-id="ad80b-134">프로젝트의 추가 서비스 각각에 대해 1-7단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-134">Perform steps 1 through 7 for each additional service in your project.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ad80b-135">프로젝트의 각 추가 서비스에 대해 프로젝트의 `ProjectInstaller` 클래스에 <xref:System.ServiceProcess.ServiceInstaller> 구성 요소를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-135">For each additional service in your project, you must add an additional <xref:System.ServiceProcess.ServiceInstaller> component to the project's `ProjectInstaller` class.</span></span> <span data-ttu-id="ad80b-136">3단계에서 추가된 <xref:System.ServiceProcess.ServiceProcessInstaller> 구성 요소는 프로젝트의 모든 개별 서비스 설치 관리자에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="ad80b-136">The <xref:System.ServiceProcess.ServiceProcessInstaller> component added in step three works with all of the individual service installers in the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad80b-137">참조</span><span class="sxs-lookup"><span data-stu-id="ad80b-137">See also</span></span>

- [<span data-ttu-id="ad80b-138">Windows 서비스 애플리케이션 소개</span><span class="sxs-lookup"><span data-stu-id="ad80b-138">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="ad80b-139">방법: 서비스 설치 및 제거</span><span class="sxs-lookup"><span data-stu-id="ad80b-139">How to: Install and Uninstall Services</span></span>](how-to-install-and-uninstall-services.md)
- [<span data-ttu-id="ad80b-140">방법: 서비스 시작</span><span class="sxs-lookup"><span data-stu-id="ad80b-140">How to: Start Services</span></span>](how-to-start-services.md)
- [<span data-ttu-id="ad80b-141">방법: 서비스에 대한 보안 컨텍스트 지정</span><span class="sxs-lookup"><span data-stu-id="ad80b-141">How to: Specify the Security Context for Services</span></span>](how-to-specify-the-security-context-for-services.md)
