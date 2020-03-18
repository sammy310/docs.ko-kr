---
title: '자습서: .NET Core 도구 만들기'
description: .NET Core 도구를 만드는 방법을 알아봅니다. 도구는 .NET Core CLI를 사용하여 설치되는 콘솔 애플리케이션입니다.
ms.date: 02/12/2020
ms.openlocfilehash: 88cc3be7b149834ace0c5f3ba8ac8c039199908f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156727"
---
# <a name="tutorial-create-a-net-core-tool-using-the-net-core-cli"></a>자습서: .NET Core CLI를 사용하여 .NET Core 도구 만들기

**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전

이 자습서에서는 .NET Core 도구를 만들고 패키지하는 방법을 설명합니다. .NET Core CLI를 사용하면 콘솔 애플리케이션을 도구로 만들 수 있으며 다른 사용자가 설치하고 실행할 수 있습니다. .NET Core 도구는 .NET Core CLI에서 설치되는 NuGet 패키지입니다. 도구에 대한 자세한 내용은 [.NET Core 도구 개요](global-tools.md)를 참조하세요.

만들 도구는 메시지를 입력으로 사용하고 로봇 이미지를 만드는 텍스트 줄과 함께 메시지를 표시하는 콘솔 애플리케이션입니다.

이는 세 가지 자습서 시리즈 중 첫 번째입니다. 이 자습서에서는 도구를 만들고 패키지합니다. 다음 두 자습서에서는 [도구를 전역 도구로 사용](global-tools-how-to-use.md)하고 [도구를 로컬 도구로 사용](local-tools-how-to-use.md)합니다.

## <a name="prerequisites"></a>사전 요구 사항

