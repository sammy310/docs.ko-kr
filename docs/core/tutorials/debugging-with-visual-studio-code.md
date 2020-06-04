---
title: Visual Studio Code를 사용하여 .NET Core 콘솔 애플리케이션 디버그
description: Visual Studio Code를 사용하여 .NET Core 콘솔 앱을 디버그하는 방법을 알아봅니다.
ms.date: 05/26/2020
ms.openlocfilehash: eaeb97f54442006d2f0e29483a68dc3de89b5778
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202492"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio-code"></a>자습서: Visual Studio Code를 사용하여 .NET Core 콘솔 애플리케이션 디버그

이 자습서에서는 .NET Core 앱 작업을 하는 데 Visual Studio Code에서 사용할 수 있는 디버깅 도구를 소개합니다.

## <a name="prerequisites"></a>사전 요구 사항

- 이 자습서는 [Visual Studio Code에서 .NET Core 콘솔 애플리케이션 만들기](with-visual-studio-code.md)에서 만든 콘솔 앱에 사용할 수 있습니다.

## <a name="use-debug-build-configuration"></a>디버그 빌드 구성 사용

디버그 및 릴리스는 .NET Core의 빌드 구성 중 두 가지입니다. 디버그 빌드 구성은 디버깅에 사용하고, 릴리스 구성은 최종 릴리스 배포에 사용합니다.

디버그 구성에서 프로그램은 완전히 기호화된 디버그 정보를 사용하여 컴파일되며 최적화되지 않습니다. 최적화하면 소스 코드와 생성된 명령 간의 관계가 복잡해지므로 디버깅이 복잡해집니다. 프로그램의 릴리스 구성은 완전히 최적화되고, 기호화된 디버그 정보를 포함하지 않습니다.

 기본적으로 Visual Studio Code는 디버그 빌드 구성을 사용하므로 디버깅 전에 변경할 필요가 없습니다.

## <a name="set-a-breakpoint"></a>중단점 설정

중단점은 중단점이 설정된 줄이 실행되기 *전에* 애플리케이션 실행을 일시적으로 중단합니다.

1. *Program.cs*에서 코드 창 왼쪽 여백을 클릭하여 이름, 날짜, 시간을 표시하는 줄에 중단점을 설정합니다. 왼쪽 여백은 줄 번호의 왼쪽에 있습니다. 중단점을 설정하는 또 다른 방법은 코드 줄에 커서를 배치한 다음 <kbd>F9</kbd> 키를 누르는 것입니다.

   다음 이미지에서 볼 수 있듯이 Visual Studio Code에서는 왼쪽 여백에 빨간 점을 표시하여 중단점이 설정된 줄을 표시합니다.

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-set.png" alt-text="중단점 설정":::

## <a name="set-up-for-terminal-input"></a>터미널 입력에 대해 설정

중단점은 `Console.ReadLine` 메서드 호출 뒤에 있습니다. **디버그 콘솔**은 실행 중인 프로그램에 대한 터미널 입력을 허용하지 않습니다. 디버깅 중에 터미널 입력을 처리하기 위해 통합 터미널(Visual Studio Code 창 중 하나) 또는 외부 터미널을 사용할 수 있습니다. 이 자습서에서는 통합 터미널을 사용합니다.

1. *.vscode/launch.json*을 엽니다.

1. `console` 설정을 `integratedTerminal`로 변경합니다.

   원본:

   ```
   "console": "internalConsole",
   ```

   대상:

   ```
   "console": "integratedTerminal",
   ```

1. 변경 내용을 저장합니다.

## <a name="start-debugging"></a>디버깅 시작

1. 왼쪽 메뉴에서 디버깅 아이콘을 선택하여 디버그 보기를 엽니다.

   :::image type="content" source="media/debugging-with-visual-studio-code/select-debug-pane.png" alt-text="Visual Studio Code에서 디버그 탭 열기":::

1. **.NET Core 시작(콘솔)** 옆에 있는 창 맨 위의 녹색 화살표를 선택하여 디버깅을 시작합니다.  디버깅을 시작하는 또 다른 방법은 <kbd>F5</kbd> 키를 누르는 것입니다.

   :::image type="content" source="media/debugging-with-visual-studio-code/start-debugging.png" alt-text="디버깅 시작":::

1. **터미널** 탭을 선택하여 응답을 기다리기 전에 프로그램이 표시하는 "What is your name?" 프롬프트를 확인합니다.

   :::image type="content" source="media/debugging-with-visual-studio-code/select-terminal.png" alt-text="터미널 탭 선택":::

1. 이름을 묻는 프롬프트에 대한 응답으로 **터미널** 창에 문자열을 입력하고 <kbd>Enter</kbd> 키를 누릅니다.

   중단점에 도달할 때와 `Console.WriteLine` 메서드가 실행되기 전에 프로그램 실행이 중지됩니다. **변수** 창의 **지역** 섹션에는 현재 실행 중인 메서드에 정의된 변수 값이 표시됩니다.

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-hit.png" alt-text="중단점 적중, 지역 표시":::

