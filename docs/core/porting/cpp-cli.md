---
title: C++/CLI 프로젝트를 .NET Core로 마이그레이션
description: C++/CLI 프로젝트를 .NET Core로 이식하는 방법에 대해 알아봅니다.
author: mjrousos
ms.date: 01/10/2020
ms.openlocfilehash: eb03f2a5ff42e8279fd3ebd6ee6fb6d955f6798d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75964862"
---
# <a name="how-to-port-a-ccli-project-to-net-core"></a>C++/CLI 프로젝트를 .NET Core로 이식하는 방법

.NET Core 3.1 및 Visual Studio 2019 버전 16.4부터 시작하면 [C++/CLI 프로젝트](/cpp/dotnet/dotnet-programming-with-cpp-cli-visual-cpp)는 .NET Core를 대상으로 할 수 있습니다. 이 지원을 통해 C++/CLI interop 레이어가 있는 Windows 데스크톱 애플리케이션을 .NET Core로 이식할 수 있습니다. 이 문서에서는 C++/CLI 프로젝트를 .NET Framework에서 .NET Core 3.1로 이식하는 방법을 설명합니다.

## <a name="ccli-net-core-limitations"></a>C++/CLI .NET Core 제한 사항

다른 언어에 비해 C++/CLI 프로젝트를 .NET Core로 이식하는 데는 몇 가지 중요한 제한 사항이 있습니다.

* .NET Core에 대한 C++/CLI 지원은 Windows 전용입니다.
* C++/CLI 프로젝트는 .NET Standard를 대상으로 할 수 없습니다. .NET Core(또는 .NET Framework)만 대상으로 할 수 있습니다.
* C++/CLI 프로젝트는 새 SDK 스타일 프로젝트 파일 형식을 지원하지 않습니다. 대신 .NET Core를 대상으로 하는 경우에도 C++/CLI 프로젝트는 기존 vcxproj 파일 형식을 사용합니다.
* C++/CLI 프로젝트는 여러 .NET 플랫폼을 멀티 타기팅할 수 없습니다. .NET Framework와 .NET Core 모두에 대해 C++/CLI 프로젝트를 빌드해야 하는 경우 별도의 프로젝트 파일을 사용하세요.
* .NET Core는 `-clr:pure` 또는 `-clr:safe` 컴파일을 지원하지 않습니다. 새 `-clr:netcore` 옵션(.NET Framework의 `-clr`와 동일)만 지원합니다.

## <a name="port-a-ccli-project"></a>C++/CLI 프로젝트 이식

C++/CLI 프로젝트를 .NET Core로 이식하려면 vcxproj 파일을 다음과 같이 변경합니다. C++/CLI 프로젝트가 SDK 스타일의 프로젝트 파일을 사용하지 않기 때문에 이 마이그레이션 단계는 다른 프로젝트 형식에 필요한 단계와 다릅니다.

