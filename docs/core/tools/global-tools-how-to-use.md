---
title: '자습서: .NET Core 전역 도구 설치 및 사용'
description: .NET 도구를 전역 도구로 설치하고 사용하는 방법을 알아봅니다.
ms.date: 02/12/2020
ms.openlocfilehash: 9f8378e50fd2544eedbbaaeffb89d67800ec6880
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156740"
---
# <a name="tutorial-install-and-use-a-net-core-global-tool-using-the-net-core-cli"></a>자습서: .NET Core CLI를 사용하여 .NET Core 전역 도구 설치 및 사용

**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전

이 자습서에서는 전역 도구를 설치하고 사용하는 방법을 설명합니다. [이 시리즈의 첫 번째 자습서](global-tools-how-to-create.md)에서 만든 도구를 사용합니다.

## <a name="prerequisites"></a>사전 요구 사항

* [이 시리즈의 첫 번째 자습서](global-tools-how-to-create.md)를 완료합니다.

## <a name="use-the-tool-as-a-global-tool"></a>도구를 전역 도구로 사용

1. *microsoft.botsay* 프로젝트 폴더에서 [dotnet tool install](dotnet-tool-install.md) 명령을 실행하여 패키지에서 도구를 설치합니다.

   ```dotnetcli
   dotnet tool install --global --add-source ./nupkg microsoft.botsay
   ```

   `--global` 매개 변수는 PATH 환경 변수에 자동으로 추가되는 기본 위치에 도구 이진 파일을 설치하도록 .NET Core CLI에 지시합니다.

   `--add-source` 매개 변수는 NuGet 패키지의 추가 소스 피드로 *./nupkg* 폴더를 임시로 사용하도록 .NET Core CLI에 지시합니다. 패키지에 고유한 이름을 지정하여 Nuget.org 사이트가 아니라 */nupkg* 디렉터리에서만 찾을 수 있는지 확인합니다.

   출력에서는 설치된 도구 및 버전을 호출하는 데 사용되는 명령을 보여 줍니다.

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
   ```

1. 도구를 호출합니다.

   ```console
   botsay hello from the bot
   ```

   > [!NOTE]
   > 이 명령이 실패하는 경우 PATH를 새로 고치기 위해 새 터미널을 열어야 할 수도 있습니다.

1. [dotnet tool uninstall](dotnet-tool-uninstall.md) 명령을 실행하여 도구를 제거합니다.

   ```dotnetcli
   dotnet tool uninstall -g microsoft.botsay
   ```

## <a name="use-the-tool-as-a-global-tool-installed-in-a-custom-location"></a>사용자 지정 위치에 설치된 전역 도구로 도구 사용

1. 패키지에서 도구를 설치합니다.

   Windows에서:

   ```dotnetcli
   dotnet tool install --tool-path c:\dotnet-tools --add-source ./nupkg microsoft.botsay
   ```

   Linux 또는 macOS에서:

   ```dotnetcli
   dotnet tool install --tool-path ~/bin --add-source ./nupkg microsoft.botsay
   ```

   `--tool-path` 매개 변수는 지정된 위치에 도구 이진 파일을 설치하도록 .NET Core CLI에 지시합니다. 디렉터리가 없는 경우 만들어집니다. 이 디렉터리는 PATH 환경 변수에 자동으로 추가되지 않습니다.

   출력에서는 설치된 도구 및 버전을 호출하는 데 사용되는 명령을 보여 줍니다.

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
   ```

1. 도구를 호출합니다.

   Windows에서:

   ```console
   c:\dotnet-tools\botsay hello from the bot
   ```

   Linux 또는 macOS에서:

   ```console
   ~/bin/botsay hello from the bot
   ```

1. [dotnet tool uninstall](dotnet-tool-uninstall.md) 명령을 실행하여 도구를 제거합니다.

   Windows에서:

   ```dotnetcli
   dotnet tool uninstall --tool-path c:\dotnet-tools microsoft.botsay
   ```

   Linux 또는 macOS에서:

   ```dotnetcli
   dotnet tool uninstall --tool-path ~/bin microsoft.botsay
   ```

## <a name="troubleshoot"></a>문제 해결

자습서를 수행하는 동안 오류 메시지가 표시되는 경우 [.NET Core 도구 사용 문제 해결](troubleshoot-usage-issues.md)을 참조하세요.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 도구를 전역 도구로 설치하고 사용했습니다. 로컬 도구와 동일한 도구를 설치하고 사용하려면 다음 자습서로 이동합니다.

> [!div class="nextstepaction"]
> [로컬 도구 설치 및 사용](local-tools-how-to-use.md)
