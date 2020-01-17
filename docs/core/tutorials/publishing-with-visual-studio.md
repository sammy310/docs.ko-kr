---
title: Visual Studio를 사용하여 .NET Core Hello World 애플리케이션 게시
description: 게시하면 .NET Core 애플리케이션을 실행하는 데 필요한 파일 집합이 만들어집니다.
author: BillWagner
ms.author: wiwagn
ms.date: 12/10/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 485d62ce67f284fe1bbe931dcaa00671be154f35
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715363"
---
# <a name="publish-your-net-core-hello-world-application-with-visual-studio"></a>Visual Studio를 사용하여 .NET Core Hello World 애플리케이션 게시

[Visual Studio에서 .NET Core를 사용하여 Hello World 애플리케이션 만들기](with-visual-studio.md)에서 Hello World 콘솔 애플리케이션을 빌드했습니다. [Visual Studio을 사용하여 Hello World 애플리케이션 디버그](debugging-with-visual-studio.md)에서 Visual Studio 디버거를 사용하여 테스트했습니다. 예상대로 작동하는지 확인했으므로 다른 사용자가 실행할 수 있도록 게시할 수 있습니다. 게시하면 애플리케이션을 실행하는 데 필요한 파일 집합이 만들어집니다. 파일을 배포하려면 대상 컴퓨터로 복사합니다.

## <a name="publish-the-app"></a>앱 게시

1. Visual Studio에서 애플리케이션의 릴리스 버전을 빌드하고 있는지 확인합니다. 필요한 경우 도구 모음의 빌드 구성 설정을 **디버그**에서 **릴리스**로 변경합니다.

   ![릴리스 빌드가 선택된 Visual Studio 도구 모음](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. **HelloWorld** 프로젝트(HelloWorld 솔루션 아님)를 마우스 오른쪽 단추로 클릭하고 메뉴에서 **게시**를 선택합니다. (주 **빌드** 메뉴에서 **HelloWorld 게시**를 선택할 수도 있습니다.)

   ![Visual Studio 게시 상황에 맞는 메뉴](media/publishing-with-visual-studio/publish-context-menu.png)
   
1. **게시 대상 선택** 페이지에서 **폴더**를 선택한 다음 **프로필 만들기**를 선택합니다.

   ![Visual Studio에서 게시 대상 선택](media/publishing-with-visual-studio/pick-publish-target.png)
   
1. **게시** 페이지에서 **게시**를 선택합니다.

   ![Visual Studio 게시 창](media/publishing-with-visual-studio/publish-page.png)
   
## <a name="inspect-the-files"></a>파일 검사

게시 프로세스는 프레임워크 종속 배포를 만듭니다. 이 배포는 시스템에 .NET Core가 설치되어 있으면 게시된 애플리케이션이 .NET Core에서 지원하는 모든 플랫폼에서 실행되는 배포 유형입니다. 사용자는 실행 파일을 두 번 클릭하거나 명령 프롬프트에서 `dotnet HelloWorld.dll` 명령을 실행하여 게시된 앱을 실행할 수 있습니다.

다음 단계에서는 게시 프로세스를 통해 생성된 파일을 살펴봅니다.

1. 명령 프롬프트를 엽니다.

   명령 프롬프트를 여는 방법 중 하나는 Windows 작업 표시줄의 검색 상자에서 **명령 프롬프트**(또는 **cmd**)를 입력하는 것입니다. **명령 프롬프트** 데스크톱 앱을 선택하거나 검색 결과에서 이미 선택되어 있는 경우 **Enter** 키를 누릅니다.

1. 애플리케이션 프로젝트 디렉터리의 *bin\Release\netcoreapp3.1\publish* 하위 디렉터리에 게시된 애플리케이션으로 이동합니다.

   ![게시된 파일을 보여 주는 콘솔 창](media/publishing-with-visual-studio/published-files-output.png)

   그림에 표시된 것과 같이 게시된 출력에는 다음 파일이 포함되어 있습니다.

      * *HelloWorld.deps.json*

         애플리케이션의 런타임 종속성 파일입니다. 애플리케이션을 실행하는 데 필요한 .NET Core 구성 요소 및 라이브러리(애플리케이션을 포함하는 동적 연결 라이브러리 포함)를 정의합니다. 자세한 내용은 [런타임 구성 파일](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md)을 참조하세요.

      * *HelloWorld.dll*

         애플리케이션의 [프레임워크 종속 배포](../deploying/deploy-with-cli.md#framework-dependent-deployment)입니다. 이 동적 연결 라이브러리를 실행하려면 명령 프롬프트에 `dotnet HelloWorld.dll`을 입력합니다.

      * *HelloWorld.exe*
      
         애플리케이션의 [프레임워크 종속 실행 파일](../deploying/deploy-with-cli.md#framework-dependent-executable)입니다. 이를 실행하려면 명령 프롬프트에서 `HelloWorld.exe`를 입력합니다.

      * *HelloWorld.pdb*(배포에 대한 선택 사항)

         디버그 기호 파일입니다. 게시된 애플리케이션 버전을 디버그해야 하는 경우에는 이 파일을 저장해야 하지만 그렇지 않으면 애플리케이션과 함께 배포할 필요가 없습니다.

      * *HelloWorld.runtimeconfig.json*

         애플리케이션의 런타임 구성 파일입니다. 애플리케이션이 실행되도록 빌드된 .NET Core의 버전을 식별합니다. 자세한 내용은 [런타임 구성 파일](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md)을 참조하세요.

## <a name="additional-resources"></a>추가 자료

- [.NET Core 애플리케이션 배포](../deploying/index.md)
