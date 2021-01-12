---
title: dotnet new에 대한 프로젝트 템플릿 만들기
description: dotnet new 명령에 대한 프로젝트 템플릿을 만드는 방법을 알아봅니다.
author: adegeo
ms.date: 12/11/2020
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: ed40cfd303c70c7b8f198a0f5b593bf1e1ebeaf8
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513135"
---
# <a name="tutorial-create-a-project-template"></a>자습서: 프로젝트 템플릿 만들기

.NET을 사용하여 프로젝트, 파일, 리소스를 생성하는 템플릿을 만들고 배포할 수 있습니다. 이 자습서는 `dotnet new` 명령에 사용할 템플릿을 만들고, 설치하고, 제거하는 방법을 알려주는 시리즈의 2부입니다.

시리즈의 2부에서는 다음 방법에 대해 알아봅니다.

> [!div class="checklist"]
>
> * 프로젝트 템플릿의 리소스 만들기
> * 템플릿 구성 폴더 및 파일 만들기
> * 파일 경로에서 템플릿 설치
> * 항목 템플릿 테스트
> * 항목 템플릿 제거

## <a name="prerequisites"></a>사전 요구 사항

* 이 자습서 시리즈의 [1부](cli-templates-create-item-template.md)를 완료합니다.
* 터미널을 열고 _working\templates_ 폴더로 이동합니다.

## <a name="create-a-project-template"></a>프로젝트 템플릿 만들기

프로젝트 템플릿은 사용자가 코드의 작업 집합을 쉽게 시작할 수 있도록 해주는 즉시 실행 가능한 프로젝트를 생성합니다. .NET에는 콘솔 애플리케이션 또는 클래스 라이브러리와 같은 몇 가지 프로젝트 템플릿이 포함되어 있습니다. 이 예제에서는 C# 9.0을 사용하고 `async main` 진입점을 생성하는 새 콘솔 프로젝트를 만듭니다.

터미널에서 _working\templates_ 폴더로 이동하고 _consoleasync_ 라는 새 하위 폴더를 만듭니다. 하위 폴더를 입력하고 `dotnet new console`을 실행하여 표준 콘솔 애플리케이션을 생성합니다. 이 템플릿에서 생성된 파일을 편집하여 새 템플릿을 만듭니다.

```console
working
└───templates
    └───consoleasync
            consoleasync.csproj
            Program.cs
```

## <a name="modify-programcs"></a>Program.cs 수정

_program.cs_ 파일을 엽니다. 콘솔 프로젝트에서는 비동기 진입점을 사용하지 않으므로 추가해 보겠습니다. 코드를 다음과 같이 변경하고 파일을 저장합니다.

```csharp
using System;
using System.Threading.Tasks;

namespace consoleasync
{
    class Program
    {
        static async Task Main(string[] args)
        {
            await Console.Out.WriteAsync("Hello World with C# 9.0!");
        }
    }
}
```

## <a name="modify-consoleasynccsproj"></a>consoleasync.csproj 수정

프로젝트에서 사용하는 C# 언어 버전을 9.0으로 업데이트해 보겠습니다. _consoleasync.csproj_ 파일을 편집하고 `<LangVersion>` 설정을 `<PropertyGroup>` 노드에 추가합니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>

    <LangVersion>9.0</LangVersion>

  </PropertyGroup>
  
</Project>
```

## <a name="build-the-project"></a>프로젝트 빌드

프로젝트 템플릿을 완료하기 전에 테스트하여 올바르게 컴파일되고 실행되는지 확인해야 합니다.

터미널에서 다음 명령을 실행합니다.

```dotnetcli
dotnet run
```

다음과 같은 출력을 얻습니다.

```console
Hello World with C# 9.0!
```

`dotnet run`을 사용하여 만든 _obj_ 및 _bin_ 폴더를 삭제할 수 있습니다. 이러한 파일을 삭제하면 템플릿에는 템플릿 관련 파일만 포함되고 빌드 작업의 결과로 생성되는 파일은 포함되지 않습니다.

템플릿의 콘텐츠를 만들었으므로 이제 템플릿의 루트 폴더에 템플릿 구성을 만들어야 합니다.

## <a name="create-the-template-config"></a>템플릿 구성 만들기

템플릿은 .NET의 템플릿 루트에 있는 특수 폴더 및 구성 파일에서 인식됩니다. 이 자습서에서 템플릿 폴더는 _working\templates\consoleasync_ 에 있습니다.

템플릿을 만들 때 템플릿 폴더의 모든 파일과 폴더는 특수 구성 폴더를 제외하고 템플릿의 일부로 포함됩니다. 이 구성 폴더는 _.template.config_ 입니다.

먼저 _.template.config_ 라는 새 하위 폴더를 만들고 폴더로 들어갑니다. 그런 다음 _template.json_ 이라는 새 파일을 만듭니다. 폴더 구조는 다음과 같이 표시됩니다.

```console
working
└───templates
    └───consoleasync
        └───.template.config
                template.json
```

원하는 텍스트 편집기에서 _template.json_ 을 열고 다음 JSON 코드를 붙여넣고 저장합니다.

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Console", "C#9" ],
  "identity": "ExampleTemplate.AsyncProject",
  "name": "Example templates: async project",
  "shortName": "consoleasync",
  "tags": {
    "language": "C#",
    "type": "project"
  }
}
```

