---
title: Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 게시
description: 게시하면 .NET Core 애플리케이션을 실행하는 데 필요한 파일 집합이 만들어집니다.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 44646a307d230db395b55b9dec5acfd168605940
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2020
ms.locfileid: "84701286"
---
# <a name="tutorial-publish-a-net-core-console-application-using-visual-studio"></a>자습서: Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 게시

이 자습서에서는 다른 사용자가 실행할 수 있도록 콘솔 앱을 게시하는 방법을 보여 줍니다. 게시하면 애플리케이션을 실행하는 데 필요한 파일 집합이 만들어집니다. 파일을 배포하려면 대상 컴퓨터로 복사합니다.

## <a name="prerequisites"></a>사전 요구 사항

- 이 자습서는 [Visual Studio 2019에서 .NET Core 콘솔 애플리케이션 만들기](with-visual-studio.md)에서 만든 콘솔 앱에 사용할 수 있습니다.

## <a name="publish-the-app"></a>앱 게시

1. Visual Studio를 시작합니다.

1. [Visual Studio에서 .NET Core 콘솔 애플리케이션 만들기](with-visual-studio.md)에서 만든 *HelloWorld* 프로젝트를 엽니다.

1. Visual Studio에서 릴리스 빌드 구성을 사용 중인지 확인합니다. 필요한 경우 도구 모음의 빌드 구성 설정을 **디버그**에서 **릴리스**로 변경합니다.

   ![릴리스 빌드가 선택된 Visual Studio 도구 모음](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. **HelloWorld** 프로젝트(HelloWorld 솔루션 아님)를 마우스 오른쪽 단추로 클릭하고 메뉴에서 **게시**를 선택합니다.

   ![Visual Studio 게시 상황에 맞는 메뉴](media/publishing-with-visual-studio/publish-context-menu.png)

1. **게시** 페이지의 **대상** 탭에서 **폴더**를 선택한 후 **다음**을 선택합니다.

   ![Visual Studio에서 게시 대상 선택](media/publishing-with-visual-studio/pick-publish-target.png)

1. **게시** 페이지의 **위치** 탭에서 **마침**을 선택합니다.

   ![Visual Studio 게시 페이지 위치 탭](media/publishing-with-visual-studio/publish-page-loc-tab.png)

1. **게시** 창의 **게시** 탭에서 **게시**를 선택합니다.

   ![Visual Studio 게시 창](media/publishing-with-visual-studio/publish-page.png)

## <a name="inspect-the-files"></a>파일 검사

기본적으로 게시 프로세스는 프레임워크 종속 배포를 만듭니다. 이 배포는 .NET Core 런타임이 설치된 머신에서 게시된 애플리케이션이 실행되는 배포 유형입니다. 사용자는 실행 파일을 두 번 클릭하거나 명령 프롬프트에서 `dotnet HelloWorld.dll` 명령을 실행하여 게시된 앱을 실행할 수 있습니다.

다음 단계에서는 게시 프로세스를 통해 생성된 파일을 살펴봅니다.

1. **솔루션 탐색기**에서 **모든 파일 표시**를 선택합니다.

1. 프로젝트 폴더에서 *bin/Release/netcoreapp3.1/publish*를 확장합니다.

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="게시된 파일을 보여 주는 솔루션 탐색기":::

   그림에 표시된 것과 같이 게시된 출력에는 다음 파일이 포함되어 있습니다.

   * *HelloWorld.deps.json*

      애플리케이션의 런타임 종속성 파일입니다. 애플리케이션을 실행하는 데 필요한 .NET Core 구성 요소 및 라이브러리(애플리케이션을 포함하는 동적 연결 라이브러리 포함)를 정의합니다. 자세한 내용은 [런타임 구성 파일](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md)을 참조하세요.

   * *HelloWorld.dll*

      애플리케이션의 [프레임워크 종속 배포](../deploying/deploy-with-cli.md#framework-dependent-deployment)입니다. 이 동적 연결 라이브러리를 실행하려면 명령 프롬프트에 `dotnet HelloWorld.dll`을 입력합니다. 앱을 실행하는 이 메서드는 .NET Core 런타임이 설치된 모든 플랫폼에서 작동합니다.

   * *HelloWorld.exe*

      애플리케이션의 [프레임워크 종속 실행 파일](../deploying/deploy-with-cli.md#framework-dependent-executable)입니다. 이를 실행하려면 명령 프롬프트에서 `HelloWorld.exe`를 입력합니다. 이 파일은 운영 체제마다 다릅니다.

   * *HelloWorld.pdb*(배포에 대한 선택 사항)

      디버그 기호 파일입니다. 게시된 애플리케이션 버전을 디버그해야 하는 경우에는 이 파일을 저장해야 하지만 그렇지 않으면 애플리케이션과 함께 배포할 필요가 없습니다.

   * *HelloWorld.runtimeconfig.json*

      애플리케이션의 런타임 구성 파일입니다. 애플리케이션이 실행되도록 빌드된 .NET Core의 버전을 식별합니다. 구성 옵션을 추가할 수도 있습니다. 자세한 내용은 [.NET Core 런타임 구성 설정](../run-time-config/index.md#runtimeconfigjson)을 참조하세요.

## <a name="run-the-published-app"></a>게시된 앱 실행

1. **솔루션 탐색기**에서 *publish* 폴더를 마우스 오른쪽 단추로 클릭하고 **전체 경로 복사**를 선택합니다.

1. 명령 프롬프트를 열고 *publish* 폴더로 이동합니다. 이를 위해 `cd`를 입력한 다음 전체 경로를 붙여넣습니다. 예를 들어:

   ```
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. 실행 파일을 사용하여 앱을 실행합니다.

   1. `HelloWorld.exe`를 입력하고 <kbd>Enter</kbd> 키를 누릅니다.

   1. 프롬프트에 대한 응답으로 이름을 입력하고 아무 키나 눌러 종료합니다.

1. `dotnet` 명령을 사용하여 앱을 실행합니다.

   1. `dotnet HelloWorld.dll`을 입력하고 <kbd>Enter</kbd> 키를 누릅니다.

   1. 프롬프트에 대한 응답으로 이름을 입력하고 아무 키나 눌러 종료합니다.

## <a name="additional-resources"></a>추가 자료

- [.NET Core 애플리케이션 배포](../deploying/index.md)

## <a name="next-steps"></a>다음 단계

이 자습서에서는 콘솔 앱을 게시했습니다. 다음 자습서에서는 클래스 라이브러리를 만듭니다.

> [!div class="nextstepaction"]
> [Visual Studio에서 .NET Standard 라이브러리 만들기](library-with-visual-studio.md)
