---
title: '방법: Windows 서비스 설치 및 제거'
ms.date: 02/05/2019
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, apps, Windows services
- installation, Windows services
- uninstalling Windows services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
author: ghogen
ms.openlocfilehash: 38fc0172b5f97561d69fe495237e95597d7b9727
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003128"
---
# <a name="how-to-install-and-uninstall-windows-services"></a><span data-ttu-id="381c6-102">방법: Windows 서비스 설치 및 제거</span><span class="sxs-lookup"><span data-stu-id="381c6-102">How to: Install and uninstall Windows services</span></span>

<span data-ttu-id="381c6-103">.NET Framework를 사용 하 여 Windows 서비스를 개발 하는 경우 [*installutil.exe*](../tools/installutil-exe-installer-tool.md) 명령줄 유틸리티 또는 [PowerShell](/powershell/scripting/overview)을 사용 하 여 서비스 앱을 신속 하 게 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-103">If you’re developing a Windows service with the .NET Framework, you can quickly install your service app by using the [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) command-line utility or [PowerShell](/powershell/scripting/overview).</span></span> <span data-ttu-id="381c6-104">사용자가 설치하고 제거할 수 있는 Windows 서비스를 릴리스하려는 개발자는 InstallShield를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-104">Developers who want to release a Windows service that users can install and uninstall should use InstallShield.</span></span> <span data-ttu-id="381c6-105">자세한 내용은 [설치 관리자 패키지 만들기(Windows 클라이언트)](https://docs.microsoft.com/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="381c6-105">For more information, see [Create an installer package (Windows client)](https://docs.microsoft.com/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).</span></span>

> [!WARNING]
> <span data-ttu-id="381c6-106">서비스를 컴퓨터에서 제거하려면 이 문서의 단계를 수행하는 대신</span><span class="sxs-lookup"><span data-stu-id="381c6-106">If you want to uninstall a service from your computer, don’t follow the steps in this article.</span></span> <span data-ttu-id="381c6-107">서비스를 설치한 프로그램 또는 소프트웨어 패키지를 확인한 다음, 설정에서 **앱**을 선택하여 해당 프로그램을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-107">Instead, find out which program or software package installed the service, and then choose **Apps** in Settings to uninstall that program.</span></span> <span data-ttu-id="381c6-108">대부분의 서비스는 Windows의 필수 요소이므로 제거하는 경우 시스템이 불안정해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-108">Note that many services are integral parts of Windows; if you remove them, you might cause system instability.</span></span>

<span data-ttu-id="381c6-109">이 문서의 단계를 수행하려면 먼저 Windows 서비스에 서비스 설치 관리자를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-109">To use the steps in this article, you first need to add a service installer to your Windows service.</span></span> <span data-ttu-id="381c6-110">자세한 내용은 [연습: Windows 서비스 앱 만들기](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="381c6-110">For more information, see [Walkthrough: Creating a Windows service app](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>

<span data-ttu-id="381c6-111">F5 키를 눌러 Visual Studio 개발 환경에서 직접 Windows 서비스 프로젝트를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-111">You can't run Windows service projects directly from the Visual Studio development environment by pressing F5.</span></span> <span data-ttu-id="381c6-112">프로젝트를 실행하려면 먼저 프로젝트에 서비스를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-112">Before you can run the project, you must install the service in the project.</span></span>

> [!TIP]
> <span data-ttu-id="381c6-113">**서버 탐색기**를 사용하여 서비스가 설치되거나 제거되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-113">You can use **Server Explorer** to verify that you've installed or uninstalled your service.</span></span> <span data-ttu-id="381c6-114">자세한 내용은 [Visual Studio에서 서버 탐색기를 사용하는 방법](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="381c6-114">For more information, see [How to use Server Explorer in Visual Studio](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).</span></span>

### <a name="install-your-service-manually-using-installutilexe-utility"></a><span data-ttu-id="381c6-115">Installutil.exe 유틸리티를 사용 하 여 수동으로 서비스 설치</span><span class="sxs-lookup"><span data-stu-id="381c6-115">Install your service manually using InstallUtil.exe utility</span></span>

1. <span data-ttu-id="381c6-116">**시작** 메뉴에서 **Visual Studio \<*version*>** 디렉터리를 선택한 다음, **Developer Command Prompt for VS \<*version*>** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-116">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>

     <span data-ttu-id="381c6-117">Visual Studio용 개발자 명령 프롬프트가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-117">The Developer Command Prompt for Visual Studio appears.</span></span>

2. <span data-ttu-id="381c6-118">프로젝트의 컴파일된 실행 파일이 있는 디렉터리에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-118">Access the directory where your project's compiled executable file is located.</span></span>

3. <span data-ttu-id="381c6-119">프로젝트의 실행 파일을 매개 변수로 사용하여 명령 프롬프트에서 *InstallUtil.exe*를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-119">Run *InstallUtil.exe* from the command prompt with your project's executable as a parameter:</span></span>

    ```console
    installutil <yourproject>.exe
    ```

     <span data-ttu-id="381c6-120">Visual Studio용 개발자 명령 프롬프트를 사용하는 경우 *InstallUtil.exe*가 시스템 경로에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-120">If you’re using the Developer Command Prompt for Visual Studio, *InstallUtil.exe* should be on the system path.</span></span> <span data-ttu-id="381c6-121">그렇지 않으면 해당 파일을 경로에 추가하거나 정규화된 경로를 사용하여 호출하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-121">Otherwise, you can add it to the path, or use the fully qualified path to invoke it.</span></span> <span data-ttu-id="381c6-122">이 도구는 *%WINDIR%\Microsoft.NET\Framework[64]\\<framework_version\>* 에 .NET Framework와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-122">This tool is installed with the .NET Framework in *%WINDIR%\Microsoft.NET\Framework[64]\\<framework_version\>*.</span></span>

     <span data-ttu-id="381c6-123">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-123">For example:</span></span>
     - <span data-ttu-id="381c6-124">32비트 버전의 .NET Framework 4 또는 4.5 이상인 경우 Windows 설치 디렉터리가 *C:\Windows*이면 기본 경로는 *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*입니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-124">For the 32-bit version of the .NET Framework 4 or 4.5 and later, if your Windows installation directory is *C:\Windows*, the default path is *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span></span>
     - <span data-ttu-id="381c6-125">64비트 버전의 .NET Framework 4 또는 4.5 이상인 경우 기본 경로는 *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*입니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-125">For the 64-bit version of the .NET Framework 4 or 4.5 and later, the default path is *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span></span>

### <a name="uninstall-your-service-manually-using-installutilexe-utility"></a><span data-ttu-id="381c6-126">Installutil.exe 유틸리티를 사용 하 여 수동으로 서비스 제거</span><span class="sxs-lookup"><span data-stu-id="381c6-126">Uninstall your service manually using InstallUtil.exe utility</span></span>

1. <span data-ttu-id="381c6-127">**시작** 메뉴에서 **Visual Studio \<*version*>** 디렉터리를 선택한 다음, **Developer Command Prompt for VS \<*version*>** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-127">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>

     <span data-ttu-id="381c6-128">Visual Studio용 개발자 명령 프롬프트가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-128">The Developer Command Prompt for Visual Studio appears.</span></span>

2. <span data-ttu-id="381c6-129">프로젝트의 출력을 매개 변수로 사용하여 명령 프롬프트에서 *InstallUtil.exe*를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-129">Run *InstallUtil.exe* from the command prompt with your project's output as a parameter:</span></span>

    ```console
    installutil /u <yourproject>.exe
    ```

3. <span data-ttu-id="381c6-130">서비스의 실행 파일을 삭제해도 서비스가 레지스트리에 남아 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-130">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="381c6-131">이러한 경우에는 [sc delete](/windows-server/administration/windows-commands/sc-delete) 명령을 사용하여 레지스트리에서 서비스의 항목을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-131">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>

### <a name="install-your-service-manually-using-powershell"></a><span data-ttu-id="381c6-132">PowerShell을 사용 하 여 수동으로 서비스 설치</span><span class="sxs-lookup"><span data-stu-id="381c6-132">Install your service manually using PowerShell</span></span>

1. <span data-ttu-id="381c6-133">**시작** 메뉴에서 **windows powershell** 디렉터리를 선택 하 고 **windows powershell**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-133">From the **Start** menu, select the **Windows PowerShell** directory, then select **Windows PowerShell**.</span></span>

2. <span data-ttu-id="381c6-134">프로젝트의 컴파일된 실행 파일이 있는 디렉터리에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-134">Access the directory where your project's compiled executable file is located.</span></span>

3. <span data-ttu-id="381c6-135">프로젝트의 출력과 서비스 이름을 매개 변수로 사용 하 여 [**새 서비스**](/powershell/module/microsoft.powershell.management/new-service) cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-135">Run the [**New-Service**](/powershell/module/microsoft.powershell.management/new-service) cmdlet with the with your project's output and a service name as parameters:</span></span>

    ```powershell
    New-Service -Name "YourServiceName" -BinaryPathName <yourproject>.exe
    ```

### <a name="uninstall-your-service-manually-using-powershell"></a><span data-ttu-id="381c6-136">PowerShell을 사용 하 여 수동으로 서비스 제거</span><span class="sxs-lookup"><span data-stu-id="381c6-136">Uninstall your service manually using PowerShell</span></span>

1. <span data-ttu-id="381c6-137">**시작** 메뉴에서 **windows powershell** 디렉터리를 선택 하 고 **windows powershell**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-137">From the **Start** menu, select the **Windows PowerShell** directory, then select **Windows PowerShell**.</span></span>

2. <span data-ttu-id="381c6-138">서비스 이름을 매개 변수로 사용 하 여 [**서비스**](/powershell/module/microsoft.powershell.management/remove-service) 이름 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-138">Run the [**Remove-Service**](/powershell/module/microsoft.powershell.management/remove-service) cmdlet with the name of your service as parameter:</span></span>

    ```powershell
    Remove-Service -Name "YourServiceName"
    ```

3. <span data-ttu-id="381c6-139">서비스의 실행 파일을 삭제해도 서비스가 레지스트리에 남아 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-139">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="381c6-140">이러한 경우에는 [sc delete](/windows-server/administration/windows-commands/sc-delete) 명령을 사용하여 레지스트리에서 서비스의 항목을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="381c6-140">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>

    ```powershell
    sc.exe delete "YourServiceName"
    ```

## <a name="see-also"></a><span data-ttu-id="381c6-141">참조</span><span class="sxs-lookup"><span data-stu-id="381c6-141">See also</span></span>

- [<span data-ttu-id="381c6-142">Windows 서비스 애플리케이션 소개</span><span class="sxs-lookup"><span data-stu-id="381c6-142">Introduction to Windows service applications</span></span>](../windows-services/introduction-to-windows-service-applications.md)
- [<span data-ttu-id="381c6-143">방법: Windows 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="381c6-143">How to: Create Windows services</span></span>](../windows-services/how-to-create-windows-services.md)
- [<span data-ttu-id="381c6-144">방법: 서비스 애플리케이션에 설치 관리자 추가</span><span class="sxs-lookup"><span data-stu-id="381c6-144">How to: Add installers to your service application</span></span>](../windows-services/how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="381c6-145">Installutil.exe(설치 관리자 도구)</span><span class="sxs-lookup"><span data-stu-id="381c6-145">Installutil.exe (Installer tool)</span></span>](../tools/installutil-exe-installer-tool.md)