1. `<CLRSupport>true</CLRSupport>` 속성을 `<CLRSupport>NetCore</CLRSupport>`로 바꿉니다. 이 속성은 주로 구성별 속성 그룹에 있으므로 여러 위치에서 바꿔야 할 수 있습니다.
2. `<TargetFrameworkVersion>` 속성을 `<TargetFramework>netcoreapp3.1</TargetFramework>`로 바꿉니다.
3. 모든 .NET Framework 참조(예: `<Reference Include="System" />`)를 제거합니다. .NET Core SDK 어셈블리는 `<CLRSupport>NetCore</CLRSupport>`를 사용할 때 자동으로 참조됩니다.
4. .NET Core에서 사용할 수 없는 API를 제거하려면 필요에 따라 cpp 파일의 API 사용을 업데이트합니다. C++/CLI 프로젝트는 상당히 얇은 interop 계층이기 때문에 필요한 변경 내용이 많지 않을 수도 있습니다. [.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md)는 전적으로 관리되는 이진 파일과 마찬가지로 C++/CLI 이진에서 사용하는 지원되지 않는 .NET API를 식별하는 데 사용할 수 있습니다. 코드 이식성을 확인하고 .NET Core API와 함께 작동하도록 프로젝트를 업데이트하는 방법에 대한 지침은 [라이브러리 이식 지침](./libraries.md#determine-portability)에서 확인할 수 있습니다.

### <a name="wpf-and-windows-forms-usage"></a>WPF 및 Windows Forms 사용법

.NET Core C++/CLI 프로젝트는 Windows Forms 및 WPF API를 사용할 수 있습니다. 해당 Windows 데스크톱 API를 사용하려면 UI 라이브러리에 명시적 프레임워크 참조를 추가해야 합니다. Windows 데스크톱 API를 사용하는 SDK 스타일 프로젝트는 `Microsoft.NET.Sdk.WindowsDesktop` SDK를 사용하여 필요한 프레임워크 라이브러리를 자동으로 참조합니다. C++/CLI 프로젝트는 SDK 스타일 프로젝트 형식을 사용하지 않으므로 .NET Core를 대상으로 할 때 명시적 프레임워크 참조를 추가해야 합니다.

Windows Forms API를 사용하려면 다음 참조를 vcxproj 파일에 추가하세요.

```xml
<!-- Reference all of Windows Forms -->
<FrameworkReference Include="Microsoft.WindowsDesktop.App.WindowsForms" />
```

WPF API를 사용하려면 다음 참조를 vcxproj 파일에 추가하세요.

```xml
<!-- Reference all of WPF -->
<FrameworkReference Include="Microsoft.WindowsDesktop.App.WPF" />
```

Windows Forms 및 WPF API를 모두 사용하려면 다음 참조를 vcxproj 파일에 추가하세요.

```xml
<!-- Reference the entirety of the Windows desktop framework:
     Windows Forms, WPF, and the types that provide integration between them -->
<FrameworkReference Include="Microsoft.WindowsDesktop.App" />
```

현재는 Visual Studio의 참조 관리자를 사용하여 해당 참조를 추가할 수 없습니다. 대신 프로젝트 파일을 수동으로 업데이트하세요. 이 업데이트는 Visual Studio에서 프로젝트를 언로드한 다음 프로젝트 파일을 편집하여 수행할 수 있습니다. VS Code 같은 다른 편집기를 사용할 수도 있습니다.

## <a name="build-without-msbuild"></a>MSBuild를 사용하지 않고 빌드

MSBuild를 사용하지 않고 C++/CLI 프로젝트를 빌드할 수도 있습니다. *cl.exe* 및 *link.exe*를 사용하여 .NET Core용 C++CLI 프로젝트를 직접 빌드하려면 다음 단계를 수행하세요.

1. 컴파일하는 경우 `-clr:netcore`를 *cl.exe*에 전달하세요.
2. 필요한 .NET Core 참조 어셈블리를 참조하세요.
3. 연결할 때 *ijwhost*를 찾을 수 있도록 .NET Core 앱 호스트 디렉터리를 `LibPath`로 제공하세요.
4. .NET Core 앱 호스트 디렉터리에서 *ijwhost.dll*을 프로젝트의 출력 디렉터리로 복사하세요.
5. 관리 코드를 실행할 애플리케이션의 첫 번째 구성 요소에 대한 [runtimeconfig.template.json](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) 파일이 있는지 확인하세요. 애플리케이션에 관리형 진입점이 있으면 `runtime.config` 파일이 자동으로 만들어지고 복사됩니다. 그러나 애플리케이션에 네이티브 진입점이 있으면 .NET Core 런타임을 사용하기 위해 첫 번째 C++/CLI 라이브러리의 `runtimeconfig.json` 파일을 만들어야 합니다.

## <a name="known-issues"></a>알려진 문제

.NET Core를 대상으로 하는 C++/CLI 프로젝트로 작업할 때 살펴볼 몇 가지 알려진 이슈가 있습니다.

* .NET Core C++/CLI 프로젝트의 WPF 프레임워크 참조는 현재 기호를 가져올 수 없다는 일부 불필요한 경고를 발생시킵니다. 해당 경고는 무시해주세요. 곧 해결될 예정입니다.
* 애플리케이션에 네이티브 진입점이 있는 경우 관리 코드를 먼저 실행하는 C++/CLI 라이브러리에 [runtimeconfig.json](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) 파일이 필요합니다. 이 구성 파일은 .NET Core 런타임이 시작될 때 사용됩니다. C++/CLI 프로젝트는 빌드 시 `runtimeconfig.json` 파일을 자동으로 만들지 않으므로 파일을 수동으로 생성해야 합니다. 관리형 진입점에서 C++/CLI 라이브러리를 호출하는 경우에는 진입점 어셈블리에 런타임을 시작할 때 사용하는 파일이 있으므로 C++/CLI 라이브러리에 `runtimeconfig.json` 파일이 필요하지 않습니다. 다음은 간단한 샘플 `runtimeconfig.json` 파일입니다. 자세한 내용은 [GitHub 사양](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)을 참조하세요.

    ```json
    {
          "runtimeOptions": {
             "tfm": "netcoreapp3.1",
             "framework": {
                "name": "Microsoft.NETCore.App",
                "version": "3.1.0"
             }
          }
    }
    ```
