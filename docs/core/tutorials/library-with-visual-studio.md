---
title: Visual Studio에서 .NET Standard 클래스 라이브러리 만들기
description: Visual Studio를 사용하여 .NET Standard 클래스 라이브러리를 만드는 방법을 알아봅니다.
ms.date: 05/21/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 2afe11ad75fc36a67efed48d56dbafb11bceaf2a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005269"
---
# <a name="tutorial-create-a-net-standard-library-in-visual-studio"></a>자습서: Visual Studio에서 .NET Standard 라이브러리 만들기

*클래스 라이브러리*는 애플리케이션에서 호출되는 형식 및 메서드를 정의합니다. .NET Standard 2.0을 대상으로 하는 클래스 라이브러리는 .NET Standard의 해당 버전을 지원하는 모든 .NET 구현에서 라이브러리를 호출할 수 있습니다. 클래스 라이브러리를 마칠 때 타사 구성 요소로 배포할지 또는 하나 이상의 애플리케이션과 함께 번들 구성 요소로 포함할지 결정할 수 있습니다.

> [!NOTE]
> .NET Standard 버전 및 지원되는 플랫폼 목록은 [.NET Standard](../../standard/net-standard.md)를 참조하세요.

이 자습서에서는 단일 문자열 처리 메서드를 포함하는 간단한 유틸리티 라이브러리를 만듭니다. <xref:System.String> 클래스의 멤버인 것처럼 호출할 수 있도록 [확장 메서드](../../csharp/programming-guide/classes-and-structs/extension-methods.md)로 구현합니다.

## <a name="prerequisites"></a>사전 요구 사항

