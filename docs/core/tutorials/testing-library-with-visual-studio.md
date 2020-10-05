---
title: Visual Studio를 사용하여 .NET Core로 .NET Standard 클래스 라이브러리 테스트
description: .NET Core 클래스 라이브러리에 대한 단위 테스트 프로젝트를 만듭니다. .NET Core 클래스 라이브러리가 단위 테스트에서 올바르게 작동하는지 확인합니다.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 04d0120622697d1e0c84fc169dfc50951cb8aa3c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177295"
---
# <a name="tutorial-test-a-net-standard-class-library-with-net-core-using-visual-studio"></a>자습서: Visual Studio를 사용하여 .NET Core로 .NET Standard 클래스 라이브러리 테스트

이 자습서에서는 솔루션에 테스트 프로젝트를 추가하여 단위 테스트를 자동화하는 방법을 보여 줍니다.

## <a name="prerequisites"></a>사전 요구 사항

- 이 자습서는 [Visual Studio를 사용하여 .NET Standard 라이브러리 만들기](library-with-visual-studio.md)에서 만든 솔루션에 사용할 수 있습니다.

## <a name="create-a-unit-test-project"></a>단위 테스트 프로젝트 만들기

단위 테스트는 개발 및 게시 동안 자동화된 소프트웨어 테스트를 제공합니다. [MSTest](https://github.com/Microsoft/testfx-docs)는 선택할 수 있는 세 가지 테스트 프레임워크 중 하나입니다. 다른 프레임워크는 [xUnit](https://xunit.net/)과 [nUnit](https://nunit.org/)입니다.

1. Visual Studio를 시작합니다.

1. [Visual Studio를 사용하여 .NET Standard 라이브러리 만들기](library-with-visual-studio.md)에서 만든 `ClassLibraryProjects` 솔루션을 엽니다.

1. "StringLibraryTest"라는 새 단위 테스트 프로젝트를 솔루션에 추가합니다.

   1. **솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가** > **새 프로젝트**를 선택합니다.

   1. **새 프로젝트 추가** 페이지의 검색 상자에 **mstest**를 입력합니다. 언어 목록에서 **C#** 또는 **Visual Basic**을 선택한 다음, 플랫폼 목록에서 **모든 플랫폼**을 선택합니다.

   1. **MSTest 테스트 프로젝트(.NET Core)** 템플릿을 선택한 후 **다음**을 선택합니다.

   1. **새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **StringLibraryTest**를 입력합니다. 그런 다음, **만들기**를 선택합니다.

1. Visual Studio는 프로젝트를 만들고 코드 창에서 다음 코드가 포함된 클래스 파일을 엽니다. 사용하려는 언어가 표시되지 않으면 페이지 맨 위에 있는 언어 선택기를 변경합니다.

   ```csharp
   using Microsoft.VisualStudio.TestTools.UnitTesting;

   namespace StringLibraryTest
   {
       [TestClass]
       public class UnitTest1
       {
           [TestMethod]
           public void TestMethod1()
           {
           }
       }
   }
   ```

   ```vb
   Imports Microsoft.VisualStudio.TestTools.UnitTesting

   Namespace StringLibraryTest
       <TestClass>
       Public Class UnitTest1
           <TestMethod>
           Sub TestSub()

           End Sub
       End Class
   End Namespace
   ```

   단위 테스트 템플릿을 통해 만들어진 소스 코드는 다음을 수행합니다.

   - 단위 테스트에 사용되는 형식을 포함하는 <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> 네임스페이스를 가져옵니다.
   - <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 특성을 `UnitTest1` 클래스에 적용합니다.
   - <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 특성을 적용하여 `TestMethod1`(C#) 또는 `TestSub`(Visual Basic)를 정의합니다.

   [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute)로 태그가 지정된 테스트 클래스에서 [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute)로 태그가 지정된 각 메서드는 단위 테스트가 실행될 때 자동으로 실행됩니다.

## <a name="add-a-project-reference"></a>프로젝트 참조 추가

테스트 라이브러리가 `StringLibrary` 클래스에 대해 작동하도록 하기 위해 **StringLibraryTest** 프로젝트의 참조를 `StringLibrary` 프로젝트에 추가합니다.

1. **솔루션 탐색기**에서 **StringLibraryTest** 프로젝트의 **종속성** 노드를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **프로젝트 참조 추가**를 선택합니다.

1. **참조 관리자** 대화 상자에서 **프로젝트** 노드를 확장하고 **StringLibrary** 옆에 있는 확인란을 선택합니다. `StringLibrary` 어셈블리에 대한 참조를 추가하면 컴파일러가 **StringLibraryTest** 프로젝트를 컴파일하면서 **StringLibrary** 메서드를 찾을 수 있습니다.

1. **확인**을 선택합니다.

## <a name="add-and-run-unit-test-methods"></a>단위 테스트 메서드 추가 및 실행

Visual Studio는 단위 테스트를 실행할 때 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 특성이 표시된 클래스에서 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 특성이 표시된 각 메서드를 실행합니다. 테스트 메서드는 첫 번째 오류가 발생하거나 메서드에 포함된 모든 테스트가 성공적으로 수행되면 종료됩니다.

가장 일반적인 테스트는 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> 클래스의 멤버를 호출합니다. 많은 어설션 메서드에는 2개 이상의 매개 변수가 포함되며, 그 중 하나는 예상된 테스트 결과이고, 다른 하나는 실제 테스트 결과입니다. `Assert` 클래스에서 가장 자주 호출되는 일부 메서드는 다음 표에 나와 있습니다.

| Assert 메서드     | 기능 |
| ------------------ | -------- |
| `Assert.AreEqual`  | 두 개의 값이나 개체가 같은지를 확인합니다. 값이나 개체가 같지 않으면 어설션이 실패합니다. |
| `Assert.AreSame`   | 두 개의 개체 변수가 같은 개체를 참조하는지를 확인합니다. 변수가 서로 다른 개체를 참조하면 어설션이 실패합니다. |
| `Assert.IsFalse`   | 조건이 `false`인지 확인합니다. 조건이 `true`이면 어설션이 실패합니다. |
| `Assert.IsNotNull` | 개체가 `null`이 아닌지를 확인합니다. 개체가 `null`이면 어설션이 실패합니다. |

테스트 메서드에서 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> 메서드를 사용하여 throw될 것으로 예상되는 예외의 유형을 나타낼 수도 있습니다. 지정된 예외가 throw되지 않으면 테스트가 실패한 것입니다.

`StringLibrary.StartsWithUpper` 메서드를 테스트할 때 대문자로 시작하는 많은 문자열을 제공하려고 합니다. 이러한 경우에 메서드가 `true`를 반환할 것으로 기대하므로 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> 메서드를 호출할 수 있습니다. 마찬가지로, 대문자 이외의 문자로 시작하는 많은 문자열을 제공하려고 합니다. 이러한 경우에 메서드가 `false`를 반환할 것으로 기대하므로 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> 메서드를 호출할 수 있습니다.

또한 라이브러리 메서드가 문자열을 처리하므로 [빈 문자열(`String.Empty`)](xref:System.String.Empty)(문자가 없고 해당 <xref:System.String.Length>가 0인 유효한 문자열) 및 `null` 문자열(초기화되지 않은 문자열)을 성공적으로 처리하는지 확인하려고 합니다. `StartsWithUpper`를 직접 정적 메서드로 호출하고 단일 <xref:System.String> 인수를 전달할 수 있습니다. 또는 `null`에 할당된 `string` 변수에 대한 확장 메서드로 `StartsWithUpper`를 호출할 수 있습니다.

각 메서드가 문자열 배열의 각 요소에 대해 해당 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> 메서드를 호출하는 메서드 세 개를 정의해 보겠습니다. 테스트에 실패할 경우 표시될 오류 메시지를 지정할 수 있도록 하는 메서드 오버로드를 호출합니다. 메시지는 실패를 일으킨 문자열을 식별합니다.

테스트 메서드를 만들려면

1. *UnitTest1.cs* 또는 *UnitTest1.vb* 코드 창에서 코드를 다음 코드로 바꿉니다.

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibraryTest/UnitTest1.vb":::

   `TestStartsWithUpper` 메서드의 대문자 테스트에는 그리스어 대문자 알파(U+0391) 및 키릴 자모 대문자 EM(U+041C)이 포함됩니다. `TestDoesNotStartWithUpper` 메서드의 소문자 테스트에는 그리스어 소문자 알파(U+03B1) 및 키릴 자모 소문자 Ghe(U+0433)가 포함됩니다.

1. 메뉴 모음에서 **파일** > **다른 이름으로 UnitTest1.cs 저장** 또는 **파일** > **다른 이름으로 UnitTest1.vb 저장**을 선택합니다. **다른 이름으로 파일 저장** 대화 상자에서 **저장** 단추 옆에 있는 화살표를 선택한 다음 **인코딩하여 저장**을 선택합니다.

   > [!div class="mx-imgBorder"]
   > ![Visual Studio 다른 이름으로 파일 저장 대화 상자](./media/testing-library-with-visual-studio/save-file-as-dialog.png)

1. **다른 이름으로 저장 확인** 대화 상자에서 **예** 단추를 선택하여 파일을 저장합니다.

1. **고급 저장 옵션** 대화 상자의 **인코딩** 드롭다운 목록에서 **유니코드(시그니처가 있는 UTF-8) - 코드 페이지 65001**을 선택한 다음 **확인**을 선택합니다.

   > [!div class="mx-imgBorder"]
   > ![Visual Studio 고급 저장 옵션 대화 상자](./media/testing-library-with-visual-studio/advanced-save-options.png)

   소스 코드를 UTF8로 인코드된 파일에 저장하지 못하면 Visual Studio에서 해당 파일이 ASCII 파일로 저장될 수 있습니다. 이 경우 런타임은 ASCII 범위 밖의 UTF8 문자를 정확히 디코드하지 않으며 테스트 결과가 올바르지 않게 됩니다.

1. 메뉴 모음에서 **테스트** > **모든 테스트 실행**을 선택합니다. **테스트 탐색기** 창이 열리지 않으면 **테스트** > **테스트 탐색기**를 선택하여 엽니다. 세 가지 테스트가 **통과한 테스트** 섹션에 표시되고 **요약** 섹션에 테스트 실행 결과가 보고됩니다.

   > [!div class="mx-imgBorder"]
   > ![테스트를 통과한 테스트 탐색기 창](./media/testing-library-with-visual-studio/test-explorer-window.png)

## <a name="handle-test-failures"></a>테스트 실패 처리

TDD(테스트 기반 개발)를 수행하는 경우 먼저 테스트를 작성하고 첫 실행에서 실패합니다. 그런 다음, 테스트를 성공하게 만드는 코드를 앱에 추가합니다. 이 자습서에서는 유효성을 검사하는 앱 코드를 작성한 후에 테스트를 만들었으므로 테스트에 실패하지 않았습니다. 테스트가 실패할 것으로 예상되는 시점에 테스트가 실패하는지 확인하려면 테스트 입력에 잘못된 값을 추가하세요.

1. `TestDoesNotStartWithUpper` 메서드의 `words` 배열이 "Error" 문자열을 포함하도록 수정합니다. 테스트를 실행하도록 솔루션을 빌드하면 Visual Studio에서 열려 있는 파일을 자동으로 저장하기 때문에 파일을 저장할 필요가 없습니다.

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. 메뉴 모음에서 **테스트** > **모든 테스트 실행**을 선택하여 테스트를 실행합니다. **테스트 탐색기** 창에 두 가지 테스트는 성공하고 한 가지 테스트는 실패한 것으로 나타납니다.

   > [!div class="mx-imgBorder"]
   > ![테스트를 실패한 테스트 탐색기 창](./media/testing-library-with-visual-studio/failed-test-window.png)

1. 실패한 테스트인 `TestDoesNotStartWith`를 선택합니다.

   **테스트 탐색기** 창에 어설션이 생성하는 메시지 "Assert.IsFalse가 실패했습니다. 'Error'에 필요한 값: false, 실제: True"가 표시됩니다. 이 오류 때문에 "Error" 다음에 나오는 배열의 문자열은 테스트되지 않았습니다.

   > [!div class="mx-imgBorder"]
   > ![Is False 어설션 실패를 표시하는 테스트 탐색기 창](./media/testing-library-with-visual-studio/failed-test-detail.png)

1. 1단계에서 추가한 "Error" 문자열을 제거합니다. 테스트를 다시 실행하면 테스트를 통과합니다.

## <a name="test-the-release-version-of-the-library"></a>라이브러리의 릴리스 버전 테스트

라이브러리의 디버그 빌드를 실행할 때 테스트에 모두 통과했으므로 라이브러리의 릴리스 빌드에 대해 추가로 테스트를 실행합니다. 컴파일러 최적화를 비롯한 여러 가지 요인 때문에 디버그 및 릴리스 빌드 간에 서로 다른 동작이 발생할 수도 있습니다.

릴리스 빌드를 테스트하려면

1. Visual Studio 도구 모음에서 빌드 구성을 **디버그**에서 **릴리스**로 변경합니다.

   > [!div class="mx-imgBorder"]
   > ![릴리스 빌드가 강조 표시된 Visual Studio 도구 모음](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)

1. **솔루션 탐색기**에서 **StringLibrary** 프로젝트를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **빌드**를 선택하여 라이브러리를 다시 컴파일합니다.

   > [!div class="mx-imgBorder"]
   > ![빌드 명령이 있는 StringLibrary 상황에 맞는 메뉴](./media/testing-library-with-visual-studio/build-library-context-menu.png)

1. 메뉴 모음에서 **테스트 실행** > **모든 테스트**를 선택하여 단위 테스트를 실행합니다. 테스트를 통과합니다.

## <a name="debug-tests"></a>테스트 디버그

Visual Studio를 IDE로 사용하는 경우 [자습서: Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 디버그](debugging-with-visual-studio.md)에 표시된 것과 동일한 프로세스로 단위 테스트 프로젝트를 사용하는 코드를 디버그할 수 있습니다. *ShowCase* 앱 프로젝트를 시작하는 대신 **StringLibraryTests** 프로젝트를 마우스 오른쪽 단추로 클릭한 다음 상황에 맞는 메뉴에서 **테스트 디버그**를 선택합니다.

Visual Studio에서 디버거를 연결한 상태로 테스트 프로젝트를 시작합니다. 테스트 프로젝트에 추가한 중단점 또는 기본 라이브러리 코드에서 실행이 중지됩니다.

## <a name="additional-resources"></a>추가 자료

* [단위 테스트 기본 사항 - Visual Studio](/visualstudio/test/unit-test-basics)
* [.NET Core 및 .NET Standard의 유닛 테스트](../testing/index.md)

## <a name="next-steps"></a>다음 단계

이 자습서에서는 클래스 라이브러리의 단위 테스트를 실행했습니다. [NuGet](https://nuget.org)에 패키지로 라이브러리를 게시하면 다른 사용자가 사용할 수 있습니다. 방법을 알아보려면 NuGet 자습서를 따릅니다.

> [!div class="nextstepaction"]
> [Visual Studio를 사용하여 NuGet 패키지 만들기 및 게시](/nuget/quickstart/create-and-publish-a-package-using-visual-studio?tabs=netcore-cli)

라이브러리를 NuGet 패키지로 게시하면 다른 사용자가 설치하고 사용할 수 있습니다. 방법을 알아보려면 NuGet 자습서를 따릅니다.

> [!div class="nextstepaction"]
> [Visual Studio에서 패키지 설치 및 사용](/nuget/quickstart/install-and-use-a-package-in-visual-studio)

라이브러리는 패키지로 배포하지 않아도 됩니다. 라이브러리를 사용하는 콘솔 앱과 함께 제공할 수 있습니다. 콘솔 앱을 게시하는 방법을 알아보려면 이 시리즈의 이전 자습서를 참조하세요.

> [!div class="nextstepaction"]
> [Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 게시](publishing-with-visual-studio.md)