## <a name="change-variable-values"></a>변수 값 변경

**디버그 콘솔** 창을 통해 디버그하는 애플리케이션과 상호 작용할 수 있습니다. 변수 값을 변경하여 프로그램에 미치는 영향을 확인할 수 있습니다.

1. **디버그 콘솔** 탭을 선택합니다.

1. **디버그 콘솔** 창의 맨 아래에 있는 프롬프트에 `name = "Gracie"`를 입력하고 <kbd>Enter</kbd> 키를 누릅니다.

   :::image type="content" source="media/debugging-with-visual-studio-code/change-variable-values.png" alt-text="변수 값 변경":::

1. **디버그 콘솔** 창의 맨 아래에 `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()`을 입력하고 <kbd>Enter</kbd> 키를 누릅니다.

   **변수** 창에 `name` 및 `date` 변수의 새 값이 표시됩니다.

1. 도구 모음에서 **계속** 단추를 선택하여 프로그램 실행을 계속합니다. <kbd>F5</kbd> 키를 눌러도 계속 진행할 수 있습니다.

   :::image type="content" source="media/debugging-with-visual-studio-code/continue-debugging.png" alt-text="디버깅 계속":::

1. **터미널** 탭을 다시 선택합니다.

   콘솔 창에 표시되는 값은 **디버그 콘솔**에서 변경한 값과 일치합니다.

   :::image type="content" source="media/debugging-with-visual-studio-code/changed-variable-values.png" alt-text="입력한 값을 보여 주는 터미널":::

1. 아무 키나 눌러 애플리케이션을 종료하고 디버깅을 중지합니다.

## <a name="set-a-conditional-breakpoint"></a>조건부 중단점 설정

프로그램은 사용자가 입력하는 문자열을 표시합니다. 사용자가 아무 값도 입력하지 않으면 어떻게 되나요? *조건부 중단점*이라는 유용한 디버깅 기능을 사용하여 이를 테스트할 수 있습니다.

1. 중단점을 나타내는 빨간색 점을 마우스 오른쪽 단추로 클릭합니다(macOS에서는 <kbd>Ctrl</kbd>+클릭). 상황에 맞는 메뉴에서 **중단점 편집**을 선택하면 조건식을 입력할 수 있는 대화 상자가 열립니다.

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-context-menu.png" alt-text="중단점 상황에 맞는 메뉴":::

1. 드롭다운에서 `Expression`을 선택하고 다음 조건식을 입력한 후 <kbd>Enter</kbd> 키를 누릅니다.

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/conditional-expression.png" alt-text="조건식 입력":::

   디버거는 중단점이 적중될 때마다 `String.IsNullOrEmpty(name)` 메서드를 호출하고, 메서드 호출이 `true`를 반환하는 경우에만 이 줄에서 중단합니다.

   조건식 대신 문이 실행되기 전에 프로그램 실행을 중단하는 적중 횟수 또는 스레드 식별자, 프로세스 이름 또는 스레드 이름과 같은 특성을 기준으로 프로그램 실행을 중단하는 필터 조건을 지정할 수 있습니다.

1. <kbd>F5</kbd> 키를 눌러 디버깅으로 프로그램을 시작합니다.

1. **터미널** 탭에서 이름을 입력하라는 메시지가 나타나면 <kbd>Enter</kbd> 키를 누릅니다.

   `name`이 `null` 또는 <xref:System.String.Empty?displayProperty=nameWithType>이라는 지정한 조건이 충족되었으므로 중단점에 도달한 후 `Console.WriteLine` 메서드가 실행되기 전에 프로그램 실행이 중지됩니다.

   **변수** 창에 `name` 변수 값이 `""` 또는 <xref:System.String.Empty?displayProperty=nameWithType>임이 표시됩니다.

