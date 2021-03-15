---
title: .NET의 코드 분석
titleSuffix: ''
description: .NET SDK의 소스 코드 분석에 대해 알아봅니다.
ms.date: 12/04/2020
ms.topic: overview
ms.custom: updateeachrelease
helpviewer_keywords:
- code analysis
- code analyzers
ms.openlocfilehash: 9fbeee7475b49a5b6514d4983142ae3be5a2f026
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102605297"
---
# <a name="overview-of-net-source-code-analysis"></a>.NET 소스 코드 분석 개요

.NET Compiler Platform(Roslyn) 분석기는 C# 또는 Visual Basic 코드를 검사하여 코드 품질 및 스타일 문제를 확인합니다. .NET 5.0부터는 Roslyn 분석기가 .NET SDK에 포함되므로 별도로 설치할 필요가 없습니다. 프로젝트가 .NET 5 이상을 대상으로 하는 경우 기본적으로 코드 분석이 사용하도록 설정되어 있습니다. 프로젝트가 .NET Core, .NET Standard 또는 .NET Framework 같은 다른 .NET 구현을 대상으로 하는 경우 [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) 속성을 `true`로 설정하여 코드 분석을 사용하도록 수동으로 설정해야 합니다.

.NET 5 이상 SDK로 이동하지 않거나, SDK 스타일이 아닌 .NET Framework 프로젝트를 사용하거나, NuGet 패키지 기반 모델을 선호하는 경우 [Microsoft.CodeAnalysis.NetAnalyzers NuGet 패키지](https://www.nuget.org/packages/Microsoft.CodeAnalysis.NetAnalyzers)에서도 분석기를 사용할 수 있습니다. 주문형 버전 업데이트에는 패키지 기반 모델을 사용하는 것이 좋습니다.

> [!NOTE]
> .NET 분석기는 대상 프레임워크에 독립적입니다. 즉, 프로젝트에서 특정 .NET 구현을 대상으로 지정하지 않아도 됩니다. 분석기는 이전 .NET 버전(예: `netcoreapp3.1` 및 `net472`)뿐만 아니라 `net5.0`을 대상으로 하는 프로젝트에서도 작동합니다. 그러나 [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) 속성을 사용하여 코드 분석을 사용하도록 설정하려면 프로젝트에서 [프로젝트 SDK](../../core/project-sdk/overview.md)를 참조해야 합니다.

분석기에서 규칙 위반이 발생하는 경우 각 규칙이 [구성](configuration-options.md)된 방법에 따라 제안, 경고, 오류로 보고됩니다. 코드 분석 위반은 컴파일러 오류와 구별하기 위해 “CA” 또는 “IDE” 접두사를 사용하여 표시됩니다.

## <a name="code-quality-analysis"></a>코드 품질 분석

‘코드 품질 분석’(“CAxxxx”) 규칙은 C# 또는 Visual Basic 코드를 검사하여 보안, 성능, 디자인, 기타 문제를 확인합니다. .NET 5.0 이상을 대상으로 하는 프로젝트의 경우 기본적으로 분석을 사용하도록 설정되어 있습니다. [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) 속성을 `true`로 설정하여 이전 버전의 .NET을 대상으로 하는 프로젝트에서 코드 분석을 사용하도록 설정할 수 있습니다. `EnableNETAnalyzers`를 `false`로 설정하여 프로젝트에서 코드 분석을 사용하지 않도록 설정할 수도 있습니다.

> [!TIP]
> Visual Studio를 사용하는 경우:
>
> - 여러 분석기 규칙에는 문제를 해결하는 데 적용할 수 있는 관련 ‘코드 수정 사항’이 있습니다. 코드 수정 사항은 전구 아이콘 메뉴에 표시됩니다.
> - 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성** > **코드 분석** 탭 > **.NET 분석기 사용** 을 선택하여 코드 분석을 사용하거나 사용하지 않도록 설정할 수 있습니다.

### <a name="enabled-rules"></a>사용 가능한 규칙

.NET 5.0에서는 기본적으로 다음 규칙이 사용하도록 설정됩니다.

| 진단 ID | 범주 | 심각도 | 설명 |
| - | - | - | - |
| [CA1416](/visualstudio/code-quality/ca1416) | 상호 운용성 | 경고 | 플랫폼 호환성 분석기 |
| [CA1417](/visualstudio/code-quality/ca1417) | 상호 운용성 | 경고 | P/Invokes에 대한 문자열 매개 변수에서 `OutAttribute`를 사용하지 않음 |
| [CA1831](/visualstudio/code-quality/ca1831) | 성능 | 경고 | 해당하는 경우 문자열에 범위 기반 인덱서 대신 `AsSpan` 사용 |
| [CA2013](/visualstudio/code-quality/ca2013) | 안정성 | 경고 | 값 형식에 `ReferenceEquals`를 사용하지 않음 |
| [CA2014](/visualstudio/code-quality/ca2014) | 안정성 | 경고 | 루프에서 `stackalloc`을 사용하지 않음 |
| [CA2015](/visualstudio/code-quality/ca2015) | 안정성 | 경고 | <xref:System.Buffers.MemoryManager%601>에서 파생된 형식에 대해 종료자를 정의하지 않음 |
| [CA2200](/visualstudio/code-quality/ca2200) | 사용량 | 경고 | 스택 정보를 유지하도록 다시 throw하십시오.
| [CA2247](/visualstudio/code-quality/ca2247) | 사용량 | 경고 | TaskCompletionSource 생성자에 전달되는 인수는 <xref:System.Threading.Tasks.TaskContinuationOptions>가 아닌 <xref:System.Threading.Tasks.TaskCreationOptions> 열거형이어야 함 |

이러한 규칙의 심각도를 변경하여 사용하지 않도록 설정하거나 오류로 수준을 올릴 수 있습니다. [더 많은 규칙을 사용하도록 설정](#enable-additional-rules)할 수도 있습니다.

- 각 .NET SDK 버전에 포함된 규칙 목록은 [분석기 릴리스](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md)를 참조하세요.
- 모든 코드 품질 규칙 목록은 [코드 품질 규칙](quality-rules/index.md)을 참조하세요.

### <a name="enable-additional-rules"></a>추가 규칙 사용

‘분석 모드’는 사용하도록 설정된 규칙이 없거나 일부 또는 모든 규칙이 사용하도록 설정된 미리 정의된 코드 분석 구성을 나타냅니다. 기본 분석 모드에서는 적은 수의 규칙만 [빌드 경고로 사용하도록 설정](#enabled-rules)됩니다. 프로젝트 파일에서 [\<AnalysisMode>](../../core/project-sdk/msbuild-props.md#analysismode) 속성을 설정하여 프로젝트의 분석 모드를 변경할 수 있습니다. 허용되는 값은 다음과 같습니다.

| 값 | 설명 |
| - | - |
| `AllDisabledByDefault` | 가장 보수적인 모드입니다. 기본적으로 모든 규칙이 사용하지 않도록 설정됩니다. 개별 규칙을 선택적으로 [옵트인](configuration-options.md)하여 사용하도록 설정할 수 있습니다.<br /><br />`<AnalysisMode>AllDisabledByDefault</AnalysisMode>` |
| `AllEnabledByDefault` | 가장 적극적인 모드입니다. 모든 규칙이 빌드 경고로 사용하도록 설정됩니다. 개별 규칙을 선택적으로 [옵트아웃](configuration-options.md)하여 사용하지 않도록 설정할 수 있습니다.<br /><br />`<AnalysisMode>AllEnabledByDefault</AnalysisMode>` |
| `Default` | 기본 모드로, 몇 가지 규칙은 경고로 사용하도록 설정되고 다른 규칙은 해당하는 코드 수정 사항이 있는 Visual Studio IDE 제안으로만 사용하도록 설정되며 나머지는 완전히 사용하지 않도록 설정됩니다. 개별 규칙을 선택적으로 [옵트인 또는 옵트아웃](configuration-options.md)하여 사용하지 않도록 설정할 수 있습니다.<br /><br />`<AnalysisMode>Default</AnalysisMode>` |

사용할 수 있는 각 규칙의 기본 심각도와 기본 분석 모드에서 규칙을 사용할 수 있는지를 확인하려면 [규칙 전체 목록](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md)을 참조하세요.

### <a name="treat-warnings-as-errors"></a>경고를 오류로 처리

프로젝트를 빌드할 때 `-warnaserror` 플래그를 사용하면 모든 코드 분석 경고도 오류로 처리됩니다. `-warnaserror`가 있을 경우 코드 품질 경고(CAxxxx)가 오류로 처리되지 않도록 하려면 프로젝트 파일에서 `CodeAnalysisTreatWarningsAsErrors` MSBuild 속성을 `false`로 설정할 수 있습니다.

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

코드 분석 경고는 계속 표시되지만 빌드를 중단하지는 않습니다.

### <a name="latest-updates"></a>최신 업데이트

기본적으로 최신 버전의 .NET SDK로 업그레이드하면 최신 코드 분석 규칙 및 기본 규칙 심각도가 제공됩니다. 새 규칙을 사용하거나 사용하지 않도록 설정하지 않으려는 경우처럼 이 동작을 원하지 않는 경우 다음 방법 중 하나를 사용하여 재정의할 수 있습니다.

- `AnalysisLevel` MSBuild 속성을 특정 값으로 설정하여 해당 집합에 대한 경고를 잠급니다. 최신 SDK로 업그레이드하는 경우 해당 경고에 대한 버그 수정이 계속 표시되지만 새 경고는 사용하도록 설정되지 않고 기존 경고는 사용하지 않도록 설정되지 않습니다. 예를 들어 규칙 세트를 .NET SDK 버전 5.0과 함께 제공되는 규칙으로 잠그려면 프로젝트 파일에 다음 항목을 추가합니다.

  ```xml
  <PropertyGroup>
    <AnalysisLevel>5.0</AnalysisLevel>
  </PropertyGroup>
  ```

  > [!TIP]
  > `AnalysisLevel` 속성의 기본값은 `latest`입니다. 즉, 최신 버전의 .NET SDK로 이동하면 항상 최신 코드 분석 규칙이 제공된다는 의미입니다.

  자세한 내용 및 가능한 값 목록은 [AnalysisLevel](../../core/project-sdk/msbuild-props.md#analysislevel)을 참조하세요.

- [Microsoft.CodeAnalysis.NetAnalyzers NuGet 패키지](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers)를 설치하여 .NET SDK 업데이트에서 규칙 업데이트를 분리합니다. .NET 5 이상을 대상으로 하는 프로젝트에서는 패키지를 설치하면 기본 제공 SDK 분석기가 꺼집니다. SDK에 NuGet 패키지 버전보다 최신인 분석기 어셈블리 버전이 포함되어 있으면 빌드 경고가 표시됩니다. 이 경고를 사용하지 않도록 설정하려면 `_SkipUpgradeNetAnalyzersNuGetWarning` 속성을 `true`로 설정합니다.

  > [!NOTE]
  > Microsoft.CodeAnalysis.NetAnalyzers NuGet 패키지를 설치하는 경우 [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) 속성을 프로젝트 파일이나 *Directory.Build.props* 파일에 추가하면 안 됩니다. NuGet 패키지를 설치하고 `EnableNETAnalyzers` 속성을 `true`로 설정하면 빌드 경고가 생성됩니다.

## <a name="code-style-analysis"></a>코드 스타일 분석

‘코드 스타일 분석’(“IDExxxx”) 규칙을 사용하면 코드베이스에서 일관된 코드 스타일을 정의하고 유지 관리할 수 있습니다. 기본 사용 설정은 다음과 같습니다.

- 명령줄 빌드: 코드 스타일 분석은 명령줄 빌드의 모든 .NET 프로젝트에 대해 기본적으로 사용하지 않도록 설정됩니다.

  .NET 5.0부터 명령줄 및 Visual Studio 내에서 [빌드에서 코드 스타일 분석을 사용하도록 설정](#enable-on-build)할 수 있습니다. 코드 스타일 위반은 “IDE” 접두사를 사용하는 경고 또는 오류로 표시됩니다. 이렇게 하면 빌드 시 일관된 코드 스타일을 적용할 수 있습니다.

- Visual Studio: 코드 스타일 분석은 기본적으로 Visual Studio 내의 모든 .NET 프로젝트에 대해 [코드 리팩터링 빠른 작업](/visualstudio/ide/code-generation-in-visual-studio)으로 사용하도록 설정됩니다.

코드 스타일 분석 규칙의 전체 목록은 [코드 스타일 규칙](style-rules/index.md)을 참조하세요.

### <a name="enable-on-build"></a>빌드 시 사용

.NET 5.0 SDK 이상 버전에서는 명령줄 및 Visual Studio에서 빌드할 때 코드 스타일 분석을 사용하도록 설정할 수 있습니다. 그러나 성능상의 이유로 [몇 가지 코드 스타일 규칙](https://github.com/dotnet/roslyn/blob/9f87b444da9c48a4d492b19f8337339056bf2b95/src/Analyzers/Core/Analyzers/EnforceOnBuildValues.cs#L95)은 Visual Studio IDE에서만 적용됩니다.

빌드 시 코드 스타일 분석을 사용하도록 설정하려면 다음 단계를 수행하세요.

1. MSBuild 속성 [EnforceCodeStyleInBuild](../../core/project-sdk/msbuild-props.md#enforcecodestyleinbuild)를 `true`로 설정합니다.

1. *.editorconfig* 파일에서 빌드 시 실행하려는 각 “IDE” 코드 스타일 규칙을 경고 또는 오류로 [구성](configuration-options.md)합니다. 예를 들면 다음과 같습니다.

   ```ini
   [*.{cs,vb}]
   # IDE0040: Accessibility modifiers required (escalated to a build warning)
   dotnet_diagnostic.IDE0040.severity = warning
   ```

   또는 기본적으로 전체 범주를 경고 또는 오류로 구성한 다음, 해당 범주에서 빌드 시 실행하지 않으려는 규칙을 선택적으로 해제할 수 있습니다. 예를 들면 다음과 같습니다.

   ```ini
   [*.{cs,vb}]

   # Default severity for analyzer diagnostics with category 'Style' (escalated to build warnings)
   dotnet_analyzer_diagnostic.category-Style.severity = warning

   # IDE0040: Accessibility modifiers required (disabled on build)
   dotnet_diagnostic.IDE0040.severity = silent
   ```

> [!NOTE]
> 코드 스타일 분석 기능은 시험용으로 제공되며 .NET 5 릴리스와 .NET 6 릴리스 사이에 변경될 수 있습니다.

## <a name="suppress-a-warning"></a>경고 표시 안 함

규칙 위반을 표시하지 않는 한 가지 방법은 EditorConfig 파일에서 해당 규칙 ID에 대한 심각도 옵션을 `none`으로 설정하는 것입니다. 예를 들면 다음과 같습니다.

```ini
dotnet_diagnostic.CA1822.severity = none
```

경고를 표시하지 않는 다른 방법 및 자세한 내용은 [코드 분석 경고를 표시하지 않는 방법](suppress-warnings.md)을 참조하세요.

## <a name="third-party-analyzers"></a>타사 분석기

공식 .NET 분석기 외에 [StyleCop](https://www.nuget.org/packages/StyleCop.Analyzers/), [Roslynator](https://www.nuget.org/packages/Roslynator.Analyzers/), [XUnit Analyzers](https://www.nuget.org/packages/xunit.analyzers/), [Sonar Analyzer](https://www.nuget.org/packages/SonarAnalyzer.CSharp/) 등의 타사 분석기도 설치할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [코드 품질 분석 규칙 참조](quality-rules/index.md)
- [코드 스타일 분석 규칙 참조](style-rules/index.md)
- [Visual Studio의 코드 분석](/visualstudio/code-quality/roslyn-analyzers-overview)
- [.NET Compiler Platform SDK](../../csharp/roslyn-sdk/index.md)
- [자습서: 첫 번째 분석기 및 코드 수정 작성](../../csharp/roslyn-sdk/tutorials/how-to-write-csharp-analyzer-code-fix.md)
