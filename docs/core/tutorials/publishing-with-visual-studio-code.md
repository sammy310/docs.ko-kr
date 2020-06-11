---
title: Visual Studio Code를 사용하여 .NET Core Hello World 애플리케이션 게시
description: 게시하면 .NET Core 애플리케이션을 실행하는 데 필요한 파일 집합이 만들어집니다.
ms.date: 05/28/2020
ms.openlocfilehash: b49b12bf41e3ea7be8dbc459eb7d9b1fbef25790
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2020
ms.locfileid: "84246657"
---
# <a name="tutorial-publish-a-net-core-console-application-with-visual-studio-code"></a>자습서: Visual Studio Code를 사용하여 .NET Core 콘솔 애플리케이션 게시

이 자습서에서는 다른 사용자가 실행할 수 있도록 콘솔 앱을 게시하는 방법을 보여 줍니다. 게시하면 애플리케이션을 실행하는 데 필요한 파일 집합이 만들어집니다. 파일을 배포하려면 대상 컴퓨터로 복사합니다.

.NET Core CLI는 앱을 게시하는 데 사용됩니다. 원하는 경우 이 자습서에 따라 Visual Studio Code 외의 다른 코드 편집기를 사용할 수 있습니다.

## <a name="prerequisites"></a>사전 요구 사항

- 이 자습서는 [Visual Studio Code에서 .NET Core 콘솔 애플리케이션 만들기](with-visual-studio-code.md)에서 만든 콘솔 앱에 사용할 수 있습니다.

## <a name="publish-the-app"></a>앱 게시

1. Visual Studio Code를 엽니다.

1. [Visual Studio Code에서 .NET Core 콘솔 애플리케이션 만들기](with-visual-studio-code.md)에서 만든 *HelloWorld* 프로젝트 폴더를 엽니다.

1. 주 메뉴에서 **보기** > **터미널**을 선택합니다.

   터미널이 *HelloWorld* 폴더에서 열립니다.

1. 다음 명령을 실행합니다.

   ```dotnetcli
   dotnet publish --configuration Release
   ```

   기본 빌드 구성은 ‘디버그’이므로 이 명령은 ‘릴리스’ 빌드 구성을 지정합니다.  릴리스 빌드 구성의 출력은 최소한의 기호 디버그 정보를 포함하고 있으며 완전히 최적화되어 있습니다.

   명령 출력은 다음 예제와 유사합니다.

   ```
   Microsoft (R) Build Engine version 16.6.0+5ff7b0c9e for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.

   Determining projects to restore...
   All projects are up-to-date for restore.
   HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\HelloWorld.dll
   HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

## <a name="inspect-the-files"></a>파일 검사

기본적으로 게시 프로세스는 프레임워크 종속 배포를 만듭니다. 이 배포는 .NET Core 런타임이 설치된 머신에서 게시된 애플리케이션이 실행되는 배포 유형입니다. 게시된 앱을 실행하려면 실행 파일을 사용하거나 명령 프롬프트에서 `dotnet HelloWorld.dll` 명령을 실행하면 됩니다.

다음 단계에서는 게시 프로세스를 통해 생성된 파일을 살펴봅니다.

1. 왼쪽 탐색 모음에서 **Explorer**를 선택합니다.

1. *bin/Release/netcoreapp3.1/publish*를 확장합니다.

   :::image type="content" source="media/publishing-with-visual-studio-code/published-files-output.png" alt-text="게시된 파일을 보여 주는 Explorer":::

   그림에 표시된 것과 같이 게시된 출력에는 다음 파일이 포함되어 있습니다.

   * *HelloWorld.deps.json*

      애플리케이션의 런타임 종속성 파일입니다. 애플리케이션을 실행하는 데 필요한 .NET Core 구성 요소 및 라이브러리(애플리케이션을 포함하는 동적 연결 라이브러리 포함)를 정의합니다. 자세한 내용은 [런타임 구성 파일](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md)을 참조하세요.

   * *HelloWorld.dll*

      애플리케이션의 [프레임워크 종속 배포](../deploying/deploy-with-cli.md#framework-dependent-deployment)입니다. 이 동적 연결 라이브러리를 실행하려면 명령 프롬프트에 `dotnet HelloWorld.dll`을 입력합니다. 앱을 실행하는 이 메서드는 .NET Core 런타임이 설치된 모든 플랫폼에서 작동합니다.

   * *HelloWorld.exe*(Linux에서는 *HelloWorld*, macOS에서는 생성되지 않음)

      애플리케이션의 [프레임워크 종속 실행 파일](../deploying/deploy-with-cli.md#framework-dependent-executable)입니다. 이 파일은 운영 체제마다 다릅니다.

   * *HelloWorld.pdb*(배포에 대한 선택 사항)

      디버그 기호 파일입니다. 게시된 애플리케이션 버전을 디버그해야 하는 경우에는 이 파일을 저장해야 하지만 그렇지 않으면 애플리케이션과 함께 배포할 필요가 없습니다.

   * *HelloWorld.runtimeconfig.json*

      애플리케이션의 런타임 구성 파일입니다. 애플리케이션이 실행되도록 빌드된 .NET Core의 버전을 식별합니다. 구성 옵션을 추가할 수도 있습니다. 자세한 내용은 [.NET Core 런타임 구성 설정](../run-time-config/index.md#runtimeconfigjson)을 참조하세요.

## <a name="run-the-published-app"></a>게시된 앱 실행

1. **Explorer**에서 *publish* 폴더를 마우스 오른쪽 단추로 클릭(또는 macOS의 경우 <kbd>Ctrl</kbd> 키를 누른 상태로 클릭)하고 **터미널에서 열기**를 선택합니다.

   :::image type="content" source="media/publishing-with-visual-studio-code/open-in-terminal.png" alt-text="터미널에서 열기를 보여 주는 상황에 맞는 메뉴":::

1. Windows 또는 Linux에서 실행 파일을 사용하여 앱을 실행합니다.

   1. Windows에서 `.\HelloWorld.exe`를 입력하고 <kbd>Enter</kbd> 키를 누릅니다.

   1. Linux에서 `./HelloWorld`를 입력하고 <kbd>Enter</kbd> 키를 누릅니다.

   1. 프롬프트에 대한 응답으로 이름을 입력하고 아무 키나 눌러 종료합니다.

1. 모든 플랫폼에서 [`dotnet`](../tools/dotnet.md) 명령을 사용하여 앱을 실행합니다.

   1. `dotnet HelloWorld.dll`을 입력하고 <kbd>Enter</kbd> 키를 누릅니다.

   1. 프롬프트에 대한 응답으로 이름을 입력하고 아무 키나 눌러 종료합니다.

## <a name="additional-resources"></a>추가 자료

- [.NET Core 애플리케이션 배포](../deploying/index.md)

## <a name="next-steps"></a>다음 단계

이 자습서에서는 콘솔 앱을 게시했습니다. 라이브러리를 빌드하는 방법에 대한 자세한 내용은 [.NET Core CLI를 사용하여 라이브러리 개발](libraries.md)을 참조하세요.

<!--In the next tutorial, you create a class library.

> [!div class="nextstepaction"]
> [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md)
-->
