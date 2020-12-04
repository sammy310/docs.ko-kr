---
title: Raspberry Pi에서 .NET 앱 디버그
description: Raspberry Pi 및 유사한 장치에서 .NET 앱을 디버깅 하는 방법에 대해 알아봅니다.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: how-to
ms.prod: dotnet
zone_pivot_groups: ide-set-one
ms.openlocfilehash: 7b9872304ee53071452772e3da02081a7def4d80
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2020
ms.locfileid: "96594016"
---
# <a name="debug-net-apps-on-raspberry-pi"></a>Raspberry Pi에서 .NET 앱 디버그

Raspberry Pi와 같은 ARM 기반 IoT 장치에서 실행 되는 .NET 앱을 디버깅 하면 고유한 챌린지를 제공 합니다. ARM 장치에서 .NET 앱을 개발할 수 있습니다. 그러나 Visual Studio 외부에서 .NET 앱을 디버깅 하는 데 필요한 OmniSharp는 ARM 장치와 호환 되지 않습니다. 따라서 호환 되는 플랫폼에서 응용 프로그램을 원격으로 디버깅 해야 합니다.

::: zone pivot="vscode"

## <a name="debug-from-visual-studio-code-cross-platform"></a>Visual Studio Code에서 디버그 (플랫폼 간)

Visual Studio Code에서 Raspberry Pi의 .NET을 디버깅 하려면 Raspberry Pi의 구성 단계와 파일 *의 프로젝트launch.js* 에 대 한 구성 단계가 필요 합니다.

### <a name="enable-ssh-on-the-raspberry-pi"></a>Raspberry Pi에서 SSH를 사용 하도록 설정

