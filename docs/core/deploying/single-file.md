---
title: 단일 파일 애플리케이션
description: 단일 파일 애플리케이션이란 무엇이고, 이 애플리케이션 배포 모델 사용을 왜 고려해야 하는지를 알아봅니다.
author: lakshanf
ms.author: lakshanf
ms.date: 12/17/2020
ms.openlocfilehash: 10ffc947f6a3adcf2889a03edd2616007ce236f3
ms.sourcegitcommit: 3a8f1979a98c6c19217a1930e0af5908988eb8ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2021
ms.locfileid: "98536140"
---
# <a name="single-file-deployment-and-executable"></a>단일 파일 배포 및 실행 파일

모든 애플리케이션 종속 파일을 하나의 이진 파일로 묶으면 애플리케이션 개발자가 애플리케이션을 단일 파일로 배포할 수 있습니다. 이 배포 모델은 .NET Core 3.0부터 사용할 수 있었으며 .NET 5.0에서 향상되었습니다. 이전의 .NET Core 3.0에서는 사용자가 단일 파일 앱을 실행할 때 .NET Core 호스트에서 먼저 모든 파일을 임시 디렉터리로 추출한 후 애플리케이션을 실행했습니다. .NET 5.0에서는 앱에서 파일을 추출할 필요 없이 코드를 직접 실행하여 이 환경을 개선합니다.

