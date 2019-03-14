---
title: 시작 F# Visual Studio Code에서
description: 사용 하는 방법을 알아봅니다 F# Visual Studio Code 및 Ionide 플러그 인 도구 모음을 사용 하 여 합니다.
ms.date: 12/23/2018
ms.openlocfilehash: 79863d57abbc71d59ce01fe30abf1db0a569f1e1
ms.sourcegitcommit: 5d9f4b805787f890ca6e0dc7ea30a43018bc9cbb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2019
ms.locfileid: "57788494"
---
# <a name="get-started-with-f-in-visual-studio-code"></a>시작 F# Visual Studio Code에서

작성할 수 있습니다 F# 에 [Visual Studio Code](https://code.visualstudio.com) 사용 하 여는 [Ionide 플러그 인](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) IntelliSense 및 기본 코드를 사용 하 여 유용한 플랫폼 간, 간단한 개발 환경 (IDE (통합) 환경을 리팩터링 합니다. 방문 [Ionide.io](http://ionide.io) 플러그 인에 자세히 알아보려면 합니다.

를 시작 했는지 확인 [ F# 하 고 올바르게 설치 Ionide 플러그 인](install-fsharp.md#install-f-with-visual-studio-code)합니다.

> [!NOTE]
> Ionide.NET Framework를 생성 합니다 F# 프로젝트, 플랫폼 간 호환성 문제가 발생할 수 있으므로 dotnet core 없습니다. 실행 하는 경우 **Linux** 하거나 **OSX**, (명령줄 도구)를 사용 하는 간단 하 게 시작 [https://docs.microsoft.com/en-us/dotnet/fsharp/get-started/get-started-command-line].

## <a name="creating-your-first-project-with-ionide"></a>Ionide를 사용 하 여 첫 번째 프로젝트 만들기

새 F# 프로젝트에서 새 폴더 (이름을 지정할 수 있습니다 원하는)에서 Visual Studio Code를 엽니다.

다음으로, 명령 팔레트를 엽니다 (**보기 > 명령 팔레트**) 다음을 입력 합니다.

```
> F# new project
```

이 연결 된 값을 [위조](https://github.com/fsharp-editing/Forge) 프로젝트입니다.

> [!NOTE]
> 템플릿 옵션을 보이지 않으면 명령 팔레트에서 다음 명령을 실행 하 여 서식 파일을 새로 고쳐 보세요. `>F#: Refresh Project Templates`합니다.

선택 "F#: 새 프로젝트 "를 눌러 **Enter**합니다. 이 프로젝트 템플릿을 선택 하는 다음 단계를 안내 합니다.

선택 된 `classlib` 템플릿과 적중 **Enter**합니다.

그런 다음에 프로젝트를 만들려면 디렉터리를 선택 합니다. 이 비워 두면 경우 현재 디렉터리를 사용 합니다.

마지막으로, 마지막 단계에서 프로젝트를 이름을 지정 합니다. F#사용 하 여 [파스칼식 대 / 소문자](http://c2.com/cgi/wiki?PascalCase) 프로젝트 이름에 대 한 합니다. 이 문서에서는 `ClassLibraryDemo` 이름으로 합니다. 프로젝트에 대해 원하는 이름을 입력 한 후 적중 **Enter**합니다.

이전 단계를 수행한 경우 Visual Studio 코드에서 작업 영역의 왼쪽에 있는 다음 표시할 얻게 됩니다.

1. F# 프로젝트 자체를 아래 합니다 `ClassLibraryDemo` 폴더입니다.
2. 통해 패키지를 추가 하기 위한 올바른 디렉터리 구조 [ `Paket` ](https://fsprojects.github.io/Paket/)합니다.
3. 플랫폼 간 빌드 스크립트 [ `FAKE` ](https://fsharp.github.io/FAKE/)합니다.
4. `paket.exe` 패키지 있습니다 가져오고 수에 대 한 종속성을 해결 하는 실행 파일입니다.
5. `.gitignore` Git 기반 소스 제어에이 프로젝트를 추가 하려는 경우 파일입니다.

## <a name="writing-some-code"></a>일부 코드 작성

엽니다는 *ClassLibraryDemo* 폴더입니다.  다음 파일이 표시 됩니다.

1. `ClassLibraryDemo.fs`에 F# 에 정의 된 클래스를 사용 하 여 구현 파일입니다.
2. `ClassLibraryDemo.fsproj`에 F# 프로젝트 파일을이 프로젝트를 빌드하는 데 사용 합니다.
3. `Script.fsx`에 F# 소스 파일을 로드 하는 스크립트 파일입니다.
4. `paket.references`를 프로젝트 종속성을 지정 하는 Paket 파일입니다.

열기 `Script.fsx`의 끝에 다음 코드를 추가 합니다.

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

이 함수는 형태의 단어 변환 [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin)합니다. 다음 단계를 사용 하 여 평가 하는 F# 대화형 (FSI).

(11 줄 이어야 함)은 전체 함수를 강조 표시 합니다. 이 강조 표시 되 면 저장 합니다 **Alt** 키 및 적중 **Enter**합니다. 아래 팝업 창을 보면 하 고 다음과 같이 표시 됩니다.

![예 F# 대화형 Ionide를 사용 하 여 출력](media/getting-started-vscode/vscode-fsi.png)

이 세 가지 작업을 수행 했습니다.

1. FSI 프로세스를 시작 하는 것입니다.
2. 강조 표시 된 코드 FSI 프로세스를 통해 보낸 합니다.
3. FSI 프로세스를 통해 전송 된 코드를 평가 합니다.

통해 전달 되는 내용 때문에 [함수](../language-reference/functions/index.md), 이제 FSI 사용 하 여 해당 함수를 호출할 수 있습니다. 대화형 창에서 다음을 입력 합니다.

```fsharp
toPigLatin "banana";;
```

다음과 같은 결과가 나타납니다.

```fsharp
val it : string = "ananabay"
```

이제 첫 번째 문자로 모음을 사용 하 여 시도해 보겠습니다. 다음을 입력하세요.

```fsharp
toPigLatin "apple";;
```

다음과 같은 결과가 나타납니다.

```fsharp
val it : string = "appleyay"
```

예상 대로 작동 하는 함수 표시 됩니다. 축 하 여 방금 작성 한 첫 번째 F# Visual Studio Code에서 함수 및 FSI를 사용 하 여 평가!

> [!NOTE]
> FSI의 선이 끝납니다 했을 수에 따라 `;;`합니다. 즉, FSI을 사용 하면 여러 줄을 입력할 수 있습니다. `;;` 끝 FSI 코드가 완료 되었을 때를 알 수 있습니다.

## <a name="explaining-the-code"></a>코드를 설명합니다.

코드를 실제로 수행 하는 방법에 대 한 잘 모르는 경우 다음을 단계별은입니다.

알 수 있듯이 `toPigLatin` 함수는 입력으로 단어 및 단어의 Pig Latin 표현으로 변환 하는 것입니다. 이 대 한 규칙 아래와 같습니다.

단어의 첫 번째 문자 모음에서 시작 하는 경우 "yay" 라는 단어의 끝에 추가 합니다. 모음을 사용 하 여 시작 되지 않으면 첫 번째 문자는 단어의 끝으로 이동 및 "살펴보고"를 추가 합니다.

FSI에서 다음을 알 수 있습니다.

```fsharp
val toPigLatin : word:string -> string
```

이 나타내는 `toPigLatin` 에서 사용 하는 함수는를 `string` 입력으로 (호출 `word`)를 반환 하는 값 및 `string`합니다. 이 [함수 형식 시그니처](https://fsharpforfunandprofit.com/posts/function-signatures/), 기본 부분 F# 이해 하기 위한 열쇠입니다 F# 코드. 또한 보면이 Visual Studio Code에서 함수를 가리키면 됩니다.

함수 본문에는 두 가지 부분 알려줍니다.

1. 내부 함수 호출 `isVowel`를 결정 하는 경우 지정 된 문자 (`c`)를 통해 제공 된 패턴 중 하 나와 일치 하는 경우를 확인 하 여이 모음인 [패턴 일치](../language-reference/pattern-matching.md):

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. [ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) 첫 번째 문자에 모음이 오는 형태로 되며 반환 값에서 문자를 입력된 하는 구문 인지에 따라 첫 번째 문자를 확인 하는 식 모음 되었거나:

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

흐름을 `toPigLatin` 따라서:

입력된 된 단어의 첫 번째 문자에 모음이 오는 형태로 인지 확인 합니다. 이 경우 "yay" 라는 단어의 끝에 연결 합니다. 이 고, 그렇지 첫 번째 문자는 단어의 끝으로 이동 하 고를 "살펴보고"를 추가 합니다.

이 주의 해야 할 사항이 하나는:는 여러 다른 언어와 달리 가지 함수에서 반환할 명시적 명령 없습니다. 왜냐하면 F# 이 식을 기반 고 함수 본문의 마지막 식 반환 값입니다. 때문에 `if..then..else` 는 식의 본문 자체를 `then` 블록 또는 본문에는 `else` 블록 입력된 값에 따라 반환 됩니다.

## <a name="moving-your-script-code-into-the-implementation-file"></a>스크립트 코드 구현 파일로 이동

이 문서의 이전 섹션의에서 일반적인 첫 번째 단계를 보여 줍니다. F# 코드: 초기 함수를 작성 및 FSI를 사용 하 여 대화형으로 실행 합니다. REPL 기반 개발 이라고 위치 [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) "읽기-평가-인쇄 루프"는 의미입니다. 작업 항목 수 있을 때까지 기능을 사용 하 여 실험에 유용한 방법입니다.

REPL 기반 개발의 다음 단계를 작업 코드를 이동 하는 것을 F# 구현 파일입니다. 다음으로 컴파일할 수는 F# 를 실행할 수 있는 어셈블리로 컴파일러.

시작 하려면 열기 `ClassLibraryDemo.fs`합니다.  일부 코드가 이미 있는 것을 알 수 있습니다. 계속 해 서 클래스 정의 삭제 하며 유지 해야 합니다 [ `namespace` ](../language-reference/namespaces.md) 맨 위에 있는 선언 합니다.

다음으로 새를 만듭니다 [ `module` ](../language-reference/modules.md) 호출 `PigLatin` 복사는 `toPigLatin` 같이 함수에:

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

을 엽니다는 `Script.fsx` 다시 파일 및 전체 삭제 `toPigLatin` 하지만 파일에 다음 두 줄을 유지 하도록 확인:

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```
텍스트 줄이 모두를 선택 하 고 FSI에서 다음이 줄을 실행 하려면 Alt + Enter 키를 누릅니다. Pig Latin 라이브러리의 내용을 FSI 프로세스로 로드 됩니다 이러한 및 `open` 는 `ClassLibraryDemo` 네임 스페이스 기능에 액세스할 수 있도록 합니다.

그런 다음 FSI 창에서 사용 하 여 함수를 호출 합니다 `PigLatin` 이전에 정의한 모듈:

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

성공 동일한 결과 얻게에서 로드 하지만, 이제는 F# 구현 파일입니다. 여기서 주요 차이점은 F# 소스 파일이 FSI에서 뿐 아니라 어디서 나 실행할 수 있는 어셈블리에 컴파일됩니다.

## <a name="summary"></a>요약

이 문서에서는 알아보았습니다.

1. Ionide 사용 하 여 Visual Studio Code를 설정 하는 방법입니다.
2. 첫 번째를 만드는 방법 F# Ionide 사용 하 여 프로젝트입니다.
3. 사용 하는 방법 F# 첫 번째 쓸 스크립팅 F# Ionide에서 작동 하 고 FSI에서 실행 합니다.
4. 스크립트 코드를 마이그레이션하는 방법 F# 원본 및 다음 FSI에서 해당 코드를 호출 합니다.

많은 쓸 엔드가 이제는 F# Visual Studio Code 및 Ionide를 사용 하는 코드입니다.

## <a name="troubleshooting"></a>문제 해결

여기 몇 가지 방법으로에 실행 될 수 있는 특정 문제를 해결할 수 있습니다.

1. Ionide의 기능을 편집 하는 코드를 가져오려면 사용자 F# 파일은 Visual Studio Code 작업 영역에 열려 있는 폴더 내에서 디스크에 저장 해야 합니다.
2. 시스템 변경 내용을 적용 하거나 열려 있는 Visual Studio Code를 사용 하 여 Ionide 필수 구성 요소를 설치, Visual Studio Code를 다시 시작 합니다.
3. 사용할 수 있는지 확인 합니다 F# 컴파일러 및 F# 정규화 된 경로 사용 하지 않고 명령줄에서 대화형입니다. 입력 하 여 수행할 수 `fsc` 에 대 한 명령줄에는 F# 컴파일러, 및 `fsi` 또는 `fsharpi` 시각적 개체에 대 한 F# 각각 Windows 및 linux/Mac에서 Mono에서 도구.
4. 잘못 된 문자가 프로젝트 디렉터리에 있는 Ionide 작동 하지 않을 수 있습니다.  이 경우 프로젝트 디렉터리를 이름을 바꿉니다.
5. Ionide 명령의 none으로 작업 하는 경우 확인 프로그램 [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) 확인 하는 경우 실수로 재정의 하 고 있습니다.
6. Ionide 컴퓨터 손상 되었습니다. 문제는 수정 사항이 제거해 봅니다는 `ionide-fsharp` 컴퓨터에 디렉터리 및 플러그 인 도구 모음을 다시 설치 합니다.

Ionide는 오픈 소스 프로젝트 작성 및의 멤버에 의해 유지 관리는 F# 커뮤니티입니다. 문제를 보고 하 고 자유롭게에 기여 하세요는 [Ionide VSCode: FSharp GitHub 리포지토리](https://github.com/ionide/ionide-vscode-fsharp)합니다.

보고서에 문제가 있다면 따르세요 [문제를 보고할 때 사용 하 여 로그를 가져오는 데 필요한 지침](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting)합니다.

Ionide 개발자가 자세한 도움말도 요청할 수 있습니다 하 고 F# 커뮤니티에는 [Ionide Gitter 채널](https://gitter.im/ionide/ionide-project)합니다.

## <a name="next-steps"></a>다음 단계

에 대 한 자세한 내용은 F# 언어의 기능을 확인 하 고 [둘러보기 F# ](../tour.md)합니다.
