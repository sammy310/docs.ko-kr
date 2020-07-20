---
title: Visual Studio Code로 .NET Standard 클래스 라이브러리 만들기
description: Visual Studio Code를 사용하여 .NET Standard 클래스 라이브러리를 만드는 방법을 알아봅니다.
ms.date: 06/08/2020
ms.openlocfilehash: 714b5cf2125f1d296adc4a4dc7d1b6c9420417ed
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86308886"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio-code"></a>자습서: Visual Studio Code로 .NET Standard 라이브러리 만들기

이 자습서에서는 단일 문자열 처리 메서드를 포함하는 간단한 유틸리티 라이브러리를 만듭니다. <xref:System.String> 클래스의 멤버인 것처럼 호출할 수 있도록 [확장 메서드](../../csharp/programming-guide/classes-and-structs/extension-methods.md)로 구현합니다.

*클래스 라이브러리*는 애플리케이션에서 호출되는 형식 및 메서드를 정의합니다. .NET Standard 2.0을 대상으로 하는 클래스 라이브러리는 .NET Standard의 해당 버전을 지원하는 모든 .NET 구현에서 라이브러리를 호출할 수 있습니다. 클래스 라이브러리를 마칠 때 타사 구성 요소 또는 하나 이상의 애플리케이션이 포함된 번들 구성 요소로 배포할 수 있습니다.

## <a name="prerequisites"></a>사전 요구 사항