SSH는 원격 디버깅에 필요 합니다. SSH를 사용 하도록 설정 하려면 [Raspberry Pi 설명서에서 *ssh 사용* 을 참조](https://www.raspberrypi.org/documentation/remote-access/ssh/) <span class="docon docon-navigate-external x-hidden-focus"></span> 하세요.

### <a name="install-the-visual-studio-remote-debugger-on-the-raspberry-pi"></a>Raspberry Pi에 Visual Studio 원격 디버거를 설치 합니다.

Raspberry Pi (로컬 또는 SSH를 통해)의 Bash 콘솔 내에서 다음 단계를 완료 합니다.

1. 다음 명령을 실행 하 여 Raspberry Pi에 Visual Studio 원격 디버거를 다운로드 하 고 설치 합니다.

    ```bash
    curl -sSL https://aka.ms/getvsdbgsh | /bin/sh /dev/stdin -v latest -l ~/vsdbg
    ```

1. 디버거에서는를 실행 해야 `root` 합니다. 기본적으로 `root` Raspberry Pi에는 암호가 없습니다. 다음 명령을 실행 하 고 프롬프트에 따라에 대 한 암호를 설정 `root` 합니다.

    ```bash
    sudo passwd root
    ```

1. Visual Studio Code SSH 프로토콜을 사용 하 여 원격으로 디버깅 합니다. 보안상의 이유로 `root` 는 기본적으로 SSH를 통해 로그온 할 수 없습니다. SSH를 `root` 통해 로그온 할 수 있게 하려면 다음 단계를 완료 합니다.

    1. 다음 명령을 실행 하 여 [nano](https://www.nano-editor.org/docs.php) 에서 */etc/ssh/sshd_config* 를 엽니다 <span class="docon docon-navigate-external x-hidden-focus"></span> .

        ```bash
        sudo nano /etc/ssh/sshd_config
        ```

    1. <kbd>Ctrl + W</kbd> 를 누르고 **PermitRootLogin** 를 검색 합니다.
    1. 필요한 경우 **PermitRootLogin** 를 사용 하 여 줄의 주석 처리를 제거 합니다.
    1. 다음과 같이 줄을 다음과 같이 변경 합니다.

        ```console
        PermitRootLogin yes
        ```

        > [!NOTE]
        > */Etc/ssh/sshd_config* 에 **PermitRootLogin** 줄이 없으면 위에 표시 된 값이 있는 새 줄을 추가 합니다.

    1. <kbd>Ctrl + X</kbd> 를 눌러 종료 하 고 기회를 절감 합니다. 수정 된 **버퍼를 저장 하** 라는 메시지가 표시 되 면 <kbd>Y</kbd> 를 눌러 확인 합니다. <kbd>Enter</kbd> 키를 눌러 원본 파일 덮어쓰기를 확인 합니다.
    1. 다음 명령을 실행 하 여 Raspberry Pi를 다시 부팅 합니다.

        ```bash
        sudo reboot
        ```

### <a name="setup-launchjson-in-visual-studio-code"></a>Visual Studio Code의에 설정 launch.js

에서 프로젝트의 *launch.js* 에 시작 구성을 추가 합니다. 프로젝트에 파일 *에 대 한launch.js* 없는 경우 **실행** 탭으로 전환 하 여 **파일에 launch.js만들기** 를 선택 하 고 대화 상자에서 **.net** 또는 **.net Core** 를 선택 하 여 프로젝트를 추가 합니다.

*launch.js* 의 새 구성은 다음과 유사 합니다.

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

다음을 확인합니다.

- `program` 는 Pi의 .NET 런타임에 대 한 경로입니다.
- `args` Pi에서 디버그할 어셈블리의 경로입니다.
- `cwd` Pi에서 앱을 시작할 때 사용할 작업 디렉터리입니다.
- `pipeProgram` 는 로컬 컴퓨터의 SSH 클라이언트 경로입니다.
- `pipeArgs` SSH 클라이언트에 전달 되는 매개 변수입니다. 암호 매개 변수 및 형식의 사용자를 지정 해야 `root` `<user>@<hostname>` 합니다.

> [!IMPORTANT]
> 위의 예제에서는 [PuTTY](https://www.ssh.com/ssh/putty/) SSH 클라이언트의 구성 요소인 *plink* 를 사용 <span class="docon docon-navigate-external x-hidden-focus"></span> 합니다. [OpenSSH](https://www.openssh.com/) <span class="docon docon-navigate-external x-hidden-focus"></span> 최신 버전의 Windows 및 Linux에 포함 된 OpenSSH를 대신 사용할 수 있습니다. 그러나 OpenSSH은 명령줄 매개 변수로 암호 보내기를 지원 하지 않습니다. OpenSSH를 사용 하려면 [암호 없는 SSH 액세스에 대해 Raspberry Pi를 구성](https://www.raspberrypi.org/documentation/remote-access/ssh/passwordless.md) <span class="docon docon-navigate-external x-hidden-focus"></span> 합니다.

### <a name="deploy-the-app"></a>앱 배포

[Raspberry Pi에 .net 앱 배포](deployment.md)에 설명 된 대로 앱을 배포 합니다. 배포 경로가 `cwd` 구성 *의launch.js* 매개 변수에 지정 된 경로와 동일한 지 확인 합니다.

### <a name="launch-the-debugger"></a>디버거 시작

**실행** 탭에서 **.net Core 시작 (원격 콘솔)** 구성을 선택 하 고 **디버깅 시작** 을 선택 합니다. 앱이 Raspberry Pi에서 시작 됩니다. 디버거를 사용 하 여 중단점을 설정 하 고, 로컬 검사 등을 검사할 수 있습니다.

## <a name="references"></a>참조

[ARM의 .Net Core를 사용 하 여 Raspberry Pi에 대 한 Windows의 VS Code 원격 디버깅](https://www.hanselman.com/blog/remote-debugging-with-vs-code-on-windows-to-a-raspberry-pi-using-net-core-on-arm)<span class="docon docon-navigate-external x-hidden-focus"></span>

::: zone-end

::: zone pivot="visualstudio"

## <a name="debug-from-visual-studio-on-windows"></a>Windows의 Visual Studio에서 디버그

Visual Studio는 SSH를 통해 원격 장치의 .NET 앱을 디버그할 수 있습니다. 장치에 특별 한 구성이 필요 하지 않습니다. Visual Studio를 사용 하 여 .NET을 원격으로 디버깅 하는 방법에 대 한 자세한 내용은 [SSH를 사용 하 여 Linux의 원격 디버그 .net](/visualstudio/debugger/remote-debugging-dotnet-core-linux-with-ssh?view=vs-2019)

::: zone-end
