---
description: 언어 기능 규칙에 대한 C# 컴파일러 옵션입니다. 이러한 옵션은 컴파일러에서 특정 언어 구문을 해석하는 방법을 제어합니다.
title: C# 컴파일러 옵션 - 언어 기능 규칙
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- CheckForOverflowUnderflow compiler option [C#]
- AllowUnsafeBlocks compiler option [C#]
- DefineConstants compiler option [C#]
- LangVersion compiler option [C#]
- Nullable compiler option [C#]
ms.openlocfilehash: 7d1d00a52bd2ca1608d4059d7d217e763defa7b9
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103482448"
---
# <a name="c-compiler-options-for-language-feature-rules"></a>언어 기능 규칙에 대한 C# 컴파일러 옵션

다음 옵션은 컴파일러에서 언어 기능을 해석하는 방법을 제어합니다. 새 MSBuild 구문은 **굵게** 표시됩니다. 이전 *csc.exe* 구문은 `code style`에 표시됩니다.

- **CheckForOverflowUnderflow** / `-checked`: 오버플로 검사를 생성합니다.
- **AllowUnsafeBlocks** / `-unsafe`: '안전하지 않은' 코드를 허용합니다.
- **DefineConstants** / `-define`: 조건부 컴파일 기호를 정의합니다.
- **LangVersion** / `-langversion`: `default`(최신 주 버전) 또는 `latest`(부 버전을 포함한 최신 버전)와 같은 언어 버전을 지정합니다.
- **Null 허용** / `-nullable`: null 허용 컨텍스트 또는 null 허용 경고를 사용하도록 설정합니다.

## <a name="checkforoverflowunderflow"></a>CheckForOverflowUnderflow

**CheckForOverflowUnderflow** 옵션은 데이터 형식 범위를 벗어난 값을 생성하는 정수 산술 문으로 인해 런타임 예외가 발생하는지 여부를 지정합니다.  

```xml
<CheckForOverflowUnderflow>true</CheckForOverflowUnderflow>
```

`checked` 또는 `unchecked` 키워드 범위 내에 있는 정수 산술 문은 **CheckForOverflowUnderflow** 옵션의 영향을 받지 않습니다. `checked` 또는 `unchecked` 키워드의 범위에 없는 정수 산술 문으로 인해 데이터 형식 범위를 벗어난 값이 생성되고 **CheckForOverflowUnderflow** 가 `true`인 경우 해당 명령문은 런타임에 예외를 발생시킵니다. **CheckForOverflowUnderflow** 가 `false`이면 해당 명령문은 런타임에 예외를 발생시키지 않습니다. 이 옵션의 기본값은 `false`이며, 오버플로 검사는 해제되어 있습니다.

## <a name="allowunsafeblocks"></a>AllowUnsafeBlocks

**AllowUnsafeBlocks** 컴파일러 옵션을 사용하면 [unsafe](../keywords/unsafe.md) 키워드를 사용하는 코드를 컴파일할 수 있습니다. 이 옵션의 기본값은 `false`입니다. 즉, 안전하지 않은 코드는 허용되지 않습니다.

```xml
<AllowUnsafeBlocks>true</AllowUnsafeBlocks>
```

안전하지 않은 코드에 대한 자세한 내용은 [안전하지 않은 코드 및 포인터](../../programming-guide/unsafe-code-pointers/index.md)를 참조하세요.

## <a name="defineconstants"></a>DefineConstants

**DefineConstants** 옵션은 프로그램의 모든 소스 코드 파일에서 기호를 정의합니다.

```xml
<DefineConstants>name;name2</DefineConstants>
```

이 옵션은 정의하려는 하나 이상의 기호 이름을 지정합니다. **DefineConstants** 옵션은 컴파일러 옵션이 프로젝트의 모든 파일에 적용된다는 점을 제외하고는 [#define](../preprocessor-directives/preprocessor-define.md) 전처리기 지시문과 동일한 효과를 갖습니다. 소스 파일의 [#undef](../preprocessor-directives/preprocessor-undef.md) 지시문이 정의를 제거할 때까지 기호는 소스 파일에 정의된 상태로 유지됩니다. `-define` 옵션을 사용하는 경우 한 파일의 `#undef` 지시문이 프로젝트의 다른 소스 코드 파일에 영향을 주지 않습니다. 이 옵션으로 만든 기호를 [#if](../preprocessor-directives/preprocessor-if.md), [#else](../preprocessor-directives/preprocessor-else.md), [#elif](../preprocessor-directives/preprocessor-elif.md), [#endif](../preprocessor-directives/preprocessor-endif.md)와 함께 사용하면 소스 파일을 조건부 컴파일할 수 있습니다. C# 컴파일러 자체는 소스 코드에서 사용할 수 있는 기호 또는 매크로를 정의하지 않습니다. 모든 기호 정의는 사용자가 정의해야 합니다.

> [!NOTE]
> C# `#define` 지시문에서는 C++와 같은 언어에서처럼 기호에 값을 지정할 수 없습니다. 예를 들어 `#define`을 사용하여 매크로를 만들거나 상수를 정의할 수 없습니다. 상수를 정의해야 하는 경우 `enum` 변수를 사용합니다. C++ 스타일 매크로를 만들려는 경우 제네릭과 같은 다른 방식을 고려해 보세요. 매크로는 오류가 발생할 가능성이 크므로 C#에서는 매크로를 사용할 수 없으며 더 안전한 방식이 사용됩니다.

## <a name="langversion"></a>LangVersion

컴파일러가 선택한 C# 언어 사양에 포함된 구문만 허용하도록 합니다.

```xml
<LangVersion>9.0</LangVersion>
```

유효한 값은 다음과 같습니다.

[!INCLUDE [lang-versions-table](../includes/langversion-table.md)]

기본 언어 버전은 애플리케이션의 대상 프레임워크 및 SDK 또는 Visual Studio의 버전에 따라 다릅니다. 이러한 규칙은 [C# 언어 버전 관리](../configure-language-version.md#defaults)에 정의되어 있습니다.

C# 애플리케이션에서 참조된 메타데이터에는 **LangVersion** 컴파일러 옵션이 적용되지 않습니다.

각 C# 컴파일러 버전에 언어 사양의 확장이 포함되어 있으므로 **LangVersion** 은 이전 컴파일러 버전의 동등한 기능을 제공하지 않습니다.

또한 C# 버전 업데이트는 일반적으로 주 .NET Framework 릴리스와 일치하지만 새 구문과 기능이 반드시 특정 프레임워크 버전에 연결되지는 않습니다. 새로운 기능에는 C# 버전과 함께 릴리스된 새 컴파일러 업데이트가 분명히 필요하지만, 각 특정 기능에 고유한 최소 .NET API 또는 공용 언어 런타임 요구 사항이 있으므로 NuGet 패키지 또는 다른 라이브러리를 포함하여 하위 수준 프레임워크에서 실행이 허용될 수도 있습니다.

사용하는 **LangVersion** 설정과 관계없이 현재 버전의 공용 언어 런타임을 사용하여 고유한 .exe 또는 .dll을 만듭니다. 한 가지 예외는 **-langversion:ISO-1** 에서 작동하는 friend 어셈블리 및 [**ModuleAssemblyName**](advanced.md#moduleassemblyname)입니다.

C# 언어 버전을 지정하는 다른 방법은 [C# 언어 버전 관리](../configure-language-version.md)를 참조하세요.

이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>을 참조하십시오.

### <a name="c-language-specification"></a>C# 언어 사양

| 버전          | 링크                       | 설명                                                             |
|------------------|----------------------------|-------------------------------------------------------------------------|
| C# 7.0 이상 |                            | 현재 사용할 수 없음                                                 |
| C# 6.0           | [링크][csharp-6]           | C# 언어 사양 버전 6 - 비공식 초안: .NET Foundation |
| C# 5.0           | [PDF 다운로드][csharp-5]   | 표준 ECMA-334 다섯 번째 버전                                           |
| C# 3.0           | [DOC 다운로드][csharp-3]   | C# 언어 사양 버전 3.0: Microsoft Corporation            |
| C# 2.0           | [PDF 다운로드][csharp-2]   | 표준 ECMA-334 네 번째 버전                                           |
| C# 1.2           | [DOC 다운로드][csharp-1.2] | C# 언어 사양 버전 1.2: Microsoft Corporation            |
| C# 1.0           | [DOC 다운로드][csharp-1]   | C# 언어 사양 버전 1.0: Microsoft Corporation            |

[csharp-6]: /dotnet/csharp/language-reference/language-specification/introduction
[csharp-5]: https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf
[csharp-3]: https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc
[csharp-2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%204th%20edition%20June%202006.pdf
[csharp-1.2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%202nd%20edition%20December%202002.pdf
[csharp-1]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%201st%20edition%20December%202001.pdf

### <a name="minimum-sdk-version-needed-to-support-all-language-features"></a>모든 언어 기능을 지원하는 데 필요한 최소 SDK 버전

다음 표에서는 해당 언어 버전을 지원하는 C# 컴파일러가 포함된 SDK의 최소 버전을 보여줍니다.

| C# 버전 | 최소 SDK 버전                                                                  |
|------------|--------------------------------------------------------------------------------------|
| C# 8.0     | Microsoft Visual Studio/Build Tools 2019, 버전 16.3 또는 .NET Core 3.0 SDK         |
| C# 7.3     | Microsoft Visual Studio/Build Tools 2017 버전 15.7                               |
| C# 7.2     | Microsoft Visual Studio/Build Tools 2017 버전 15.5                               |
| C# 7.1     | Microsoft Visual Studio/Build Tools 2017 버전 15.3                               |
| C# 7.0     | Microsoft Visual Studio/Build Tools 2017                                             |
| C# 6       | Microsoft Visual Studio/Build Tools 2015                                             |
| C# 5       | Microsoft Visual Studio/Build Tools 2012 또는 번들 .NET Framework 4.5 컴파일러      |
| C# 4       | Microsoft Visual Studio/Build Tools 2010 또는 번들 .NET Framework 4.0 컴파일러      |
| C# 3       | Microsoft Visual Studio/Build Tools 2008 또는 번들 .NET Framework 3.5 컴파일러      |
| C# 2       | Microsoft Visual Studio/Build Tools 2005 또는 번들 .NET Framework 2.0 컴파일러      |
| C# 1.0/1.2 | Microsoft Visual Studio/Build Tools .NET 2002 또는 번들된 .NET Framework 1.0 컴파일러 |

## <a name="nullable"></a>Nullable

**Nullable** 옵션을 사용하면 null 허용 컨텍스트를 지정할 수 있습니다.

```xml
<Nullable>enable</Nullable>
```

인수는 `enable`, `disable`, `warnings` 또는 `annotations` 중 하나여야 합니다. `enable` 인수는 null 허용 컨텍스트를 사용하도록 설정합니다. `disable`을 지정하면 null 허용 컨텍스트가 비활성화됩니다. `warnings` 인수를 제공하면 null 허용 경고 컨텍스트가 활성화됩니다. `annotations` 인수를 지정하면 null 허용 주석 컨텍스트가 활성화됩니다.

흐름 분석은 실행 코드 내에서 변수의 Null 허용 여부를 유추하는 데 사용됩니다. 변수의 유추된 Null 허용 여부는 변수의 선언된 Null 허용 여부와 관계가 없습니다. 메서드 호출은 조건부로 생략된 경우에도 분석됩니다. 예를 들어 릴리스 모드의 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>입니다.

다음 특성으로 주석이 지정된 메서드를 호출하면 흐름 분석에도 영향을 줍니다.

- 간단한 사전 조건: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> 및 <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute>
- 간단한 사후 조건: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> 및 <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute>
- 조건부 사후 조건: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> 및 <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute>
- <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute>(예: <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>에 대한 `DoesNotReturnIf(false)`) 및 <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- 멤버 사후 조건: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> 및 <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])>

> [!IMPORTANT]
> 전역 null 허용 컨텍스트는 생성된 코드 파일에 적용되지 않습니다. 이 설정과 관계없이 null 허용 컨텍스트는 생성됨으로 표시된 모든 소스 파일에 대해 *disabled* 입니다. 다음 네 가지 방법으로 파일은 생성됨으로 표시됩니다.
>
> 1. .editorconfig에서 해당 파일에 적용되는 섹션에 `generated_code = true`를 지정합니다.
> 1. 파일의 맨 위에 있는 주석에 `<auto-generated>` 또는 `<auto-generated/>`를 배치합니다. 해당 주석의 모든 줄에 넣을 수 있지만 주석 블록은 파일의 첫 번째 요소여야 합니다.
> 1. 파일 이름을 *TemporaryGeneratedFile_* 로 시작합니다.
> 1. 파일 이름을 *.designer.cs*, *.generated.cs*, *.g.cs* 또는 *.g.i.cs* 로 종료합니다.
>
> 생성기는 [`#nullable`](../preprocessor-directives/preprocessor-nullable.md) 전처리기 지시문을 사용하여 옵트인할 수 있습니다.
