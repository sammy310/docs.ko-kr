---
title: C# 언어 버전 관리 - C# 가이드
description: C# 언어 버전은 프로젝트에 따라 결정된다는 사실과 그 이유를 알아봅니다. 기본값을 수동으로 재정의하는 방법을 알아봅니다.
ms.custom: updateeachrelease
ms.date: 08/11/2020
ms.openlocfilehash: a06aa8812dad6f4b9a9254eef9f7c678c22af860
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634513"
---
# <a name="c-language-versioning"></a>C# 언어 버전 관리

최신 C# 컴파일러는 프로젝트의 대상 프레임워크를 기반으로 기본 언어 버전을 결정합니다. Visual Studio는 이 값을 변경하는 UI를 제공하지 않지만, *csproj* 파일을 편집하여 값을 변경할 수 있습니다. 기본값이 이렇게 선택되면 항상 대상 프레임워크와 호환되는 최신 언어 버전을 사용할 수 있게 됩니다. 프로젝트의 대상과 호환되는 최신 언어 기능을 이용할 수 있다는 이점이 있습니다. 또한, 기본값이 이렇게 선택되면 대상 프레임워크에서 사용할 수 없는 형식이나 런타임 동작이 필요한 언어를 사용하지 않을 수 있습니다. 기본값보다 최신의 언어 버전을 선택할 경우 컴파일 시간 및 런타임 오류를 진단하기 어려워질 수 있습니다.

이 문서의 규칙은 Visual Studio 2019 또는 .NET SDK와 함께 제공되는 컴파일러에 적용됩니다. Visual Studio 2017 설치 또는 이전 .NET Core SDK 버전의 일부인 C# 컴파일러는 기본적으로 C# 7.0을 대상으로 합니다.

C# 8.0은 .NET Core 3.x 이상 버전에서만 지원됩니다. 대부분의 최신 기능에는 .NET Core 3.x에서 도입된 라이브러리 및 런타임 기능이 필요합니다.

- [기본 인터페이스 구현](../whats-new/csharp-8.md#default-interface-methods)에는 .NET Core 3.0 CLR의 새로운 기능이 필요합니다.
- [비동기 스트림](../whats-new/csharp-8.md#asynchronous-streams)에는 새로운 형식인 <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType> 및 <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>이 필요합니다.
- [인덱스 및 범위](../whats-new/csharp-8.md#indices-and-ranges)에는 새로운 형식인 <xref:System.Index?displayProperty=nameWithType> 및 <xref:System.Range?displayProperty=nameWithType>이 필요합니다.
- [Nulle 허용 참조 형식](../whats-new/csharp-8.md#nullable-reference-types)은 더 효과적인 경고를 제공하기 위해 몇 가지 [특성](attributes/nullable-analysis.md)을 사용하는데, 이러한 특성은 .NET Core 3.0에서 추가되었습니다. 다른 대상 프레임워크는 이러한 특성으로 주석이 추가되지 않았습니다. 즉, null 허용 경고가 잠재적인 문제를 정확하게 반영하지 못할 수 있습니다.

C# 9.0은 .NET 5 이상 버전에서만 지원됩니다.

## <a name="defaults"></a>기본값

컴파일러는 다음 규칙에 따라 기본값을 결정합니다.

| 대상 프레임워크 | 버전 | C# 언어 버전 기본값 |
|------------------|---------|-----------------------------|
| .NET             | 5.x     | C# 9.0                      |
| .NET Core        | 3.x     | C# 8.0                      |
| .NET Core        | 2.x     | C# 7.3                      |
| .NET Standard    | 2.1     | C# 8.0                      |
| .NET Standard    | 2.0     | C# 7.3                      |
| .NET Standard    | 1.x     | C# 7.3                      |
| .NET Framework   | 모두     | C# 7.3                      |

프로젝트가 해당 미리 보기 언어 버전이 있는 미리 보기 프레임워크를 대상으로 하는 경우 사용되는 언어 버전은 미리 보기 언어 버전입니다. 따라서 릴리스된 .NET Core 버전을 대상으로 하는 프로젝트에 영향을 주지 않으면서 모든 환경에서 해당 미리 보기의 최신 기능을 사용할 수 있습니다.

> [!TIP]
> 현재 사용 중인 언어 버전을 확인하려면 코드에 `#error version`(대/소문자 구분)을 입력합니다. 이렇게 하면 컴파일러가 사용 중인 컴파일러 버전 및 현재 선택된 언어 버전을 포함하는 메시지가 있는 진단 CS8304를 생성합니다.

## <a name="override-a-default"></a>기본값 재정의

C# 버전을 명시적으로 지정해야 하는 경우 다음과 같은 여러 가지 방법으로 수행할 수 있습니다.

- [프로젝트 파일](#edit-the-project-file)을 수동으로 편집합니다.
- [하위 디렉터리에 있는 여러 프로젝트의](#configure-multiple-projects) 언어 버전을 설정합니다.
- [`-langversion` 컴파일러 옵션](compiler-options/langversion-compiler-option.md)을 구성합니다.

### <a name="edit-the-project-file"></a>프로젝트 파일 편집

프로젝트 파일에서 언어 버전을 설정할 수 있습니다. 예를 들어 미리 보기 기능에 명시적으로 액세스하려는 경우 다음과 같은 요소를 추가합니다.

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

값 `preview`는 컴파일러에서 지원하는 사용 가능한 최신 미리 보기 C# 언어를 사용합니다.

### <a name="configure-multiple-projects"></a>여러 프로젝트 구성

여러 프로젝트를 구성하려면 `<LangVersion>` 요소를 포함하는 **Directory.Build.props** 파일을 만들 수 있습니다. 일반적으로 솔루션 디렉터리에서 이 작업을 수행합니다. 솔루션 디렉터리의 **Directory.Build.props** 파일에 다음을 추가합니다.

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

해당 파일을 포함하는 디렉터리의 모든 하위 디렉터리에 있는 빌드는 미리 보기 C# 버전을 사용합니다. 자세한 내용은 [빌드 사용자 지정](/visualstudio/msbuild/customize-your-build)에 대한 문서를 참조하세요.

## <a name="c-language-version-reference"></a>C# 언어 버전 참조

모든 표는 현재 C# 언어 버전을 보여줍니다. 컴파일러가 오래된 것이라면 일부 값을 파악하지 못할 수 있습니다. 최신 .NET SDK를 설치하는 경우 나열된 모든 항목에 액세스할 수 있습니다.

[!INCLUDE [langversion-table](includes/langversion-table.md)]

> [!TIP]
> [Visual Studio용 개발자 명령 프롬프트](../../framework/tools/developer-command-prompt-for-vs.md)를 열고 다음 명령을 실행하여 컴퓨터에서 사용할 수 있는 언어 버전의 목록을 확인합니다.
>
> ```CMD
> csc -langversion:?
> ```
>
> 이와 같이 [-langversion](compiler-options/langversion-compiler-option.md) compile 옵션을 질문하면 다음과 같은 내용이 출력됩니다.
>
> ```CMD
> Supported language versions:
> default
> 1
> 2
> 3
> 4
> 5
> 6
> 7.0
> 7.1
> 7.2
> 7.3
> 8.0
> 9.0 (default)
> latestmajor
> preview
> latest
> ```