1. **디버그 콘솔** 프롬프트에 다음 문을 입력하고 <kbd>Enter</kbd> 키를 눌러 값이 빈 문자열인지 확인합니다. 결과는 `true`입니다.

   ```csharp
   name == String.Empty
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/expression-in-debug-console.png" alt-text="문이 실행된 후 true 값을 반환하는 디버그 콘솔":::

1. 도구 모음에서 **계속** 단추를 선택하여 프로그램 실행을 계속합니다.

1. **터미널** 탭을 선택하고 아무 키나 눌러 프로그램을 종료하고 디버깅을 중지합니다.

1. 코드 창 왼쪽 여백에 있는 점을 클릭하여 중단점을 지웁니다. 중단점을 지우는 또 다른 방법은 코드 줄이 선택되어 있는 동안 <kbd>F9</kbd> 키를 누르는 것입니다.

1. 중단점 조건이 손실된다는 경고가 표시되면 **중단점 제거**를 선택합니다.

## <a name="step-through-a-program"></a>단계별 프로그램 실행

Visual Studio Code에서 프로그램을 한 줄씩 단계별로 실행하고 해당 실행을 모니터링할 수도 있습니다. 일반적으로 중단점을 설정하고 프로그램 코드 일부의 프로그램 흐름을 따라가면서 확인할 수 있습니다. 이 프로그램은 작으므로 전체 프로그램을 단계별로 실행할 수 있습니다.

1. `Main` 메서드의 여는 중괄호에 중단점을 설정합니다.

1. <kbd>F5</kbd> 키를 눌러 디버깅을 시작합니다.

   Visual Studio Code가 중단점 줄을 강조 표시합니다.

   이 시점에서 **변수** 창에는 `args` 배열이 비어 있다고 표시되고, `name` 및 `date`에는 기본값이 있습니다.

1. **한 단계씩 코드 실행**을 선택하거나 <kbd>F11</kbd> 키를 누릅니다.

   :::image type="content" source="media/debugging-with-visual-studio-code/step-into.png" alt-text="한 단계씩 코드 실행 단추":::

   Visual Studio Code가 다음 줄을 강조 표시합니다.

1. **한 단계씩 코드 실행**을 선택하거나 <kbd>F11</kbd> 키를 누릅니다.

   Visual Studio Code가 이름 프롬프트에 대해 `Console.WriteLine`을 실행하고 다음에 실행할 줄을 강조 표시합니다. 다음 줄은 `name`의 `Console.ReadLine`입니다. **변수** 창은 변경되지 않으며, **터미널** 탭에는 "What is your name?" 프롬프트가 표시됩니다.

1. **한 단계씩 코드 실행**을 선택하거나 <kbd>F11</kbd> 키를 누릅니다.

   Visual Studio가 `name` 변수 할당을 강조 표시합니다. **변수** 창에 `name`이 여전히 `null`이라고 표시됩니다.

1. 터미널 탭에 문자열을 입력하고 <kbd>Enter</kbd> 키를 눌러 프롬프트에 응답합니다.

   문자열을 입력하는 동안 **터미널** 탭에 문자열이 표시되지 않을 수 있지만 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 메서드는 입력을 캡처합니다.

1. **한 단계씩 코드 실행**을 선택하거나 <kbd>F11</kbd> 키를 누릅니다.

   Visual Studio Code가 `date` 변수 할당을 강조 표시합니다. **변수** 창에는 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 메서드 호출에 의해 반환된 값이 표시됩니다. **터미널** 탭에는 프롬프트에 입력한 문자열이 표시됩니다.

1. **한 단계씩 코드 실행**을 선택하거나 <kbd>F11</kbd> 키를 누릅니다.

   **변수** 창에는 <xref:System.DateTime.Now?displayProperty=nameWithType> 속성에 따라 할당된 이후의 `date` 변수 값이 표시됩니다.

1. **한 단계씩 코드 실행**을 선택하거나 <kbd>F11</kbd> 키를 누릅니다.

   Visual Studio Code가 <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> 메서드를 호출합니다. 콘솔 창에는 서식이 지정된 문자열이 표시됩니다.

1. **프로시저 나가기**를 선택하거나 <kbd>Shift</kbd>+<kbd>F11</kbd> 키를 누릅니다.

   :::image type="content" source="media/debugging-with-visual-studio-code/step-out.png" alt-text="프로시저 나가기 단추":::

1. **터미널** 탭을 선택합니다.

   터미널에 "종료하려면 아무 키나 누르세요..."가 표시됩니다.

1. 아무 키나 눌러 프로그램을 종료합니다.

## <a name="select-release-build-configuration"></a>릴리스 빌드 구성 선택

애플리케이션의 디버그 버전을 테스트한 후에는 릴리스 버전을 컴파일하고 테스트해야 합니다. 릴리스 버전에는 애플리케이션의 동작에 영향을 줄 수 있는 컴파일러 최적화가 통합됩니다. 예를 들어 성능 향상을 위해 설계된 컴파일러 최적화는 다중 스레드 애플리케이션에서 경합 상태를 만들 수 있습니다.

콘솔 애플리케이션의 릴리스 버전을 빌드하고 테스트하려면 **터미널**을 열고 다음 명령을 실행합니다.

```dotnetcli
dotnet run --configuration Release
```

## <a name="additional-resources"></a>추가 자료

* [Visual Studio Code의 디버깅](https://code.visualstudio.com/docs/editor/debugging)

## <a name="next-steps"></a>다음 단계

이 자습서에서는 Visual Studio Code 디버깅 도구를 사용했습니다. 앱의 배포 가능 버전을 게시하는 방법을 알아보려면 [앱 게시](cli-create-console-app.md#publish-your-app)를 참조하세요.

<!--In the next tutorial, you publish a deployable version of the app.

> [!div class="nextstepaction"]
> [Publish a .NET Core console application with Visual Studio Code](publishing-with-visual-studio-code.md)
-->