1. [C# 확장](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)이 설치된 [Visual Studio Code](https://code.visualstudio.com/). Visual Studio Code에 확장을 설치하는 방법에 대한 자세한 내용은 [VS Code 확장 Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery)를 참조하세요.
2. [.NET Core 3.1 SDK 이상](https://dotnet.microsoft.com/download)

## <a name="create-a-solution"></a>솔루션 만들기

먼저 클래스 라이브러리 프로젝트를 배치할 빈 솔루션을 만듭니다. 솔루션은 하나 이상의 프로젝트에 대한 컨테이너로 작동합니다. 동일한 솔루션에 관련 프로젝트를 추가합니다.

1. Visual Studio Code를 시작합니다.

1. 주 메뉴에서 **파일** > **폴더 열기** (macOS에서는 **열기...** )를 선택합니다.

1. **폴더 열기** 대화 상자에서 *ClassLibraryProjects* 폴더를 만들고 **폴더 선택**(macOS에서는 **열기**)을 클릭합니다.

1. 주 메뉴에서 **보기** > **터미널**을 선택하여 Visual Studio Code에서 **터미널**을 엽니다.

   *ClassLibraryProjects* 폴더에서 명령 프롬프트와 함께 **터미널**이 열립니다.

1. **터미널**에서 다음 명령을 입력합니다.

   ```dotnetcli
   dotnet new sln
   ```

   터미널 출력은 다음 예제처럼 표시됩니다.

   ```
   The template "Solution File" was created successfully.
   ```

## <a name="create-a-class-library-project"></a>클래스 라이브러리 프로젝트 만들기

"StringLibrary"라는 새로운 .NET Standard 클래스 라이브러리 프로젝트를 솔루션에 추가합니다.

1. 터미널에서 다음 명령을 실행하여 라이브러리 프로젝트를 만듭니다.

   ```dotnetcli
   dotnet new classlib -o StringLibrary
   ```

   터미널 출력은 다음 예제처럼 표시됩니다.

   ```
   The template "Class library" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on StringLibrary\StringLibrary.csproj...
     Determining projects to restore...
     Restore completed in 328.13 ms for C:\Projects\ClassLibraryProjects\StringLibrary\StringLibrary.csproj.
   Restore succeeded.
   ```

1. 다음 명령을 실행하여 라이브러리 프로젝트를 솔루션에 추가합니다.

   ```dotnetcli
   dotnet sln add StringLibrary/StringLibrary.csproj
   ```

   터미널 출력은 다음 예제처럼 표시됩니다.

   ```
   Project `StringLibrary\StringLibrary.csproj` added to the solution.
   ```

1. 라이브러리에 올바른 버전의 .NET Standard가 대상으로 지정되었는지 확인합니다. **Explorer**에서 *StringLibrary/StringLibrary.csproj*를 엽니다.

   `TargetFramework` 요소는 프로젝트가 .NET Standard 2.0을 대상으로 함을 보여 줍니다.

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">

     <PropertyGroup>
       <TargetFramework>netstandard2.0</TargetFramework>
     </PropertyGroup>

   </Project>
   ```

1. *Class1.cs*를 열고 코드를 다음 코드로 바꿉니다.

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

   클래스 라이브러리 `UtilityLibraries.StringLibrary`에는 `StartsWithUpper`라는 메서드가 포함되어 있습니다. 이 메서드는 현재 문자열 인스턴스가 대문자로 시작하는지 여부를 나타내는 <xref:System.Boolean> 값을 반환합니다. 유니코드 표준은 대문자와 소문자를 구분합니다. <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> 메서드는 문자가 대문자인 경우 `true`를 반환합니다.

1. 파일을 저장합니다.

1. 다음 명령을 실행하여 솔루션을 빌드하고 프로젝트가 오류 없이 컴파일되는지 확인합니다.

   ```dotnetcli
   dotnet build
   ```

   터미널 출력은 다음 예제처럼 표시됩니다.

   ```
   Microsoft (R) Build Engine version 16.6.0 for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.
     Determining projects to restore...
     All projects are up-to-date for restore.
     You are using a preview version of .NET Core. See: https://aka.ms/dotnet-core-preview
     StringLibrary -> C:\Projects\ClassLibraryProjects\StringLibrary\bin\Debug\netstandard2.0\StringLibrary.dll
   Build succeeded.
       0 Warning(s)
       0 Error(s)
   Time Elapsed 00:00:02.78
   ```

## <a name="add-a-console-app-to-the-solution"></a>솔루션에 콘솔 앱 추가

클래스 라이브러리를 사용하는 콘솔 애플리케이션을 추가합니다. 이 앱은 사용자에게 문자열을 입력하라는 메시지를 표시하고 문자열이 대문자로 시작하는지 여부를 보고합니다.

1. 터미널에서 다음 명령을 실행하여 콘솔 앱 프로젝트를 만듭니다.

   ```dotnetcli
   dotnet new console -o ShowCase
   ```

   터미널 출력은 다음 예제처럼 표시됩니다.

   ```
   The template "Console Application" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on ShowCase\ShowCase.csproj...  
     Determining projects to restore...
     Restore completed in 210.78 ms for C:\Projects\ClassLibraryProjects\ShowCase\ShowCase.csproj.
   Restore succeeded.
   ```

1. 다음 명령을 실행하여 솔루션에 콘솔 앱 프로젝트를 추가합니다.

   ```dotnetcli
   dotnet sln add ShowCase/ShowCase.csproj
   ```

   터미널 출력은 다음 예제처럼 표시됩니다.

   ```
   Project `ShowCase\ShowCase.csproj` added to the solution.
   ```

1. *ShowCase/Program.cs*를 열고 모든 코드를 다음 코드로 바꿉니다.

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   코드는 `row` 변수를 사용하여 콘솔 창에 기록된 데이터 행 수를 유지합니다. 25보다 크거나 같으면 코드는 콘솔 창을 지우고 사용자에게 메시지를 표시합니다.

   프로그램에서 문자열을 입력하라는 메시지를 사용자에게 표시합니다. 문자열이 대문자로 시작하는지 여부를 나타냅니다. 사용자가 문자열을 입력하지 않고 <kbd>Enter</kbd> 키를 누르면 애플리케이션이 종료되고 콘솔 창이 닫힙니다.

1. 변경 내용을 저장합니다.

## <a name="add-a-project-reference"></a>프로젝트 참조 추가

처음에는 새 콘솔 앱 프로젝트가 클래스 라이브러리에 액세스할 수 없습니다. 클래스 라이브러리의 메서드를 호출할 수 있도록 허용하려면 클래스 라이브러리 프로젝트에 대한 프로젝트 참조를 만듭니다.

1. 다음 명령을 실행합니다.

   ```dotnetcli
   dotnet add ShowCase/ShowCase.csproj reference StringLibrary/StringLibrary.csproj
   ```

   터미널 출력은 다음 예제처럼 표시됩니다.

   ```
   Reference `..\StringLibrary\StringLibrary.csproj` added to the project.
   ```

## <a name="run-the-app"></a>앱 실행

1. 터미널에서 다음 명령을 실행합니다.

   ```dotnetcli
   dotnet run --project ShowCase/ShowCase.csproj
   ```

1. 문자열을 입력하고 <kbd>Enter</kbd> 키를 눌러 프로그램을 사용해 본 다음 <kbd>Enter</kbd> 키를 눌러 끝냅니다.

   터미널 출력은 다음 예제처럼 표시됩니다.

   ```
   Press <Enter> only to exit; otherwise, enter a string and press <Enter>:

   A string that starts with an uppercase letter
   Input: A string that starts with an uppercase letter
   Begins with uppercase? : Yes

   A string that starts with a lowercase letter
   Input: A string that starts with a lowercase letter
   Begins with uppercase? : Yes
   ```

## <a name="additional-resources"></a>추가 자료

* [.NET Core CLI를 사용하여 라이브러리 개발](libraries.md)
* [지원되는 .NET Standard 버전 및 플랫폼](../../standard/net-standard.md)

## <a name="next-steps"></a>다음 단계

이 자습서에서는 솔루션을 만들고, 라이브러리 프로젝트를 추가하고, 라이브러리를 사용하는 콘솔 앱 프로젝트를 추가했습니다. 다음 자습서에서는 솔루션에 단위 테스트 프로젝트를 추가합니다.

> [!div class="nextstepaction"]
> [Visual Studio Code에서 .NET Core로 .NET Standard 라이브러리 테스트](testing-library-with-visual-studio-code.md)
