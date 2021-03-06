---
title: Raspberry Pi에서 .NET 앱 디버그
description: Raspberry Pi 및 유사한 장치에서 .NET 앱을 디버깅 하는 방법에 대해 알아봅니다.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: how-to
ms.prod: dotnet
zone_pivot_groups: ide-set-one
ms.openlocfilehash: 58858384c49a296e0b33d663f3ef930caf9cace6
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258067"
---
# <a name="debug-net-apps-on-raspberry-pi"></a><span data-ttu-id="52785-103">Raspberry Pi에서 .NET 앱 디버그</span><span class="sxs-lookup"><span data-stu-id="52785-103">Debug .NET apps on Raspberry Pi</span></span>

<span data-ttu-id="52785-104">Raspberry Pi와 같은 ARM 기반 IoT 장치에서 실행 되는 .NET 앱을 디버깅 하면 고유한 챌린지를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-104">Debugging .NET apps running on ARM-based IoT devices like Raspberry Pi presents a unique challenge.</span></span> <span data-ttu-id="52785-105">ARM 장치에서 .NET 앱을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52785-105">It is possible to develop .NET apps on ARM devices.</span></span> <span data-ttu-id="52785-106">그러나 Visual Studio 외부에서 .NET 앱을 디버깅 하는 데 필요한 OmniSharp는 ARM 장치와 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52785-106">However, OmniSharp, which is required for debugging .NET apps outside of Visual Studio, is not compatible with ARM devices.</span></span> <span data-ttu-id="52785-107">따라서 호환 되는 플랫폼에서 응용 프로그램을 원격으로 디버깅 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-107">As a result, apps must be debugged remotely from a compatible platform.</span></span>

::: zone pivot="vscode"

## <a name="debug-from-visual-studio-code-cross-platform"></a><span data-ttu-id="52785-108">Visual Studio Code에서 디버그 (플랫폼 간)</span><span class="sxs-lookup"><span data-stu-id="52785-108">Debug from Visual Studio Code (cross-platform)</span></span>

<span data-ttu-id="52785-109">Visual Studio Code에서 Raspberry Pi의 .NET을 디버깅 하려면 Raspberry Pi의 구성 단계와 파일 *의 프로젝트launch.js* 에 대 한 구성 단계가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-109">Debugging .NET on Raspberry Pi from Visual Studio Code requires configuration steps on the Raspberry Pi and in the project's *launch.json* file.</span></span>

### <a name="enable-ssh-on-the-raspberry-pi"></a><span data-ttu-id="52785-110">Raspberry Pi에서 SSH를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="52785-110">Enable SSH on the Raspberry Pi</span></span>

<span data-ttu-id="52785-111">SSH는 원격 디버깅에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-111">SSH is required for remote debugging.</span></span> <span data-ttu-id="52785-112">SSH를 사용 하도록 설정 하려면 [Raspberry Pi 설명서에서 *ssh 사용* 을 참조](https://www.raspberrypi.org/documentation/remote-access/ssh/)하세요.</span><span class="sxs-lookup"><span data-stu-id="52785-112">To enable SSH, [refer to *Enable SSH* in the Raspberry Pi documentation](https://www.raspberrypi.org/documentation/remote-access/ssh/).</span></span>

### <a name="install-the-visual-studio-remote-debugger-on-the-raspberry-pi"></a><span data-ttu-id="52785-113">Raspberry Pi에 Visual Studio 원격 디버거를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-113">Install the Visual Studio Remote Debugger on the Raspberry Pi</span></span>

<span data-ttu-id="52785-114">Raspberry Pi (로컬 또는 SSH를 통해)의 Bash 콘솔 내에서 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-114">Within a Bash console on the Raspberry Pi (either locally or via SSH), complete the following steps:</span></span>