- [.NET Core SDK 3.1](https://dotnet.microsoft.com/download) 이상 버전

  이 자습서와 이어지는 [전역 도구 자습서](global-tools-how-to-use.md)는 .NET Core SDK 2.1 이상 버전에 적용됩니다. 전역 도구를 해당 버전부터 사용할 수 있기 때문입니다. 그러나 이 자습서에서는 계속해서 [로컬 도구 자습서](local-tools-how-to-use.md)를 진행할 수 있도록 3.1 이상 버전을 설치했다고 가정합니다. 로컬 도구는 .NET Core SDK 3.0부터 사용할 수 있습니다. 도구를 만드는 절차는 전역 도구 또는 로컬 도구로 사용하는지 여부와 관계없이 동일합니다.
  
- 선택하는 텍스트 편집기 또는 코드 편집기입니다.

## <a name="create-a-project"></a>프로젝트 만들기

1. 명령 프롬프트를 열고 *repository*라는 폴더를 만듭니다.

1. *repository* 폴더로 이동하여 다음 명령을 입력합니다.

   ```dotnetcli
   dotnet new console -n microsoft.botsay
   ```

   이 명령은 *repository* 폴더 아래에 *microsoft.botsay*라는 새 폴더를 만듭니다.

1. *microsoft.botsay* 폴더로 이동합니다.

   ```console
   cd microsoft.botsay
   ```

## <a name="add-the-code"></a>코드 추가

1. 코드 편집기를 사용하여 `Program.cs` 파일을 엽니다.

1. 다음 `using` 지시문을 파일의 맨 위에 추가합니다.

   ```csharp
   using System.Reflection;
   ```

1. `Main` 메서드를 다음 코드로 바꿔 애플리케이션의 명령줄 인수를 처리합니다.

   ```csharp
   static void Main(string[] args)
   {
       if (args.Length == 0)
       {
           var versionString = Assembly.GetEntryAssembly()
                                   .GetCustomAttribute<AssemblyInformationalVersionAttribute>()
                                   .InformationalVersion
                                   .ToString();

           Console.WriteLine($"botsay v{versionString}");
           Console.WriteLine("-------------");
           Console.WriteLine("\nUsage:");
           Console.WriteLine("  botsay <message>");
           return;
       }

       ShowBot(string.Join(' ', args));
   }
   ```

   인수가 전달되지 않으면 짧은 도움말 메시지가 표시됩니다. 그렇지 않으면 모든 인수가 다음 단계에서 만드는 `ShowBot` 메서드를 호출하여 단일 문자열로 연결되고 출력됩니다.

1. 문자열 매개 변수를 사용하는 `ShowBot`이라는 새 메서드를 추가합니다. 이 메서드는 텍스트 줄을 사용하여 메시지와 로봇 이미지를 출력합니다.

   ```csharp
   static void ShowBot(string message)
   {
       string bot = $"\n        {message}";
       bot += @"
       __________________
                         \
                          \
                             ....
                             ....'
                              ....
                           ..........
                       .............'..'..
                    ................'..'.....
                  .......'..........'..'..'....
                 ........'..........'..'..'.....
                .'....'..'..........'..'.......'.
                .'..................'...   ......
                .  ......'.........         .....
                .    _            __        ......
               ..    #            ##        ......
              ....       .                 .......
              ......  .......          ............
               ................  ......................
               ........................'................
              ......................'..'......    .......
           .........................'..'.....       .......
        ........    ..'.............'..'....      ..........
      ..'..'...      ...............'.......      ..........
     ...'......     ...... ..........  ......         .......
    ...........   .......              ........        ......
   .......        '...'.'.              '.'.'.'         ....
   .......       .....'..               ..'.....
      ..       ..........               ..'........
             ............               ..............
            .............               '..............
           ...........'..              .'.'............
          ...............              .'.'.............
         .............'..               ..'..'...........
         ...............                 .'..............
          .........                        ..............
           .....
   ";
       Console.WriteLine(bot);
   }
   ```

1. 변경 내용을 저장합니다.

## <a name="test-the-application"></a>애플리케이션 테스트

프로젝트를 실행하고 출력을 확인합니다. 다른 결과를 보려면 명령줄에서 다음 변형을 시도해 보세요.

```dotnetcli
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- Hello from the bot
```

`--` 구분 기호 뒤의 모든 인수가 애플리케이션에 전달됩니다.

## <a name="package-the-tool"></a>도구 패키징

애플리케이션을 도구로 패키지하고 배포하려면 먼저 프로젝트 파일을 수정해야 합니다.

1. *microsoft.botsay.csproj* 파일을 열고 `<PropertyGroup>` 노드 끝에 다음 세 개의 새 XML 노드를 추가합니다.

   ```xml
   <PackAsTool>true</PackAsTool>
   <ToolCommandName>botsay</ToolCommandName>
   <PackageOutputPath>./nupkg</PackageOutputPath>
   ```

   `<ToolCommandName>`은 설치 후 도구를 호출할 명령을 지정하는 선택적 요소입니다. 이 요소를 제공하지 않으면 도구의 명령 이름은 *.csproj* 확장명이 없는 프로젝트 파일 이름입니다.

   `<PackageOutputPath>`는 NuGet 패키지가 생성될 위치를 결정하는 선택적 요소입니다. NuGet 패키지는 .NET Core CLI가 도구를 설치하는 데 사용됩니다.

   이제 프로젝트 파일은 다음 예제와 같습니다.

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">
  
     <PropertyGroup>

       <OutputType>Exe</OutputType>
       <TargetFramework>netcoreapp3.1</TargetFramework>
  
       <PackAsTool>true</PackAsTool>
       <ToolCommandName>botsay</ToolCommandName>
       <PackageOutputPath>./nupkg</PackageOutputPath>
  
     </PropertyGroup>

   </Project>
   ```

1. [dotnet pack](dotnet-pack.md) 명령을 실행하여 NuGet 패키지를 만듭니다.

   ```dotnetcli
   dotnet pack
   ```

   *microsoft.botsay.1.0.0.nupkg* 파일은 *microsoft.botsay.csproj* 파일의 `<PackageOutputPath>` 값으로 식별되는 폴더(이 예제에서는 *./nupkg* 폴더)에 만들어집니다.
  
   공개적으로 도구를 릴리스하려면 `https://www.nuget.org`에 업로드할 수 있습니다. NuGet에서 도구를 사용할 수 있게 되면 개발자는 [dotnet tool install](dotnet-tool-install.md) 명령을 사용하여 도구를 설치할 수 있습니다. 이 자습서에서는 로컬 *nupkg* 폴더에서 패키지를 직접 설치하므로 NuGet에 패키지를 업로드할 필요가 없습니다.

## <a name="troubleshoot"></a>문제 해결

자습서를 수행하는 동안 오류 메시지가 표시되는 경우 [.NET Core 도구 사용 문제 해결](troubleshoot-usage-issues.md)을 참조하세요.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 콘솔 애플리케이션을 만들고 도구로 패키지했습니다. 도구를 전역 도구로 사용하는 방법을 알아보려면 다음 자습서로 이동합니다.

> [!div class="nextstepaction"]
> [전역 도구 설치 및 사용](global-tools-how-to-use.md)

원한다면 전역 도구 자습서를 건너뛰고 로컬 도구 자습서로 바로 이동할 수 있습니다.

> [!div class="nextstepaction"]
> [로컬 도구 설치 및 사용](local-tools-how-to-use.md)
