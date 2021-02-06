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
ms.openlocfilehash: 2cda5a23bbc90ca5dc2305b5d7023e8ea6120b79
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643074"
---
# <a name="overview-of-net-source-code-analysis"></a>.NET 소스 코드 분석 개요

.NET 컴파일러 플랫폼(Roslyn) 분석기는 C# 또는 Visual Basic 코드를 검사하여 코드 품질 및 코드 스타일 문제를 확인합니다. .NET 5.0부터 이러한 분석기는 .NET SDK에 포함 되어 있으므로 별도로 설치할 필요가 없습니다. 프로젝트가 .NET 5 이상을 대상으로 하는 경우 기본적으로 코드 분석이 사용 됩니다. 프로젝트가 .NET Core, .NET Standard 또는 .NET Framework 같은 다른 .NET 구현을 대상으로 하는 경우 [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) 속성을로 설정 하 여 코드 분석을 수동으로 사용 하도록 설정 해야 합니다 `true` .

.NET 5 + SDK로 이동 하지 않거나 NuGet 패키지 기반 모델을 선호 하는 경우에는 [Microsoft CodeAnalysis. Netanalyzers NuGet 패키지](https://www.nuget.org/packages/Microsoft.CodeAnalysis.NetAnalyzers)에서도 분석기를 사용할 수 있습니다. 주문형 버전 업데이트에 대 한 패키지 기반 모델을 사용 하는 것이 좋습니다.

> [!NOTE]
> .NET 분석기는 대상 프레임 워크에 독립적입니다. 즉, 프로젝트에서 특정 .NET 구현을 대상으로 하지 않아도 됩니다. 분석기는 및와 같은 이전 버전의 .NET을 대상으로 하는 프로젝트에 대해서도 작동 합니다 `net5.0` `netcoreapp3.1` `net472` .

분석기에서 규칙 위반을 발견 하는 경우 각 규칙의 [구성](configuration-options.md)방법에 따라 제안, 경고 또는 오류로 보고 됩니다. 코드 분석 위반은 컴파일러 오류와 구별 하기 위해 접두사 "CA" 또는 "IDE"와 함께 표시 됩니다.

## <a name="code-quality-analysis"></a>코드 품질 분석

*코드 품질 분석* ("caxxxx") 규칙은 c # 또는 Visual Basic 코드에서 보안, 성능, 디자인 및 기타 문제를 검사 합니다. 분석은 기본적으로 .NET 5.0 이상을 대상으로 하는 프로젝트에 대해 사용 하도록 설정 됩니다. [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) 속성을로 설정 하 여 이전 .net 버전을 대상으로 하는 프로젝트에 대해 코드 분석을 사용 하도록 설정할 수 있습니다 `true` . 을로 설정 하 여 프로젝트에 대 한 코드 분석을 사용 하지 않도록 설정할 수도 있습니다 `EnableNETAnalyzers` `false` .

> [!TIP]
> Visual Studio를 사용하는 경우:
>
> - 많은 분석기 규칙에는 문제를 해결 하기 위해 적용할 수 있는 *코드 수정* 이 연결 되어 있습니다. 코드 수정이 전구 아이콘 메뉴에 표시 됩니다.
> - 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **속성**  >  **코드 분석** 탭 > **.net 분석기 사용** 을 선택 하 여 코드 분석을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.

### <a name="enabled-rules"></a>활성화 된 규칙

다음 규칙은 기본적으로 .NET 5.0에서 사용 하도록 설정 됩니다.

| 진단 ID | 범주 | 심각도 | 설명 |
| - | - | - | - |
| [CA1416](/visualstudio/code-quality/ca1416) | 상호 운용성 | 경고 | 플랫폼 호환성 분석기 |
| [CA1417](/visualstudio/code-quality/ca1417) | 상호 운용성 | 경고 | `OutAttribute`P/invoke에 문자열 매개 변수를 사용 하지 마십시오. |
| [CA1831](/visualstudio/code-quality/ca1831) | 성능 | 경고 | `AsSpan`적절 한 경우 문자열에 범위 기반 인덱서 대신을 사용 합니다. |
| [CA2013](/visualstudio/code-quality/ca2013) | 안정성 | 경고 | 값 형식과 함께 사용 하지 마십시오. `ReferenceEquals` |
| [CA2014](/visualstudio/code-quality/ca2014) | 안정성 | 경고 | 루프에 사용 하지 마십시오. `stackalloc` |
| [CA2015](/visualstudio/code-quality/ca2015) | 안정성 | 경고 | 에서 파생 된 형식에 대해 종료자를 정의 하지 마십시오. <xref:System.Buffers.MemoryManager%601> |
| [CA2200](/visualstudio/code-quality/ca2200) | 사용량 | 경고 | 스택 정보를 유지하도록 다시 throw하십시오.
| [CA2247](/visualstudio/code-quality/ca2247) | 사용량 | 경고 | TaskCompletionSource 생성자에 전달 된 인수는 <xref:System.Threading.Tasks.TaskCreationOptions> 대신 열거형 이어야 합니다. <xref:System.Threading.Tasks.TaskContinuationOptions> |

이러한 규칙의 심각도를 변경 하 여 사용 하지 않도록 설정 하거나 오류를 상승 시킬 수 있습니다. [추가 규칙을 사용 하도록 설정할](#enable-additional-rules)수도 있습니다.

- 각 .NET SDK 버전에 포함 된 규칙 목록은 [Analyzer 릴리스](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md)를 참조 하세요.
- 모든 코드 품질 규칙의 목록은 [코드 품질 규칙](quality-rules/index.md)을 참조 하세요.

### <a name="enable-additional-rules"></a>추가 규칙 사용

*분석 모드* 는 none, some 또는 all 규칙이 설정 된 미리 정의 된 코드 분석 구성을 나타냅니다. 기본 분석 모드에서는 적은 수의 규칙만 [빌드 경고로 설정](#enabled-rules)됩니다. 프로젝트 파일에서 [AnalysisMode](../../core/project-sdk/msbuild-props.md#analysismode) 속성을 설정 하 여 프로젝트에 대 한 분석 모드를 변경할 수 있습니다. 허용 되는 값은 다음과 같습니다.

| 값 | 설명 |
| - | - |
| `AllDisabledByDefault` | 이는 가장 보수적인 모드입니다. 모든 규칙은 기본적으로 사용 하지 않도록 설정 됩니다. 개별 규칙을 선택적으로 [옵트인](configuration-options.md)하여 사용하도록 설정할 수 있습니다.<br /><br />`<AnalysisMode>AllDisabledByDefault</AnalysisMode>` |
| `AllEnabledByDefault` | 이는 가장 적극적인 모드입니다. 모든 규칙은 빌드 경고로 설정 됩니다. 개별적으로 사용 하지 않도록 설정 하는 규칙을 선택적으로 [옵트아웃 (opt out](configuration-options.md) ) 할 수 있습니다.<br /><br />`<AnalysisMode>AllEnabledByDefault</AnalysisMode>` |
| `Default` | 기본 모드에서는 몇 가지 규칙을 경고로 사용 하 고, 다른 규칙은 해당 코드 수정이 있는 Visual Studio IDE 제안 으로만 활성화 되며, 나머지는 완전히 사용 하지 않도록 설정 됩니다. 개별 규칙을 선택적 [으로 옵트인 또는 옵트아웃](configuration-options.md) 하 여 사용 하지 않도록 설정할 수 있습니다.<br /><br />`<AnalysisMode>Default</AnalysisMode>` |

사용할 수 있는 각 규칙의 기본 심각도와 규칙을 기본 분석 모드에서 사용할 수 있는지 여부를 확인 하려면 [규칙의 전체 목록을](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md)참조 하세요.

### <a name="treat-warnings-as-errors"></a>경고를 오류로 처리

프로젝트를 빌드할 때 플래그를 사용 하는 경우 `-warnaserror` 모든 코드 분석 경고도 오류로 처리 됩니다. CAxxxx (코드 품질 경고)를의 오류로 처리 하지 않으려는 경우 `-warnaserror` `CodeAnalysisTreatWarningsAsErrors` 프로젝트 파일에서 MSBuild 속성을로 설정할 수 있습니다 `false` .

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

코드 분석 경고가 계속 표시 되지만 빌드를 중단 하지는 않습니다.

### <a name="latest-updates"></a>최신 업데이트

최신 버전의 .NET SDK로 업그레이드 하는 경우 기본적으로 최신 코드 분석 규칙 및 기본 규칙 심각도가 제공 됩니다. 이 동작을 원하지 않는 경우, 예를 들어 새 규칙을 사용 하거나 사용 하지 않도록 설정 하려는 경우 다음 방법 중 하나를 사용 하 여 재정의할 수 있습니다.

- `AnalysisLevel`MSBuild 속성을 특정 값으로 설정 하 여 해당 집합에 대 한 경고를 잠급니다. 최신 SDK로 업그레이드 하는 경우 해당 경고에 대 한 버그 수정이 계속 표시 되지만 새 경고는 사용할 수 없으며, 기존 경고는 사용 하지 않도록 설정 됩니다. 예를 들어 .NET SDK 버전 5.0와 함께 제공 되는 규칙 집합을 잠그려면 프로젝트 파일에 다음 항목을 추가 합니다.

  ```xml
  <PropertyGroup>
    <AnalysisLevel>5.0</AnalysisLevel>
  </PropertyGroup>
  ```

  > [!TIP]
  > 속성의 기본값은 `AnalysisLevel` 입니다 `latest` . 즉, 최신 버전의 .net SDK로 이동할 때 항상 최신 코드 분석 규칙을 가져옵니다.

  자세한 내용 및 가능한 값 목록을 보려면 [AnalysisLevel](../../core/project-sdk/msbuild-props.md#analysislevel)를 참조 하세요.

- [Microsoft CodeAnalysis NuGet 패키지](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) 를 설치 하 여 .net SDK 업데이트에서 규칙 업데이트를 분리 합니다. 패키지를 설치 하면 기본 제공 SDK 분석기가 해제 되 고 SDK에 NuGet 패키지의 최신 분석기 어셈블리 버전이 포함 되어 있으면 빌드 경고가 생성 됩니다.

## <a name="code-style-analysis"></a>코드 스타일 분석

*코드 스타일 분석* ("IDExxxx") 규칙을 사용 하 여 코드 베이스에서 일관 된 코드 스타일을 정의 하 고 유지할 수 있습니다. 기본 설정 설정은 다음과 같습니다.

- 명령줄 빌드: 코드 스타일 분석은 기본적으로 명령줄 빌드의 모든 .NET 프로젝트에 대해 사용 하지 않도록 설정 됩니다.

  .NET 5.0부터 명령줄 및 Visual Studio 내에서 [빌드에 대 한 코드 스타일 분석을 사용 하도록 설정할](#enable-on-build)수 있습니다. 코드 스타일 위반은 "IDE" 접두사를 사용 하 여 경고나 오류로 표시 됩니다. 이렇게 하면 빌드 시 일관 된 코드 스타일을 적용할 수 있습니다.

- Visual Studio: 코드 스타일 분석은 기본적으로 Visual Studio 내의 모든 .NET 프로젝트에 대해 [코드 리팩터링 빠른 작업](/visualstudio/ide/code-generation-in-visual-studio)으로 사용 됩니다.

코드 스타일 분석 규칙의 전체 목록은 [코드 스타일 규칙](style-rules/index.md)을 참조 하세요.

### <a name="enable-on-build"></a>빌드 시 사용

.NET 5.0 SDK 이상 버전을 사용 하 여 명령줄 및 Visual Studio에서 빌드할 때 코드 스타일 분석을 사용 하도록 설정할 수 있습니다. 그러나 성능상의 이유로 [몇 가지 코드 스타일 규칙](https://github.com/dotnet/roslyn/blob/9f87b444da9c48a4d492b19f8337339056bf2b95/src/Analyzers/Core/Analyzers/EnforceOnBuildValues.cs#L95) 은 VISUAL Studio IDE에만 적용 됩니다.

빌드에서 코드 스타일 분석을 사용 하도록 설정 하려면 다음 단계를 따르세요.

1. MSBuild 속성 [EnforceCodeStyleInBuild](../../core/project-sdk/msbuild-props.md#enforcecodestyleinbuild) 을로 설정 `true` 합니다.

1. *Editorconfig* 파일에서 빌드에서 실행 하려는 각 "IDE" 코드 스타일 규칙을 경고나 오류로 [구성](configuration-options.md) 합니다. 다음은 그 예입니다. 

   ```ini
   [*.{cs,vb}]
   # IDE0040: Accessibility modifiers required (escalated to a build warning)
   dotnet_diagnostic.IDE0040.severity = warning
   ```

   또는 전체 범주를 경고나 오류로 구성 하 고, 기본적으로이 범주에서 규칙을 선택적으로 해제 한 후에 빌드 시 실행 하지 않을 수 있습니다. 다음은 그 예입니다. 

   ```ini
   [*.{cs,vb}]

   # Default severity for analyzer diagnostics with category 'Style' (escalated to build warnings)
   dotnet_analyzer_diagnostic.category-Style.severity = warning

   # IDE0040: Accessibility modifiers required (disabled on build)
   dotnet_diagnostic.IDE0040.severity = silent
   ```

> [!NOTE]
> 코드 스타일 분석 기능은 실험적 이며 .NET 5와 .NET 6 릴리스 사이에서 변경 될 수 있습니다.

## <a name="suppress-a-warning"></a>경고 표시 안 함

규칙 위반을 억제 하는 한 가지 방법은 EditorConfig 파일에서 해당 규칙 ID에 대 한 심각도 옵션을로 설정 하는 것입니다 `none` . 다음은 그 예입니다. 

```ini
dotnet_diagnostic.CA1822.severity = none
```

경고를 표시 하지 않는 다른 방법 및 자세한 내용은 [코드 분석 경고를 표시 하지 않는 방법](suppress-warnings.md)을 참조 하세요.

## <a name="third-party-analyzers"></a>타사 분석기

공식 .NET 분석기 외에도 [StyleCop,](https://www.nuget.org/packages/StyleCop.Analyzers/) [rosl](https://www.nuget.org/packages/Roslynator.Analyzers/), [Xunit 분석기](https://www.nuget.org/packages/xunit.analyzers/)및 [sonar.projectname) Analyzer](https://www.nuget.org/packages/SonarAnalyzer.CSharp/)와 같은 타사 분석기를 설치할 수도 있습니다.

## <a name="see-also"></a>참고 항목

- [코드 품질 분석 규칙 참조](quality-rules/index.md)
- [코드 스타일 분석 규칙 참조](style-rules/index.md)
- [Visual Studio의 코드 분석](/visualstudio/code-quality/roslyn-analyzers-overview)
- [.NET Compiler Platform SDK](../../csharp/roslyn-sdk/index.md)
- [자습서: 첫 번째 분석기 및 코드 수정 작성](../../csharp/roslyn-sdk/tutorials/how-to-write-csharp-analyzer-code-fix.md)