단일 파일 배포는 [프레임워크 종속 배포 모델](index.md#publish-framework-dependent)과 [자체 포함 애플리케이션](index.md#publish-self-contained)에 모두 사용할 수 있습니다. 자체 포함 애플리케이션의 단일 파일 크기는 런타임 및 프레임워크 라이브러리를 포함하므로 커집니다. 단일 파일 배포 옵션을 [ReadyToRun](ready-to-run.md) 및 [Trim(.NET 5.0의 실험적 기능)](trim-self-contained.md) 게시 옵션과 함께 사용할 수 있습니다.

## <a name="api-incompatibility"></a>API 비호환성

일부 API는 단일 파일 배포와 호환되지 않으며, 이러한 API를 사용하는 애플리케이션은 수정이 필요할 수 있습니다. 사용 중인 타사 프레임워크나 패키지에도 이러한 API 중 하나가 사용될 수 있으며, 이 경우 수정이 필요할 수 있습니다. 문제의 가장 일반적인 원인은 애플리케이션과 함께 제공되는 파일 또는 DLL의 파일 경로에 대한 종속성입니다.

아래 표에는 단일 파일 사용을 위한 관련 런타임 라이브러리 API 세부 정보가 나와 있습니다.

| API                            | 참고                                                                   |
|--------------------------------|------------------------------------------------------------------------|
| `Assembly.Location`            | 빈 문자열을 반환합니다.                                               |
| `Module.FullyQualifiedName`    | `<Unknown>` 값이 포함된 문자열을 반환하거나 예외를 throw합니다. |
| `Module.Name`                  | `<Unknown>` 값이 포함된 문자열을 반환합니다.                        |
| `Assembly.GetFile`             | <xref:System.IO.IOException>을 버립니다.                                   |
| `Assembly.GetFiles`            | <xref:System.IO.IOException>을 버립니다.                                   |
| `Assembly.CodeBase`            | <xref:System.PlatformNotSupportedException>을 버립니다.                    |
| `Assembly.EscapedCodeBase`     | <xref:System.PlatformNotSupportedException>을 버립니다.                    |
| `AssemblyName.CodeBase`        | `null`를 반환합니다.                                                        |
| `AssemblyName.EscapedCodeBase` | `null`를 반환합니다.                                                        |

일반적인 시나리오를 해결하기 위한 몇 가지 권장 사항이 있습니다.

* 실행 파일 옆의 파일에 액세스하려면 <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>을 사용합니다.

* 실행 파일의 파일 이름을 찾으려면 <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>의 첫 번째 요소를 사용합니다.

* 느슨한 파일이 제공되는 것을 완전히 방지하려면 [포함 리소스](../../framework/resources/creating-resource-files-for-desktop-apps.md)를 사용하는 것이 좋습니다.

## <a name="attaching-a-debugger"></a>디버거 연결

Linux에서 자체 포함 단일 파일 프로세스나 디버그 크래시 덤프에 연결할 수 있는 유일한 디버거는 [LLDB를 포함한 SOS](../diagnostics/dotnet-sos.md)입니다.

Windows와 Mac에서는 Visual Studio 및 VS Code를 사용하여 크래시 덤프를 디버그할 수 있습니다. 실행 중인 자체 포함 단일 파일 실행 파일에 연결하려면 추가 파일 _mscordbi.{dll,so}_ 가 필요합니다.

이 파일이 없으면 Visual Studio에서 “프로세스에 연결할 수 없습니다. 디버그 구성 요소가 설치되지 않았습니다.” 오류가 발생할 수 있고, VS Code에서는 “프로세스에 연결하지 못했습니다: 알 수 없는 오류: 0x80131c3c” 오류가 발생할 수 있습니다.

이러한 오류를 해결하려면 실행 파일 옆에 _mscordbi_ 를 복사해야 합니다. _mscordbi_ 는 기본적으로 애플리케이션의 런타임 ID를 사용하여 하위 디렉터리에 `publish`됩니다. 따라서 예를 들어 `-r win-x64` 매개 변수를 사용하여 Windows용 `dotnet` CLI로 자체 포함 단일 파일 실행 파일을 게시하는 경우 실행 파일은 _bin/Debug/net5.0/win-x64/publish_ 에 배치됩니다. _mscordbi.dll_ 복사본은 _bin/Debug/net5.0/win-x64_ 에 있습니다.

## <a name="other-considerations"></a>기타 고려 사항

단일 파일은 기본적으로 네이티브 라이브러리를 묶지 않습니다. Linux에서는 런타임을 번들로 사전 링크하며, 애플리케이션 네이티브 라이브러리만 단일 파일 앱과 동일한 디렉터리에 배포됩니다. Windows에서는 호스팅 코드만 사전 링크하며, 런타임 및 애플리케이션 네이티브 라이브러리가 모두 단일 파일 앱과 동일한 디렉터리에 배포됩니다. 그러면 네이티브 파일을 단일 파일에서 제외해야 하는 좋은 디버깅 환경이 보장됩니다. `IncludeNativeLibrariesForSelfExtract` 플래그를 설정하면 네이티브 라이브러리가 단일 파일 번들에 포함되지만 단일 파일 애플리케이션을 실행할 때 클라이언트 머신의 임시 디렉터리에 파일이 추출됩니다.

`IncludeAllContentForSelfExtract`를 지정하면 실행 파일을 실행하기 전에 모든 파일이 추출됩니다. 이렇게 하면 원래 .NET Core 단일 파일 배포 동작이 유지됩니다.

단일 파일 애플리케이션에는 관련된 모든 PDB 파일이 함께 포함되며, 기본적으로 함께 제공되지 않습니다. 빌드하는 프로젝트의 어셈블리 내부에 PDB를 포함하려면 [아래](#include-pdb-files-inside-the-bundle) 설명된 대로 `DebugType`을 `embedded`로 설정합니다.

관리형 C++ 구성 요소는 단일 파일 배포에 적합하지 않으므로 단일 파일과 호환되도록 C# 또는 다른 비관리형 C++ 언어로 애플리케이션을 작성하는 것이 좋습니다.

## <a name="exclude-files-from-being-embedded"></a>파일이 포함되지 않도록 제외

다음 메타데이터를 설정하면 특정 파일이 단일 파일에 포함되지 않도록 명시적으로 제외할 수 있습니다.

```xml
<ExcludeFromSingleFile>true</ExcludeFromSingleFile>
```

예를 들어 일부 파일을 게시 디렉터리에 저장하지만 단일 파일에 묶이지 않도록 하려면 다음을 수행합니다.

```xml
<ItemGroup>
  <Content Update="Plugin.dll">
    <CopyToPublishDirectory>PreserveNewest</CopyToPublishDirectory>
    <ExcludeFromSingleFile>true</ExcludeFromSingleFile>
  </Content>
</ItemGroup>
```

## <a name="include-pdb-files-inside-the-bundle"></a>번들 내에 PDB 파일 포함

어셈블리의 PDB 파일은 아래 설정을 사용하여 어셈블리 자체(`.dll`)에 포함할 수 있습니다. 기호는 어셈블리의 일부이므로 단일 파일 애플리케이션의 일부가 됩니다.

```xml
<DebugType>embedded</DebugType>
```

예를 들어 어셈블리의 프로젝트 파일에 다음 속성을 추가하여 해당 어셈블리에 PDB 파일을 포함합니다.

```xml
<PropertyGroup>
  <DebugType>embedded</DebugType>
</PropertyGroup>
```

## <a name="publish-a-single-file-app---sample-project-file"></a>단일 파일 앱 게시 - 샘플 프로젝트 파일

다음은 단일 파일 게시를 지정하는 샘플 프로젝트 파일입니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <PublishSingleFile>true</PublishSingleFile>
    <SelfContained>true</SelfContained>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
    <PublishReadyToRun>true</PublishReadyToRun>
  </PropertyGroup>

</Project>
```

위 속성에는 다음과 같은 함수가 있습니다.

* `PublishSingleFile` - 단일 파일 게시를 사용하도록 설정합니다.
* `SelfContained` - 앱이 자체 포함인지, 프레임워크 종속인지를 결정합니다.
* `RuntimeIdentifier` - 대상으로 할 [OS 및 CPU 종류](../rid-catalog.md)를 지정합니다.
* `PublishTrimmed` - 자체 포함 앱에만 지원되는 [어셈블리 트리밍](trim-self-contained.md)을 사용하도록 설정합니다.
* `PublishReadyToRun` - [AOT(Ahead-Of-Time) 컴파일](ready-to-run.md)을 사용하도록 설정합니다.

**참고:**

* 앱은 OS 및 아키텍처별로 다릅니다. Linux x64, Linux ARM64, Windows x64 등과 같은 각 구성에 대해 게시해야 합니다.
* *\*.runtimeconfig.json* 과 같은 구성 파일은 단일 파일에 포함됩니다. 추가 구성 파일이 필요한 경우 단일 파일 옆에 배치할 수 있습니다.

## <a name="publish-a-single-file-app---cli"></a>단일 파일 앱 게시 - CLI

[dotnet publish](../tools/dotnet-publish.md) 명령을 사용하여 단일 파일 애플리케이션을 게시합니다. 앱을 게시할 때 다음 속성을 설정합니다.

- 특정 런타임에 대해 게시: `-r win-x64`
- 단일 파일로 게시: `-p:PublishSingleFile=true`

다음 예제에서는 Windows용 앱을 자체 포함 단일 파일 애플리케이션으로 게시합니다.

```dotnetcli
dotnet publish -r win-x64 -p:PublishSingleFile=true --self-contained true
```

다음 예제에서는 Linux용 앱을 프레임워크 종속 단일 파일 애플리케이션으로 게시합니다.

```dotnetcli
dotnet publish -r linux-x64 -p:PublishSingleFile=true --self-contained false
```

자세한 내용은 [.NET Core CLI를 사용하여 .NET Core 앱 게시](deploy-with-cli.md)를 참조하세요.

## <a name="publish-a-single-file-app---visual-studio"></a>단일 파일 앱 게시 - Visual Studio

Visual Studio는 애플리케이션의 게시 방식을 제어하는 재사용 가능한 게시 프로필을 만듭니다.

01. **솔루션 탐색기** 창에서 게시할 프로젝트를 마우스 오른쪽 단추로 클릭합니다. **게시** 를 선택합니다.

    :::image type="content" source="media/single-file/visual-studio-solution-explorer.png" alt-text="오른쪽 클릭 메뉴에서 게시 옵션이 강조 표시된 솔루션 탐색기.":::

    기존 게시 프로필이 없는 경우 지침에 따라 게시 프로필을 만들고 **폴더** 대상 유형을 선택합니다.

01. **편집** 을 선택합니다.

    :::image type="content" source="media/single-file/visual-studio-publish-edit-settings.png" alt-text="편집 단추가 있는 Visual Studio 게시 프로필.":::

01. **프로필 설정** 대화 상자에서 다음 옵션을 설정합니다.

    - **배포 모드** 를 **자체 포함** 으로 설정합니다.
    - **대상 런타임** 을 게시할 플랫폼으로 설정합니다.
    - **단일 파일 생성** 을 선택합니다.

    **저장** 을 선택하여 설정을 저장하고 **게시** 대화 상자로 돌아갑니다.

    :::image type="content" source="media/single-file/visual-studio-publish-single-file-properties.png" alt-text="배포 모드, 대상 런타임, 단일 파일 옵션이 강조 표시된 프로필 설정 대화 상자":::

01. **게시** 를 선택하여 앱을 단일 파일로 게시합니다.

자세한 내용은 [Visual Studio를 사용하여 .NET Core 앱 게시](deploy-with-vs.md)를 참조하세요.

## <a name="publish-a-single-file-app---visual-studio-for-mac"></a>단일 파일 앱 게시 - Mac용 Visual Studio

Mac용 Visual Studio에서는 앱을 단일 파일로 게시하는 옵션을 제공하지 않습니다. [단일 파일 앱 게시 - CLI](#publish-a-single-file-app---cli) 섹션의 지침에 따라 수동으로 게시해야 합니다. 자세한 내용은 [.NET Core CLI를 사용하여 .NET Core 앱 게시](deploy-with-cli.md)를 참조하세요.

## <a name="see-also"></a>참조

- [.NET Core 애플리케이션 배포](index.md).
- [.NET Core CLI를 사용하여 .NET Core 앱 게시](deploy-with-cli.md).
- [Visual Studio를 사용하여 .NET Core 앱 게시](deploy-with-vs.md).
- [`dotnet publish` 명령](../tools/dotnet-publish.md)
