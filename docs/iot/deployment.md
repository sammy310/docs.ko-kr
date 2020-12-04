---
title: Raspberry Pi에 .NET 앱 배포
description: Raspberry Pi에 .NET 앱을 배포 하는 방법에 대해 알아봅니다.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: how-to
ms.prod: dotnet
ms.openlocfilehash: 4da558e2cdfc283d21f2a5497cb71dc746109614
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96594129"
---
# <a name="deploy-net-apps-to-raspberry-pi"></a>Raspberry Pi에 .NET 앱 배포

Raspberry Pi에 .NET 앱을 배포 하는 것은 다른 플랫폼의 경우와 동일 합니다. 앱은 *자체 포함* 또는 *프레임 워크 종속* 배포 모드로 실행할 수 있습니다. 각 전략에는 장점이 있습니다. 자세한 내용은 [.net 응용 프로그램 게시 개요](../core/deploying/index.md)를 참조 하세요.

## <a name="deploying-a-framework-dependent-app"></a>프레임 워크 종속 앱 배포

앱을 프레임 워크 종속 앱으로 배포 하려면 다음 단계를 완료 합니다.

1. [!INCLUDE [ensure-ssh](includes/ensure-ssh.md)]

1. [Dotnet 설치 스크립트](../core/tools/dotnet-install-script.md)를 사용 하 여 Raspberry Pi에 .net을 설치 합니다. Raspberry Pi (로컬 또는 SSH)의 Bash 프롬프트에서 다음 단계를 완료 합니다.
    1. 다음 명령을 실행 하 여 .NET을 설치 합니다.

        ```bash
        curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin
        ```

        > [!NOTE]
        > 이 방법으로 최신 버전을 설치합니다. 특정 버전이 필요한 경우 끝에를 추가 합니다 `--version <VERSION>` `<VERSION>` . 여기서은 특정 빌드 버전입니다.

    1. 경로 확인을 간소화 하려면 환경 변수를 추가 하 `DOTNET_ROOT` 고 다음 명령을 사용 하 여에 *. dotnet* 디렉터리를 추가 합니다. `$PATH`

        ```bash
        echo 'export DOTNET_ROOT=$HOME/.dotnet' >> ~/.bashrc
        echo 'export PATH=$PATH:$HOME/.dotnet' >> ~/.bashrc
        source ~/.bashrc
        ```

    1. 다음 명령을 사용 하 여 .NET 설치를 확인 합니다.

        ```dotnetcli
        dotnet --version
        ```

        표시 된 버전이 설치한 버전과 일치 하는지 확인 합니다.

1. 개발 환경에 따라 다음과 같이 개발 컴퓨터에 앱을 게시 합니다.
    - **Visual Studio** 를 사용 하는 경우 [로컬 폴더에 앱을 배포](/visualstudio/deployment/quickstart-deploy-to-local-folder?view=vs-2019)합니다. 게시 하기 전에 게시 프로필 요약에서 **편집** 을 선택 하 고 **설정** 탭을 선택 합니다. **배포 모드가** *프레임 워크 종속* 으로 설정 되 고 **대상 런타임이** *이식 가능* 으로 설정 되어 있는지 확인 합니다.
    - **.NET CLI** 를 사용 하는 경우 [dotnet publish](../core/tools/dotnet-publish.md) 명령을 사용 합니다. 추가 인수는 필요 하지 않습니다.

1. [!INCLUDE [sftp-client](includes/sftp-client.md)]

1. Raspberry Pi (로컬 또는 SSH)의 Bash 프롬프트에서 앱을 실행 합니다. 이렇게 하려면 배포 폴더를 현재 디렉터리로 설정 하 고 다음 명령을 실행 합니다. 여기서 *HelloWorld.dll* 는 앱의 진입점입니다.

    ```dotnetcli
    dotnet HelloWorld.dll
    ```

## <a name="deploying-a-self-contained-app"></a>자체 포함 된 앱 배포

앱을 자체 포함 된 앱으로 배포 하려면 다음 단계를 완료 합니다.

1. [!INCLUDE [ensure-ssh](includes/ensure-ssh.md)]

1. 개발 환경에 따라 다음과 같이 개발 컴퓨터에 앱을 게시 합니다.
    - **Visual Studio** 를 사용 하는 경우 [로컬 폴더에 앱을 배포](/visualstudio/deployment/quickstart-deploy-to-local-folder?view=vs-2019)합니다. 게시 하기 전에 게시 프로필 요약에서 **편집** 을 선택 하 고 **설정** 탭을 선택 합니다. **배포 모드가** *자체 포함* 된 것으로 설정 되 고 **대상 런타임이** *linux-arm* 으로 설정 되어 있는지 확인 합니다.
    - **.NET CLI** 를 사용 하는 경우 인수와 함께 [dotnet publish](../core/tools/dotnet-publish.md) 명령을 사용 합니다 `-r linux-arm` .

        ```dotnetcli
        dotnet publish -r linux-arm
        ```

1. [!INCLUDE [sftp-client](includes/sftp-client.md)]

1. Raspberry Pi (로컬 또는 SSH)의 Bash 프롬프트에서 앱을 실행 합니다. 이렇게 하려면 현재 디렉터리를 배포 위치로 설정 하 고 다음 단계를 완료 합니다.
    1. 실행 파일의 *실행 권한을 제공* 합니다 (여기서 `HelloWorld` 은 실행 파일 이름).

        ```bash
        chmod +x HelloWorld
        ```

    1. 실행 파일을 실행 합니다.

        ```bash
        ./HelloWorld
        ```