- **.NET Core 플랫폼 간 개발** 워크로드가 설치된 [Visual Studio 2019 버전 16.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019). 이 워크로드를 선택하면 .NET Core 3.1 SDK가 자동으로 설치됩니다.

  자세한 내용은 [.NET Core SDK 설치](../install/sdk.md?pivots=os-windows) 문서의 [Visual Studio를 사용하여 설치](../install/sdk.md?pivots=os-windows#install-with-visual-studio) 섹션을 참조하세요.

## <a name="create-a-visual-studio-solution"></a>Visual Studio 솔루션 만들기

먼저 클래스 라이브러리 프로젝트를 배치할 빈 솔루션을 만듭니다. Visual Studio 솔루션은 하나 이상의 프로젝트에 대한 컨테이너로 작동합니다. 동일한 솔루션에 관련 프로젝트를 추가합니다.

빈 솔루션을 만들려면 다음을 수행합니다.

1. Visual Studio를 엽니다.

2. 시작 창에서 **새 프로젝트 만들기**를 선택합니다.

3. **새 프로젝트 만들기** 페이지의 검색 상자에 **solution**을 입력합니다. **빈 솔루션** 템플릿을 선택한 후, **다음**을 선택합니다.

   ![Visual Studio의 빈 솔루션 템플릿](media/library-with-visual-studio/blank-solution.png)

4. **새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **ClassLibraryProjects**를 입력합니다. 그런 다음, **만들기**를 선택합니다.

## <a name="create-a-class-library-project"></a>클래스 라이브러리 프로젝트 만들기

1. "StringLibrary"라는 새로운 .NET Standard 클래스 라이브러리 프로젝트를 솔루션에 추가합니다.

   1. **솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가** > **새 프로젝트**를 선택합니다.

   1. **새 프로젝트 추가** 페이지의 검색 상자에 **library**를 입력합니다. 언어 목록에서 **C#** 또는 **Visual Basic**을 선택한 다음, 플랫폼 목록에서 **모든 플랫폼**을 선택합니다. **클래스 라이브러리(.NET Standard)** 템플릿을 선택하고 **다음**을 선택합니다.

   1. **새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **StringLibrary**를 입력합니다. 그런 다음, **만들기**를 선택합니다.

1. 라이브러리에 올바른 버전의 .NET Standard가 대상으로 지정되었는지 확인합니다. **솔루션 탐색기**에서 라이브러리 프로젝트를 마우스 오른쪽 단추로 클릭한 다음, **속성**을 선택합니다. **대상 프레임워크** 텍스트 상자에 프로젝트가 .NET Standard 2.0을 대상으로 한다는 것이 표시됩니다.

   ![클래스 라이브러리에 대한 프로젝트 속성](./media/library-with-visual-studio/library-project-properties.png)

1. Visual Basic을 사용하는 경우 **루트 네임스페이스** 텍스트 상자의 텍스트를 지웁니다.

   ![클래스 라이브러리에 대한 프로젝트 속성](./media/library-with-visual-studio/vb/library-project-properties.png)

   각 프로젝트에 대해 Visual Basic에서는 프로젝트 이름에 해당하는 네임스페이스를 자동으로 만듭니다. 이 자습서에서는 코드 파일의 [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) 키워드를 사용하여 최상위 네임스페이스를 정의합니다.

1. *Class1.cs* 또는 *Class1.vb* 코드 창에서 코드를 다음 코드로 바꾸고 파일을 저장합니다. 사용하려는 언어가 표시되지 않으면 페이지 맨 위에 있는 언어 선택기를 변경합니다.

   [!code-csharp[](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs)]
   [!code-vb[](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   클래스 라이브러리 `UtilityLibraries.StringLibrary`에는 `StartsWithUpper`라는 메서드가 포함되어 있습니다. 이 메서드는 현재 문자열 인스턴스가 대문자로 시작하는지 여부를 나타내는 <xref:System.Boolean> 값을 반환합니다. 유니코드 표준은 대문자와 소문자를 구분합니다. <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> 메서드는 문자가 대문자인 경우 `true`를 반환합니다.

1. 메뉴 모음에서 **빌드** > **솔루션 빌드**를 선택하여 프로젝트가 오류 없이 컴파일되는지 확인합니다.

## <a name="add-a-console-app-to-the-solution"></a>솔루션에 콘솔 앱 추가

사용자에게 문자열을 입력하라는 메시지를 표시하고 문자열이 대문자로 시작하는지 여부를 보고하는 콘솔 애플리케이션에서 이 클래스 라이브러리를 사용합니다.

1. "ShowCase"라는 새 .NET Core 콘솔 애플리케이션을 솔루션에 추가합니다.

   1. **솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가** > **새 프로젝트**를 선택합니다.

   1. **새 프로젝트 추가** 페이지의 검색 상자에 **console**을 입력합니다. 언어 목록에서 **C#** 또는 **Visual Basic**을 선택한 다음, 플랫폼 목록에서 **모든 플랫폼**을 선택합니다.

   1. **콘솔 앱(.NET Core)** 템플릿을 선택하고 **다음**을 선택합니다.

   1. **새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **ShowCase**를 입력합니다. 그런 다음, **만들기**를 선택합니다.

1. **솔루션 탐색기**에서 **ShowCase** 프로젝트를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **시작 프로젝트로 설정**을 선택합니다.

   ![Visual Studio 프로젝트 상황에 맞는 메뉴로 시작 프로젝트 설정](media/library-with-visual-studio/set-startup-project-context-menu.png)

1. 처음에는 새 콘솔 앱 프로젝트가 클래스 라이브러리에 액세스할 수 없습니다. 클래스 라이브러리의 메서드를 호출할 수 있도록 허용하려면 클래스 라이브러리 프로젝트에 대한 프로젝트 참조를 만듭니다. **솔루션 탐색기**에서 `ShowCase` 프로젝트의 **종속성** 노드를 마우스 오른쪽 단추로 클릭하고 **프로젝트 참조 추가**를 선택합니다.

   ![Visual Studio의 참조 추가 상황에 맞는 메뉴](media/library-with-visual-studio/add-reference-context-menu.png)

1. **참조 관리자** 대화 상자에서 **StringLibrary** 프로젝트를 선택하고 **확인**을 선택합니다.

   ![StringLibrary를 선택한 참조 관리자 대화 상자](media/library-with-visual-studio/manage-project-references.png)

1. *Program.cs* 또는 *Program.vb* 파일의 코드 창에서 모든 코드를 다음 코드로 바꿉니다.

   [!code-csharp[UsingClassLib#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]
   [!code-vb[UsingClassLib#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   코드는 `row` 변수를 사용하여 콘솔 창에 기록된 데이터 행 수를 유지합니다. 25보다 크거나 같으면 코드는 콘솔 창을 지우고 사용자에게 메시지를 표시합니다.

   프로그램에서 문자열을 입력하라는 메시지를 사용자에게 표시합니다. 문자열이 대문자로 시작하는지 여부를 나타냅니다. 사용자가 문자열을 입력하지 않고 Enter 키를 누르면 애플리케이션이 종료되고 콘솔 창이 닫힙니다.

1. 필요한 경우 도구 모음을 변경하여 컴파일하는 `ShowCase` 프로젝트의 **디버그** 릴리스를 컴파일합니다. **ShowCase** 단추에서 녹색 화살표를 선택하여 프로그램을 컴파일하고 실행합니다.

   ![Visual Studio 프로젝트 도구 모음 디버그 단추 표시](media/library-with-visual-studio/visual-studio-project-toolbar.png)

1. 문자열을 입력하고 **Enter** 키를 눌러 프로그램을 사용해 본 다음 **Enter** 키를 눌러 끝냅니다.

   :::image type="content" source="media/library-with-visual-studio/run-showcase.png" alt-text="ShowCase가 실행되는 콘솔 창":::

## <a name="next-steps"></a>다음 단계

이 자습서에서는 솔루션을 만들고, 라이브러리 프로젝트를 추가하고, 라이브러리를 사용하는 콘솔 앱 프로젝트를 추가했습니다. 다음 자습서에서는 솔루션에 단위 테스트 프로젝트를 추가합니다.

> [!div class="nextstepaction"]
> [Visual Studio에서 .NET Core를 사용하여 .NET Standard 라이브러리 테스트](testing-library-with-visual-studio.md)
