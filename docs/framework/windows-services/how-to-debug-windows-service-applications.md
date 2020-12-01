---
title: '방법: Windows 서비스 애플리케이션 디버그'
description: 다른 Visual Studio 애플리케이션 형식으로 쉽게 디버그할 수 없는 Windows 서비스 애플리케이션을 디버그하는 방법을 이해합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- Windows NT services, debugging
- Windows Service applications, debugging
- services, debugging
ms.assetid: 63ab0800-0f05-4f1e-88e6-94c73fd920a2
ms.openlocfilehash: 4d8ac0316e47925d253e7220597ab9953252521e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270630"
---
# <a name="how-to-debug-windows-service-applications"></a><span data-ttu-id="fe832-103">방법: Windows 서비스 애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="fe832-103">How to: Debug Windows Service Applications</span></span>

<span data-ttu-id="fe832-104">서비스는 Visual Studio 내에서가 아니라 서비스 제어 관리자의 컨텍스트 내에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-104">A service must be run from within the context of the Services Control Manager rather than from within Visual Studio.</span></span> <span data-ttu-id="fe832-105">따라서 서비스를 디버그하는 것은 다른 Visual Studio 애플리케이션 형식을 디버그하는 것처럼 단순하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-105">For this reason, debugging a service is not as straightforward as debugging other Visual Studio application types.</span></span> <span data-ttu-id="fe832-106">서비스를 디버그하려면 서비스를 시작한 다음 서비스가 실행되는 프로세스에 디버거를 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-106">To debug a service, you must start the service and then attach a debugger to the process in which it is running.</span></span> <span data-ttu-id="fe832-107">그리고 나면 Visual Studio의 모든 표준 디버깅 기능을 사용하여 애플리케이션을 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-107">You can then debug your application by using all of the standard debugging functionality of Visual Studio.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="fe832-108">프로세스에 대해 알고 있으며 해당 프로세스에 디버거를 연결하는 경우 프로세스가 종료될 수도 있음을 이해한 상태에서 프로세스에 디버거를 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-108">You should not attach to a process unless you know what the process is and understand the consequences of attaching to and possibly killing that process.</span></span> <span data-ttu-id="fe832-109">예를 들어 WinLogon 프로세스에 연결한 후에 디버깅을 중지하면 시스템이 중단됩니다. 시스템은 WinLogon 없이는 작동할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-109">For example, if you attach to the WinLogon process and then stop debugging, the system will halt because it can’t operate without WinLogon.</span></span>  
  
 <span data-ttu-id="fe832-110">실행 중인 서비스에만 디버거를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-110">You can attach the debugger only to a running service.</span></span> <span data-ttu-id="fe832-111">연결 프로세스에서는 현재 서비스 작동이 중단되지만 서비스 처리가 실제로 중지되거나 일시 중지되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-111">The attachment process interrupts the current functioning of your service; it doesn’t actually stop or pause the service's processing.</span></span> <span data-ttu-id="fe832-112">즉, 디버깅을 시작할 때 실행 중인 서비스는 디버그할 때도 기술적으로 계속 시작됨 상태이지만 처리는 일시 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-112">That is, if your service is running when you begin debugging, it is still technically in the Started state as you debug it, but its processing has been suspended.</span></span>  
  
 <span data-ttu-id="fe832-113">프로세스에 연결한 후에는 중단점을 설정하여 코드를 디버그하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-113">After attaching to the process, you can set breakpoints and use these to debug your code.</span></span> <span data-ttu-id="fe832-114">프로세스에 연결하는 데 사용한 대화 상자를 종료하면 디버그 모드가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-114">Once you exit the dialog box you use to attach to the process, you are effectively in debug mode.</span></span> <span data-ttu-id="fe832-115">서비스 제어 관리자를 사용하여 서비스를 시작, 중지, 일시 중지 및 계속해 설정된 중단점을 적중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-115">You can use the Services Control Manager to start, stop, pause and continue your service, thus hitting the breakpoints you've set.</span></span> <span data-ttu-id="fe832-116">나중에 디버깅이 정상적으로 완료되면 이 더미 서비스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-116">You can later remove this dummy service after debugging is successful.</span></span>  
  
 <span data-ttu-id="fe832-117">이 문서에서는 로컬 컴퓨터에서 실행되는 서비스를 디버그하는 방법에 대해 다루지만, 원격 컴퓨터에서 실행되는 Windows 서비스도 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-117">This article covers debugging a service that's running on the local computer, but you can also debug Windows Services that are running on a remote computer.</span></span> <span data-ttu-id="fe832-118">[원격 디버깅](/visualstudio/debugger/debug-installed-app-package)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe832-118">See [Remote Debugging](/visualstudio/debugger/debug-installed-app-package).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe832-119">서비스 제어 관리자는 모든 서비스 시작 시도에 대해 30초의 제한을 적용하므로 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드를 디버그하는 작업은 까다로울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-119">Debugging the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method can be difficult because the Services Control Manager imposes a 30-second limit on all attempts to start a service.</span></span> <span data-ttu-id="fe832-120">자세한 내용은 [문제 해결: Windows 서비스 디버깅](troubleshooting-debugging-windows-services.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe832-120">For more information, see [Troubleshooting: Debugging Windows Services](troubleshooting-debugging-windows-services.md).</span></span>  
  
> [!WARNING]
> <span data-ttu-id="fe832-121">디버깅을 위한 의미 있는 정보를 가져오려면 Visual Studio 디버거가 디버그 중인 이진 파일에 대한 기호 파일을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-121">To get meaningful information for debugging, the Visual Studio debugger needs to find symbol files for the binaries that are being debugged.</span></span> <span data-ttu-id="fe832-122">Visual Studio에서 빌드한 서비스를 디버그하는 경우 기호 파일(.pdb 파일)은 실행 파일이나 라이브러리와 같은 폴더에 있으며 디버거는 이러한 파일을 자동으로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-122">If you are debugging a service that you built in Visual Studio, the symbol files (.pdb files) are in the same folder as the executable or library, and the debugger loads them automatically.</span></span> <span data-ttu-id="fe832-123">직접 빌드하지 않은 서비스를 디버그할 때는 먼저 서비스의 기호를 찾아 디버거가 해당 기호를 검색할 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-123">If you are debugging a service that you didn't build, you should first find symbols for the service and make sure they can be found by the debugger.</span></span> <span data-ttu-id="fe832-124">[Visual Studio 디버거에서 기호 파일(.pdb) 및 소스 파일 지정](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe832-124">See [Specify Symbol (.pdb) and Source Files in the Visual Studio Debugger](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger).</span></span> <span data-ttu-id="fe832-125">시스템 프로세스를 디버그하거나 서비스에 시스템 호출을 위한 기호를 포함하려는 경우에는 Microsoft 기호 서버를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-125">If you're debugging a system process or want to have symbols for system calls in your services, you should add the Microsoft Symbol Servers.</span></span> <span data-ttu-id="fe832-126">[디버깅 기호](/windows/desktop/DxTechArts/debugging-with-symbols)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe832-126">See [Debugging Symbols](/windows/desktop/DxTechArts/debugging-with-symbols).</span></span>  
  
### <a name="to-debug-a-service"></a><span data-ttu-id="fe832-127">서비스를 디버깅하려면</span><span class="sxs-lookup"><span data-stu-id="fe832-127">To debug a service</span></span>  
  
1. <span data-ttu-id="fe832-128">디버그 구성에서 서비스를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-128">Build your service in the Debug configuration.</span></span>  
  
2. <span data-ttu-id="fe832-129">서비스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-129">Install your service.</span></span> <span data-ttu-id="fe832-130">자세한 내용은 [방법: 서비스 설치 및 제거](how-to-install-and-uninstall-services.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe832-130">For more information, see [How to: Install and Uninstall Services](how-to-install-and-uninstall-services.md).</span></span>  
  
3. <span data-ttu-id="fe832-131">**서비스 제어 관리자**, **서버 탐색기** 또는 코드에서 서비스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-131">Start your service, either from **Services Control Manager**, **Server Explorer**, or from code.</span></span> <span data-ttu-id="fe832-132">자세한 내용은 [방법: 서비스 시작](how-to-start-services.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe832-132">For more information, see [How to: Start Services](how-to-start-services.md).</span></span>  
  
4. <span data-ttu-id="fe832-133">시스템 프로세스에 연결할 수 있도록 관리 자격 증명을 사용하여 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-133">Start Visual Studio with administrative credentials so you can attach to system processes.</span></span>  
  
5. <span data-ttu-id="fe832-134">(선택 사항) Visual Studio 메뉴 모음에서 **도구**, **옵션** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-134">(Optional) On the Visual Studio menu bar, choose **Tools**, **Options**.</span></span> <span data-ttu-id="fe832-135">**옵션** 대화 상자에서 **디버깅**, **기호** 를 차례로 선택하고 **Microsoft 기호 서버** 확인란을 선택한 다음, **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-135">In the **Options** dialog box, choose **Debugging**, **Symbols**, select the **Microsoft Symbol Servers** check box, and then choose the **OK** button.</span></span>  
  
6. <span data-ttu-id="fe832-136">메뉴 모음의 **디버그** 또는 **도구** 메뉴에서 **프로세스에 연결** 을</span><span class="sxs-lookup"><span data-stu-id="fe832-136">On the menu bar, choose **Attach to Process** from the **Debug** or **Tools** menu.</span></span> <span data-ttu-id="fe832-137">(키보드: Ctrl+Alt+P)</span><span class="sxs-lookup"><span data-stu-id="fe832-137">(Keyboard: Ctrl+Alt+P)</span></span>  
  
     <span data-ttu-id="fe832-138">**프로세스** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-138">The **Processes** dialog box appears.</span></span>  
  
7. <span data-ttu-id="fe832-139">**모든 사용자의 프로세스 표시** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-139">Select the **Show processes from all users** check box.</span></span>  
  
8. <span data-ttu-id="fe832-140">**사용 가능한 프로세스** 섹션에서 서비스의 프로세스를 선택한 다음, **연결** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-140">In the **Available Processes** section, choose the process for your service, and then choose **Attach**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="fe832-141">프로세스의 이름은 서비스의 실행 파일 이름과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-141">The process will have the same name as the executable file for your service.</span></span>  
  
     <span data-ttu-id="fe832-142">**프로세스에 연결** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-142">The **Attach to Process** dialog box appears.</span></span>  
  
9. <span data-ttu-id="fe832-143">적절한 옵션을 선택하고 **확인** 단추를 선택하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-143">Choose the appropriate options, and then choose **OK** to close the dialog box.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="fe832-144">이제 디버그 모드가 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-144">You are now in debug mode.</span></span>  
  
10. <span data-ttu-id="fe832-145">코드에서 사용할 중단점을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-145">Set any breakpoints you want to use in your code.</span></span>  
  
11. <span data-ttu-id="fe832-146">서비스 제어 관리자에 액세스하고 서비스를 조작하여 중단점을 적중하는 중지, 일시 중지 및 계속 명령을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-146">Access the Services Control Manager and manipulate your service, sending stop, pause, and continue commands to hit your breakpoints.</span></span> <span data-ttu-id="fe832-147">서비스 제어 관리자 실행에 대한 자세한 내용은 [방법: 서비스 시작](how-to-start-services.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe832-147">For more information about running the Services Control Manager, see [How to: Start Services](how-to-start-services.md).</span></span> <span data-ttu-id="fe832-148">또한 [문제 해결: Windows 서비스 디버깅](troubleshooting-debugging-windows-services.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe832-148">Also, see [Troubleshooting: Debugging Windows Services](troubleshooting-debugging-windows-services.md).</span></span>  
  
## <a name="debugging-tips-for-windows-services"></a><span data-ttu-id="fe832-149">Windows 서비스 디버깅 팁</span><span class="sxs-lookup"><span data-stu-id="fe832-149">Debugging Tips for Windows Services</span></span>  

 <span data-ttu-id="fe832-150">서비스의 프로세스에 연결하면 해당 서비스의 코드를 대부분 디버그할 수 있지만 모든 코드를 디버그할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-150">Attaching to the service's process allows you to debug most, but not all, the code for that service.</span></span> <span data-ttu-id="fe832-151">예를 들어 서비스가 이미 시작되었기 때문에 이러한 방식으로 서비스를 로드하는 데 사용되는 서비스의 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드 내 코드나 `Main` 메서드 내의 코드는 디버그할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-151">For example, because the service has already been started, you cannot debug the code in the service's <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method or the code in the `Main` method that is used to load the service this way.</span></span> <span data-ttu-id="fe832-152">이 제한을 해결하는 한 가지 방법은 디버그에만 사용되는 두 번째 임시 서비스를 서비스 애플리케이션에 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-152">One way to work around this limitation is to create a temporary second service in your service application that exists only to aid in debugging.</span></span> <span data-ttu-id="fe832-153">두 서비스를 모두 설치하고서 이 더미 서비스를 시작하여 서비스 프로세스를 로드할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-153">You can install both services, and then start this dummy service to load the service process.</span></span> <span data-ttu-id="fe832-154">임시 서비스에서 프로세스를 시작하고 나면 Visual Studio에서 **디버그** 메뉴를 사용하여 서비스 프로세스에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-154">Once the temporary service has started the process, you can use the **Debug** menu in Visual Studio to attach to the service process.</span></span>  
  
 <span data-ttu-id="fe832-155">프로세스에 연결할 수 있을 때까지 <xref:System.Threading.Thread.Sleep%2A> 메서드에 대한 호출을 추가하여 작업을 지연시켜 봅니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-155">Try adding calls to the <xref:System.Threading.Thread.Sleep%2A> method to delay action until you’re able to attach to the process.</span></span>  
  
 <span data-ttu-id="fe832-156">프로그램을 일반 콘솔 애플리케이션으로 변경해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-156">Try changing the program to a regular console application.</span></span> <span data-ttu-id="fe832-157">이렇게 하려면 `Main` 메서드를 시작하는 방법에 따라 Windows 서비스와 콘솔 애플리케이션 둘 다로 실행할 수 있도록 다음과 같이 다시 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-157">To do this, rewrite the `Main` method as follows so it can run both as a Windows Service and as a console application, depending on how it's started.</span></span>  
  
#### <a name="how-to-run-a-windows-service-as-a-console-application"></a><span data-ttu-id="fe832-158">방법: 콘솔 애플리케이션으로 Windows 서비스 실행</span><span class="sxs-lookup"><span data-stu-id="fe832-158">How to: Run a Windows Service as a console application</span></span>  
  
1. <span data-ttu-id="fe832-159"><xref:System.ServiceProcess.ServiceBase.OnStart%2A> 및 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 메서드를 실행하는 서비스에 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-159">Add a method to your service that runs the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> methods:</span></span>  
  
    ```csharp  
    internal void TestStartupAndStop(string[] args)  
    {  
        this.OnStart(args);  
        Console.ReadLine();  
        this.OnStop();  
    }  
    ```  
  
2. <span data-ttu-id="fe832-160">`Main` 메서드를 다음과 같이 다시 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-160">Rewrite the `Main` method as follows:</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        if (Environment.UserInteractive)  
        {  
            MyNewService service1 = new MyNewService(args);  
            service1.TestStartupAndStop(args);  
        }  
        else  
        {  
            // Put the body of your old Main method here.  
        }  
    }
    ```  
  
3. <span data-ttu-id="fe832-161">프로젝트 속성의 **애플리케이션** 탭에서 **출력 형식** 을 **콘솔 애플리케이션** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-161">In the **Application** tab of the project's properties, set the **Output type** to **Console Application**.</span></span>  
  
4. <span data-ttu-id="fe832-162">**디버깅 시작**(F5)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-162">Choose **Start Debugging** (F5).</span></span>  
  
5. <span data-ttu-id="fe832-163">프로그램을 Windows 서비스로 다시 실행하려면 해당 프로그램을 설치하고 Windows 서비스를 시작하는 일반적인 방법으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-163">To run the program as a Windows Service again, install it and start it as usual for a Windows Service.</span></span> <span data-ttu-id="fe832-164">이러한 변경 내용을 되돌릴 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-164">It's not necessary to reverse these changes.</span></span>  
  
 <span data-ttu-id="fe832-165">시스템 시작 시에만 발생하는 문제를 디버그하려는 등의 일부 경우에는 Windows 디버거를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe832-165">In some cases, such as when you want to debug an issue that occurs only on system startup, you have to use the Windows debugger.</span></span> <span data-ttu-id="fe832-166">[WDK(Windows 드라이버 키트)를 다운로드](/windows-hardware/drivers/download-the-wdk)하고 [How to debug Windows Services](https://support.microsoft.com/kb/824344)(Windows 서비스를 디버그하는 방법)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe832-166">[Download the Windows Driver Kit (WDK)](/windows-hardware/drivers/download-the-wdk) and see [How to debug Windows Services](https://support.microsoft.com/kb/824344).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe832-167">참조</span><span class="sxs-lookup"><span data-stu-id="fe832-167">See also</span></span>

- [<span data-ttu-id="fe832-168">Windows 서비스 애플리케이션 소개</span><span class="sxs-lookup"><span data-stu-id="fe832-168">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="fe832-169">방법: 서비스 설치 및 제거</span><span class="sxs-lookup"><span data-stu-id="fe832-169">How to: Install and Uninstall Services</span></span>](how-to-install-and-uninstall-services.md)
- [<span data-ttu-id="fe832-170">방법: 서비스 시작</span><span class="sxs-lookup"><span data-stu-id="fe832-170">How to: Start Services</span></span>](how-to-start-services.md)
- [<span data-ttu-id="fe832-171">서비스 디버그</span><span class="sxs-lookup"><span data-stu-id="fe832-171">Debugging a Service</span></span>](/windows/desktop/Services/debugging-a-service)