1. <span data-ttu-id="52785-115">다음 명령을 실행 하 여 Raspberry Pi에 Visual Studio 원격 디버거를 다운로드 하 고 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-115">Execute the following command to download and install the Visual Studio Remote Debugger on the Raspberry Pi:</span></span>

    ```bash
    curl -sSL https://aka.ms/getvsdbgsh | /bin/sh /dev/stdin -v latest -l ~/vsdbg
    ```

1. <span data-ttu-id="52785-116">디버거에서는를 실행 해야 `root` 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-116">The debugger requires running as `root`.</span></span> <span data-ttu-id="52785-117">기본적으로 `root` Raspberry Pi에는 암호가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52785-117">By default, `root` has no password on Raspberry Pi.</span></span> <span data-ttu-id="52785-118">다음 명령을 실행 하 고 프롬프트에 따라에 대 한 암호를 설정 `root` 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-118">Set a password for `root` by executing the following command and following the prompts.</span></span>

    ```bash
    sudo passwd root
    ```

1. <span data-ttu-id="52785-119">Visual Studio Code SSH 프로토콜을 사용 하 여 원격으로 디버깅 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-119">Visual Studio Code uses the SSH protocol to debug remotely.</span></span> <span data-ttu-id="52785-120">보안상의 이유로 `root` 는 기본적으로 SSH를 통해 로그온 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52785-120">For security purposes, `root` is not permitted to log on via SSH by default.</span></span> <span data-ttu-id="52785-121">SSH를 `root` 통해 로그온 할 수 있게 하려면 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-121">To enable `root` to log on via SSH, complete the following steps:</span></span>

    1. <span data-ttu-id="52785-122">다음 명령을 실행 하 여 [nano](https://www.nano-editor.org/docs.php)에서 */etc/ssh/sshd_config* 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="52785-122">Execute the following command to open */etc/ssh/sshd_config* in [nano](https://www.nano-editor.org/docs.php).</span></span>

        ```bash
        sudo nano /etc/ssh/sshd_config
        ```

    1. <span data-ttu-id="52785-123"><kbd>Ctrl + W</kbd> 를 누르고 **PermitRootLogin** 를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-123">Press <kbd>Ctrl+W</kbd> and search for **PermitRootLogin**.</span></span>
    1. <span data-ttu-id="52785-124">필요한 경우 **PermitRootLogin** 를 사용 하 여 줄의 주석 처리를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-124">Uncomment the line with **PermitRootLogin** if needed.</span></span>
    1. <span data-ttu-id="52785-125">다음과 같이 줄을 다음과 같이 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-125">Change the line to read as follows:</span></span>

        ```console
        PermitRootLogin yes
        ```

        > [!NOTE]
        > <span data-ttu-id="52785-126">*/Etc/ssh/sshd_config* 에 **PermitRootLogin** 줄이 없으면 위에 표시 된 값이 있는 새 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-126">If there is no **PermitRootLogin** line in */etc/ssh/sshd_config*, add a new line with the value shown above.</span></span>

    1. <span data-ttu-id="52785-127"><kbd>Ctrl + X</kbd> 를 눌러 종료 하 고 기회를 절감 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-127">Press <kbd>Ctrl+X</kbd> to exit and save your chances.</span></span> <span data-ttu-id="52785-128">수정 된 **버퍼를 저장 하** 라는 메시지가 표시 되 면 <kbd>Y</kbd> 를 눌러 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-128">When prompted **Save modified buffer?**, press <kbd>Y</kbd> to confirm.</span></span> <span data-ttu-id="52785-129"><kbd>Enter</kbd> 키를 눌러 원본 파일 덮어쓰기를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-129">Press <kbd>Enter</kbd> to confirm overwriting the original file.</span></span>
    1. <span data-ttu-id="52785-130">다음 명령을 실행 하 여 Raspberry Pi를 다시 부팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-130">Reboot the Raspberry Pi by executing the following command:</span></span>

        ```bash
        sudo reboot
        ```

### <a name="setup-launchjson-in-visual-studio-code"></a><span data-ttu-id="52785-131">Visual Studio Code의에 설정 launch.js</span><span class="sxs-lookup"><span data-stu-id="52785-131">Setup launch.json in Visual Studio Code</span></span>

<span data-ttu-id="52785-132">에서 프로젝트의 *launch.js* 에 시작 구성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-132">Add a launch configuration to the project's *launch.json*.</span></span> <span data-ttu-id="52785-133">프로젝트에 파일 *에 대 한launch.js* 없는 경우 **실행** 탭으로 전환 하 여 **파일에 launch.js만들기** 를 선택 하 고 대화 상자에서 **.net** 또는 **.net Core** 를 선택 하 여 프로젝트를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-133">If the project doesn't have a *launch.json* file, add one by switching to the **Run** tab, selecting **create a launch.json file**, and selecting **.NET** or **.NET Core** in the dialog.</span></span>

<span data-ttu-id="52785-134">*launch.js* 의 새 구성은 다음과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-134">The new configuration in *launch.json* should look similar to this:</span></span>

```json
"configurations": [
    {
        "name": ".NET Core Launch (remote console)",
        "type": "coreclr",
        "request": "launch",
        "preLaunchTask": "build",
        "program": "/home/pi/.dotnet/dotnet",
        "args": ["/home/pi/sample/Sample.dll"],
        "cwd": "/home/pi/sample",
        "stopAtEntry": false,
        "console": "internalConsole",
        "pipeTransport": {
            "pipeCwd": "${workspaceFolder}",
            "pipeProgram": "C:\\Program Files\\PuTTY\\PLINK.EXE",
            "pipeArgs": [
                "-pw",
                "P@ssw0rd",
                "root@raspberrypi"
            ],
            "debuggerPath": "/home/pi/vsdbg/vsdbg"
        }
    },
```

<span data-ttu-id="52785-135">다음을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-135">Notice the following:</span></span>

- <span data-ttu-id="52785-136">`program` 는 Pi의 .NET 런타임에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="52785-136">`program` is the path to the .NET runtime on the Pi.</span></span>
- <span data-ttu-id="52785-137">`args` Pi에서 디버그할 어셈블리의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="52785-137">`args` is the path to the assembly to debug on the Pi.</span></span>
- <span data-ttu-id="52785-138">`cwd` Pi에서 앱을 시작할 때 사용할 작업 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="52785-138">`cwd` is the working directory to use when launching the app on the Pi.</span></span>
- <span data-ttu-id="52785-139">`pipeProgram` 는 로컬 컴퓨터의 SSH 클라이언트 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="52785-139">`pipeProgram` is the path to an SSH client on the local machine.</span></span>
- <span data-ttu-id="52785-140">`pipeArgs` SSH 클라이언트에 전달 되는 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="52785-140">`pipeArgs` are the parameters to be passed to the SSH client.</span></span> <span data-ttu-id="52785-141">암호 매개 변수 및 형식의 사용자를 지정 해야 `root` `<user>@<hostname>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-141">Be sure to specify the password parameter, as well as the `root` user in the format `<user>@<hostname>`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52785-142">위의 예제에서는 [PuTTY](https://www.ssh.com/ssh/putty/) SSH 클라이언트의 구성 요소인 *plink* 를 사용 <span class="docon docon-navigate-external x-hidden-focus"></span> 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-142">The above example uses *plink*, a component of the [PuTTY](https://www.ssh.com/ssh/putty/)<span class="docon docon-navigate-external x-hidden-focus"></span> SSH client.</span></span> <span data-ttu-id="52785-143">[](https://www.openssh.com/) <span class="docon docon-navigate-external x-hidden-focus"></span> 최신 버전의 Windows 및 Linux에 포함 된 OpenSSH를 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52785-143">[OpenSSH](https://www.openssh.com/)<span class="docon docon-navigate-external x-hidden-focus"></span>, which is included in recent versions of Windows and Linux, may be used instead.</span></span> <span data-ttu-id="52785-144">그러나 OpenSSH은 명령줄 매개 변수로 암호 보내기를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52785-144">However, OpenSSH doesn't support sending passwords as a command-line parameter.</span></span> <span data-ttu-id="52785-145">OpenSSH를 사용 하려면 [암호 없는 SSH 액세스에 대해 Raspberry Pi를 구성](https://www.raspberrypi.org/documentation/remote-access/ssh/passwordless.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-145">To use OpenSSH, [configure your Raspberry Pi for passwordless SSH access](https://www.raspberrypi.org/documentation/remote-access/ssh/passwordless.md).</span></span>

### <a name="deploy-the-app"></a><span data-ttu-id="52785-146">앱 배포</span><span class="sxs-lookup"><span data-stu-id="52785-146">Deploy the app</span></span>

<span data-ttu-id="52785-147">[Raspberry Pi에 .net 앱 배포](deployment.md)에 설명 된 대로 앱을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-147">Deploy the app as described in [Deploy .NET apps to Raspberry Pi](deployment.md).</span></span> <span data-ttu-id="52785-148">배포 경로가 `cwd` 구성 *의launch.js* 매개 변수에 지정 된 경로와 동일한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-148">Ensure the deployment path is the same path specified in the `cwd` parameter in the *launch.json* configuration.</span></span>

### <a name="launch-the-debugger"></a><span data-ttu-id="52785-149">디버거 시작</span><span class="sxs-lookup"><span data-stu-id="52785-149">Launch the debugger</span></span>

<span data-ttu-id="52785-150">**실행** 탭에서 **.net Core 시작 (원격 콘솔)** 구성을 선택 하 고 **디버깅 시작** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="52785-150">On the **Run** tab, select the **.NET Core Launch (remote console)** configuration and select **Start Debugging**.</span></span> <span data-ttu-id="52785-151">앱이 Raspberry Pi에서 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52785-151">The app launches on the Raspberry Pi.</span></span> <span data-ttu-id="52785-152">디버거를 사용 하 여 중단점을 설정 하 고, 로컬 검사 등을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52785-152">The debugger may be used to set breakpoints, inspect locals, and more.</span></span>

## <a name="references"></a><span data-ttu-id="52785-153">참조</span><span class="sxs-lookup"><span data-stu-id="52785-153">References</span></span>

[<span data-ttu-id="52785-154">ARM의 .NET Core를 사용 하 여 Raspberry Pi에 대 한 Windows의 VS Code 원격 디버깅</span><span class="sxs-lookup"><span data-stu-id="52785-154">Remote debugging with VS Code on Windows to a Raspberry Pi using .NET Core on ARM</span></span>](https://www.hanselman.com/blog/remote-debugging-with-vs-code-on-windows-to-a-raspberry-pi-using-net-core-on-arm)

::: zone-end

::: zone pivot="visualstudio"

## <a name="debug-from-visual-studio-on-windows"></a><span data-ttu-id="52785-155">Windows의 Visual Studio에서 디버그</span><span class="sxs-lookup"><span data-stu-id="52785-155">Debug from Visual Studio on Windows</span></span>

<span data-ttu-id="52785-156">Visual Studio는 SSH를 통해 원격 장치의 .NET 앱을 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52785-156">Visual Studio can debug .NET apps on remote devices via SSH.</span></span> <span data-ttu-id="52785-157">장치에 특별 한 구성이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52785-157">No specialized configuration is required on the device.</span></span> <span data-ttu-id="52785-158">Visual Studio를 사용 하 여 .NET을 원격으로 디버깅 하는 방법에 대 한 자세한 내용은 [SSH를 사용 하 여 Linux의 원격 디버그 .net](/visualstudio/debugger/remote-debugging-dotnet-core-linux-with-ssh?view=vs-2019)</span><span class="sxs-lookup"><span data-stu-id="52785-158">For details on using Visual Studio to debug .NET remotely, see [Remote debug .NET on Linux using SSH](/visualstudio/debugger/remote-debugging-dotnet-core-linux-with-ssh?view=vs-2019).</span></span>

::: zone-end