이 구성 파일에는 템플릿에 대한 모든 설정이 포함되어 있습니다. 기본 설정(예: `name` 및 `shortName`)을 확인할 수 있지만 `project`로 설정된 `tags/type` 값도 있습니다. 이 값에 따라, 만든 템플릿이 프로젝트 템플릿으로 지정됩니다. 만드는 템플릿 형식에 대한 제한은 없습니다. `item` 및 `project` 값은 사용자가 검색 중인 템플릿 형식을 쉽게 필터링할 수 있도록 .NET에서 권장하는 일반적인 이름입니다.

`classifications` 항목은 `dotnet new`를 실행할 때 표시되고 템플릿 목록을 가져오는 **태그** 열을 나타냅니다. 사용자는 분류 태그를 기준으로 검색할 수도 있습니다. .json 파일의 `tags` 속성을 `classifications` 태그 목록과 혼동하지 마세요. 불행히도 두 항목은 이름이 비슷합니다. *template.json* 파일에 대한 전체 스키마는 [JSON Schema Store](http://json.schemastore.org/template)(JSON 스키마 저장소)에서 찾을 수 있습니다. *template.json* 파일에 대한 자세한 내용은 [dotnet 템플릿 wiki](https://github.com/dotnet/templating/wiki)를 참조하세요.

유효한 _.template.config/template.json_ 파일이 있으므로 이제 템플릿을 설치할 준비가 되었습니다. 템플릿을 설치하기 전에 _bin_ 또는 _obj_ 폴더와 같이 템플릿에 포함하지 않을 추가 파일 폴더 및 파일을 삭제해야 합니다. 터미널에서 _consoleasync_ 폴더로 이동하고 `dotnet new -i .\`를 실행하여 현재 폴더에 있는 템플릿을 설치합니다. Linux 또는 macOS 운영 체제를 사용하는 경우 슬래시를 사용합니다(`dotnet new -i ./`).

이 명령은 사용자 템플릿을 포함하여 설치된 템플릿 목록을 출력합니다.

```dotnetcli
dotnet new -i .\
```

그러면 다음과 같은 출력이 표시됩니다.

```console
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name               Language          Tags
--------------------------------------------      -------------------      ------------      ----------------------
Console Application                               console                  [C#], F#, VB      Common/Console
Example templates: async project                  consoleasync             [C#]              Common/Console/C#9
Class library                                     classlib                 [C#], F#, VB      Common/Library
WPF Application                                   wpf                      [C#], VB          Common/WPF
```

### <a name="test-the-project-template"></a>프로젝트 템플릿 테스트

프로젝트 템플릿을 설치했으므로 이제 템플릿을 테스트합니다.

1. _test_ 폴더로 이동합니다.

1. `dotnet run` 명령으로 쉽게 테스트할 수 있는 작업 프로젝트를 생성하는 다음 명령을 사용하여 새 콘솔 애플리케이션을 만듭니다.

    ```dotnetcli
    dotnet new consoleasync
    ```

    다음과 같은 출력을 얻습니다.

    ```console
    The template "Example templates: async project" was created successfully.
    ```

1. 다음 명령을 사용하여 프로젝트를 실행합니다.

    ```dotnetcli
    dotnet run
    ```

    다음과 같은 출력을 얻습니다.

    ```console
    Hello World with C# 9.0!
    ```

지금까지 .NET을 사용하여 프로젝트 템플릿을 만들고 배포했습니다. 이 자습서 시리즈의 다음 부분에 대비하여, 여기서 만든 템플릿을 제거해야 합니다. 또한 _test_ 폴더에서 모든 파일을 삭제해야 합니다. 그러면 이 자습서의 다음 주요 섹션을 위해 정리된 상태로 되돌아갑니다.

### <a name="uninstall-the-template"></a>템플릿 제거

파일 경로를 사용하여 템플릿을 설치했으므로 **절대** 파일 경로를 사용하여 템플릿을 제거해야 합니다. `dotnet new -u` 명령을 실행하여 설치된 템플릿 목록을 확인할 수 있습니다. 사용자 템플릿은 마지막에 나열되어야 합니다. 나열된 `Uninstall Command`를 사용하여 템플릿을 제거합니다.

```dotnetcli
dotnet new -u
```

그러면 다음과 같은 출력이 표시됩니다.

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ProjectTemplates.2.2
    Details:
      NuGetPackageId: Microsoft.DotNet.Common.ProjectTemplates.2.2
      Version: 1.0.2-beta4
      Author: Microsoft
    Templates:
      Class library (classlib) C#
      Class library (classlib) F#
      Class library (classlib) VB
      Console Application (console) C#
      Console Application (console) F#
      Console Application (console) VB
    Uninstall Command:
      dotnet new -u Microsoft.DotNet.Common.ProjectTemplates.2.2

... cut to save space ...

  C:\Test\templatetutorial\working\templates\consoleasync
    Templates:
      Example templates: async project (consoleasync) C#
    Uninstall Command:
      dotnet new -u C:\working\templates\consoleasync
```

만든 템플릿을 제거하려면 출력에 표시된 `Uninstall Command`를 실행합니다.

```dotnetcli
dotnet new -u C:\working\templates\consoleasync
```

## <a name="next-steps"></a>다음 단계

이 자습서에서는 프로젝트 템플릿을 만들었습니다. 항목 템플릿과 프로젝트 템플릿을 모두 사용하기 쉬운 파일로 패키징하는 방법을 알아보려면 이 자습서 시리즈를 계속 진행하세요.

> [!div class="nextstepaction"]
> [템플릿 팩 만들기](cli-templates-create-template-pack.md)
