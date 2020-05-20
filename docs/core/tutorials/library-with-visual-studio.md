---
title: Visual Studio에서 .NET Standard 클래스 라이브러리 빌드
description: Visual Studio를 사용하여 C# 또는 Visual Basic으로 작성된 .NET Standard 클래스 라이브러리를 빌드하는 방법 알아보기
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 748a1499e0c3a4a41613a69b715dbcfbd585bfe3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714014"
---
# <a name="build-a-net-standard-library-in-visual-studio"></a>Visual Studio에서 .NET Standard 라이브러리 빌드

*클래스 라이브러리*는 애플리케이션에서 호출되는 형식 및 메서드를 정의합니다. .NET Standard 2.0을 대상으로 하는 클래스 라이브러리는 .NET Standard의 해당 버전을 지원하는 모든 .NET 구현에서 라이브러리를 호출할 수 있습니다. 클래스 라이브러리를 마칠 때 타사 구성 요소로 배포할지 또는 하나 이상의 애플리케이션과 함께 번들 구성 요소로 포함할지 결정할 수 있습니다.

> [!NOTE]
> .NET Standard 버전 및 지원되는 플랫폼 목록은 [.NET Standard](../../standard/net-standard.md)를 참조하세요.

이 항목에서는 단일 문자열 처리 메서드를 포함하는 간단한 유틸리티 라이브러리를 만들어 보겠습니다. <xref:System.String> 클래스의 멤버인 것처럼 호출할 수 있도록 [확장 메서드](../../csharp/programming-guide/classes-and-structs/extension-methods.md)로 구현하겠습니다.

## <a name="create-a-visual-studio-solution"></a>Visual Studio 솔루션 만들기

먼저 클래스 라이브러리 프로젝트를 배치할 빈 솔루션을 만듭니다. Visual Studio 솔루션은 하나 이상의 프로젝트에 대한 컨테이너로 작동합니다. 자습서 시리즈를 계속 학습하는 경우 동일한 솔루션에 관련 프로젝트를 추가합니다.

빈 솔루션을 만들려면 다음을 수행합니다.

1. Visual Studio를 엽니다.

2. 시작 창에서 **새 프로젝트 만들기**를 선택합니다.

3. **새 프로젝트 만들기** 페이지의 검색 상자에 **solution**을 입력합니다. **빈 솔루션** 템플릿을 선택한 후, **다음**을 선택합니다.

   ![Visual Studio의 빈 솔루션 템플릿](media/library-with-visual-studio/blank-solution.png)

4. **새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **ClassLibraryProjects**를 입력합니다. 그런 다음, **만들기**를 선택합니다.

> [!TIP]
> 이 단계를 건너뛰고 다음 단계에서 프로젝트를 만들 때 Visual Studio에서 솔루션을 만들도록 할 수도 있습니다. **새 프로젝트 구성** 페이지에서 솔루션 옵션을 찾습니다.

## <a name="create-a-class-library-project"></a>클래스 라이브러리 프로젝트 만들기

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[C#](#tab/csharp)

1. “StringLibrary”라는 새로운 C# .NET Standard 클래스 라이브러리 프로젝트를 솔루션에 추가합니다.

   1. **솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가** > **새 프로젝트**를 선택합니다.

   1. **새 프로젝트 추가** 페이지의 검색 상자에 **library**를 입력합니다. 언어 목록에서 **C#** 을 선택한 다음, 플랫폼 목록에서 **모든 플랫폼**을 선택합니다. **클래스 라이브러리(.NET Standard)** 템플릿을 선택하고 **다음**을 선택합니다.

   1. **새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **StringLibrary**를 입력합니다. 그런 다음, **만들기**를 선택합니다.

1. 라이브러리에 올바른 버전의 .NET Standard가 대상으로 지정되었는지 확인합니다. **솔루션 탐색기**에서 라이브러리 프로젝트를 마우스 오른쪽 단추로 클릭한 다음, **속성**을 선택합니다. **대상 프레임워크** 텍스트 상자에 프로젝트가 .NET Standard 2.0을 대상으로 한다는 것이 표시됩니다.

   ![클래스 라이브러리에 대한 프로젝트 속성](./media/library-with-visual-studio/library-project-properties.png)

1. 코드 창의 코드를 다음 코드로 바꾸고 파일을 저장합니다.

   [!CODE-csharp[ClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs)]

   클래스 라이브러리 `UtilityLibraries.StringLibrary`에는 `StartsWithUpper`라는 메서드가 포함되어 있습니다. 이 메서드는 현재 문자열 인스턴스가 대문자로 시작하는지 여부를 나타내는 <xref:System.Boolean> 값을 반환합니다. 유니코드 표준은 대문자와 소문자를 구분합니다. <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> 메서드는 문자가 대문자인 경우 `true`를 반환합니다.

1. 메뉴 모음에서 **빌드** > **솔루션 빌드**를 선택합니다.

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

1. “StringLibrary”라는 새로운 Visual Basic .NET Standard 클래스 라이브러리 프로젝트를 솔루션에 추가합니다.

   1. **솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가** > **새 프로젝트**를 선택합니다.

   1. **새 프로젝트 추가** 페이지의 검색 상자에 **library**를 입력합니다. 언어 목록에서 **Visual Basic**을 선택한 다음, 플랫폼 목록에서 **모든 플랫폼**을 선택합니다. **클래스 라이브러리(.NET Standard)** 템플릿을 선택하고 **다음**을 선택합니다.

   1. **새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **StringLibrary**를 입력합니다. 그런 다음, **만들기**를 선택합니다.

1. 라이브러리에 올바른 버전의 .NET Standard가 대상으로 지정되었는지 확인합니다. **솔루션 탐색기**에서 라이브러리 프로젝트를 마우스 오른쪽 단추로 클릭한 다음, **속성**을 선택합니다. **대상 프레임워크** 텍스트 상자에 프로젝트가 .NET Standard 2.0을 대상으로 한다는 것이 표시됩니다.

   ![클래스 라이브러리에 대한 프로젝트 속성](./media/library-with-visual-studio/vb/library-project-properties.png)

1. **속성** 대화 상자에서 **루트 네임스페이스** 텍스트 상자의 텍스트를 지웁니다. 각 프로젝트에 대해 Visual Basic에서는 프로젝트 이름에 해당하는 네임스페이스를 자동으로 만듭니다. 이 자습서에서는 코드 파일의 [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) 키워드를 사용하여 최상위 네임스페이스를 정의합니다.

1. 코드 창의 코드를 다음 코드로 바꾸고 파일을 저장합니다.

   [!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   클래스 라이브러리 `UtilityLibraries.StringLibrary`에는 `StartsWithUpper`라는 메서드가 포함되어 있습니다. 이 메서드는 현재 문자열 인스턴스가 대문자로 시작하는지 여부를 나타내는 <xref:System.Boolean> 값을 반환합니다. 유니코드 표준은 대문자와 소문자를 구분합니다. <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> 메서드는 문자가 대문자인 경우 `true`를 반환합니다.

1. 메뉴 모음에서 **빌드** > **솔루션 빌드**를 선택합니다.

---

   프로젝트가 오류 없이 컴파일되어야 합니다.

## <a name="next-steps"></a>다음 단계

라이브러리를 성공적으로 빌드했습니다. 해당 메서드를 호출하지 않았으므로 예상대로 작동하는지 알지 못합니다. 라이브러리 개발의 다음 단계는 테스트하는 것입니다.

> [!div class="nextstepaction"]
> [단위 테스트 프로젝트 만들기](testing-library-with-visual-studio.md)
