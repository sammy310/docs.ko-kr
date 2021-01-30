---
title: 코드 분석 규칙에 대 한 구성 파일
description: 코드 분석 규칙을 구성 하는 다양 한 구성 파일에 대해 알아봅니다.
ms.date: 09/24/2020
ms.topic: conceptual
no-loc:
- EditorConfig
ms.openlocfilehash: b98fdd48f2373bd23fcd3273834860a60c682969
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99216384"
---
# <a name="configuration-files-for-code-analysis-rules"></a>코드 분석 규칙에 대 한 구성 파일

코드 분석 규칙에는 다양 한 [구성 옵션이](configuration-options.md)있습니다. 이러한 옵션은 다음 분석기 구성 파일 중 하나에서 키-값 쌍으로 지정 합니다.

- [EditorConfig](#editorconfig) file: 파일 기반 또는 폴더 기반 구성 옵션입니다.
- [Global AnalyzerConfig](#global-analyzerconfig) File: 프로젝트 수준 구성 옵션입니다. 일부 프로젝트 파일이 프로젝트 폴더 외부에 상주 하는 경우에 유용 합니다.

## EditorConfig

[EditorConfig](/visualstudio/ide/create-portable-custom-editor-options) 파일은 **특정 원본 파일이 나 폴더에 적용 되는 옵션** 을 제공 하는 데 사용 됩니다. 옵션은 해당 하는 파일 및 폴더를 식별 하기 위해 섹션 헤더 아래에 배치 됩니다. 구성 하려는 각 규칙에 대 한 항목을 추가 하 고 해당 하는 파일 확장명 섹션 (예:)에 저장 `[*.cs]` 합니다.

```ini
[*.cs]
<option_name> = <option_value>
```

위의 예제에서 `[*.cs]` 는 `.cs` 하위 폴더를 비롯 하 여 현재 폴더 내에서 파일 확장명이 있는 모든 c # 파일을 선택 하는 editorconfig 섹션 헤더입니다. 이후 항목인은 `<option_name> = <option_value>` 모든 c # 파일에 적용 되는 분석기 옵션입니다.

파일을 EditorConfig 해당 디렉터리에 배치 하 여 폴더, 프로젝트 또는 전체 리포지토리에 파일 규칙을 적용할 수 있습니다. 이러한 옵션은 빌드 시 분석을 실행 하 고 Visual Studio에서 코드를 편집 하는 동안 적용 됩니다.

들여쓰기 크기 또는 후행 공백을 잘라낼 지 여부와 같은 편집기 설정에 대 한 기존 *editorconfig* 파일이 있는 경우 코드 분석 구성 옵션을 동일한 파일에 저장할 수 있습니다.

> [!TIP]
> Visual Studio에서는 이러한 파일 중 하나를 프로젝트에 쉽게 추가할 수 있는 *editorconfig* 항목 템플릿을 제공 합니다. 자세한 내용은 [ EditorConfig 프로젝트에 파일 추가](/visualstudio/ide/create-portable-custom-editor-options#add-an-editorconfig-file-to-a-project)를 참조 하세요.

### <a name="example"></a>예제

다음은 EditorConfig 옵션 및 규칙 심각도를 구성 하는 예제 파일입니다.

```ini
# Remove the line below if you want to inherit .editorconfig settings from higher directories
root = true

# C# files
[*.cs]

#### Core EditorConfig Options ####

# Indentation and spacing
indent_size = 4
indent_style = space
tab_width = 4

#### .NET Coding Conventions ####

# this. and Me. preferences
dotnet_style_qualification_for_method = true

#### Diagnostic configuration ####

# CA1000: Do not declare static members on generic types
dotnet_diagnostic.CA1000.severity = warning
```

## <a name="global-analyzerconfig"></a>글로벌 AnalyzerConfig

.NET 5 SDK (Visual Studio 2019 버전 16.8 이상에서 지원 됨)부터 전역 _AnalyzerConfig_ 파일을 사용 하 여 분석기 옵션을 구성할 수도 있습니다. 이러한 파일은 해당 파일 이름이 나 파일 경로에 관계 없이 **프로젝트의 모든 소스 파일에 적용 되는 옵션** 을 제공 하는 데 사용 됩니다.

[EditorConfig](#editorconfig)파일과 달리 전역 구성 파일은 들여쓰기 크기 또는 후행 공백을 잘라낼 지 여부와 같은 ide의 편집기 스타일 설정을 구성 하는 데 사용할 수 없습니다. 대신 프로젝트 수준 분석기 구성 옵션을 지정 하기 위한 용도로만 디자인 되었습니다.

### <a name="format"></a>서식

해당 하는 EditorConfig 파일 및 폴더를 식별 하기 위해와 같이 섹션 헤더를 포함 해야 하는 파일과 달리 `[*.cs]` global AnalyzerConfig 파일에는 섹션 머리글이 없습니다. 대신 `is_global = true` 일반 파일과 구분 하기 위해 양식의 최상위 항목이 필요 EditorConfig 합니다. 이는 파일의 모든 옵션이 전체 프로젝트에 적용 됨을 나타냅니다. 예를 들면 다음과 같습니다.

```ini
is_global = true
<option_name> = <option_value>
```

### <a name="naming"></a>이름 지정

명명 되어야 하는 파일의 경우와 달리 EditorConfig `.editorconfig` 전역 구성 파일에는 특정 이름 또는 확장명이 필요 하지 않습니다. 그러나 이러한 파일의 이름을로 지정할 경우 `.globalconfig` 하위 폴더를 포함 하 여 현재 폴더 내의 모든 c # 및 Visual Basic 프로젝트에 암시적으로 적용 됩니다. 그렇지 않은 경우 `GlobalAnalyzerConfigFiles` MSBuild 프로젝트 파일에 항목을 명시적으로 추가 해야 합니다.

```xml
<ItemGroup>
  <GlobalAnalyzerConfigFiles Include="<path_to_global_analyzer_config>" />
</ItemGroup>
```

> [!NOTE]
> 최상위 항목은 `is_global = true` 파일의 이름을 지정 하는 경우에도 필요 `.globalconfig` 합니다.

### <a name="example"></a>예제

다음은 프로젝트 수준에서 옵션 및 규칙 심각도를 구성 하는 예제 전역 AnalyzerConfig 파일입니다.

```ini
# Top level entry required to mark this as a global AnalyzerConfig file
is_global = true

# NOTE: No section headers for configuration entries

#### .NET Coding Conventions ####

# this. and Me. preferences
dotnet_style_qualification_for_method = true:warning

#### Diagnostic configuration ####

# CA1000: Do not declare static members on generic types
dotnet_diagnostic.CA1000.severity = warning
```

## <a name="precedence"></a>우선 순위

EditorConfig파일 및 전역 AnalyzerConfig 파일은 모두 각 옵션에 대 한 키-값 쌍을 지정 합니다. 키가 같지만 값이 다른 항목이 여러 개 있는 경우 충돌이 발생 합니다.

### <a name="general-options"></a>일반 옵션

옵션 간에 충돌이 발생할 경우 충돌을 해결 하는 데 다음과 같은 우선 순위 규칙이 사용 됩니다.

- 동일한 구성 파일의 일치 하는 항목: 파일에서 나중에 표시 되는 항목은 wins입니다. 단일 파일 내의 충돌 하는 항목과 EditorConfig 단일 전역 AnalyzerConfig 파일 내에 있는 경우에도 마찬가지입니다.

- 두 파일에서 충돌 하 EditorConfig 는 항목: 파일 시스템에서 더 심층적 파일의 항목으로 EditorConfig , 파일 경로가 더 긴 경우 wins.

- 두 전역 AnalyzerConfig 파일의 충돌 항목: 컴파일러 경고가 보고 되 고 두 항목이 모두 무시 됩니다.

- EditorConfig파일 및 전역 AnalyzerConfig 파일에서 충돌 하는 항목: 파일의 항목은 EditorConfig wins입니다.

### <a name="severity-options"></a>심각도 옵션

이전 [일반 우선 순위 규칙](#general-options) 은 구성 파일에 지정 된 모든 옵션에 적용 됩니다. [심각도 구성](configuration-options.md#severity-level) 옵션의 경우 다음과 같은 추가 선행 규칙을 적용 합니다.

- 컴파일러 옵션 (또는)으로 명령줄에서 지정 된 심각도 옵션은 `/nowarn` `/warnaserror` 항상 및 전역 AnalyzerConfig 파일에 지정 된 [심각도 구성](configuration-options.md#severity-level) 옵션을 재정의 EditorConfig 합니다.

- 심각도 옵션은 [규칙 집합](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) 파일을 사용 하 여 지정할 수도 있습니다. 그러나 및 전역 AnalyzerConfig 파일의 경우에는 규칙 집합 파일이 더 이상 사용 되지 않습니다 EditorConfig . [규칙 집합 파일을 해당 EditorConfig 파일로 변환](/visualstudio/code-quality/use-roslyn-analyzers#convert-an-existing-ruleset-file-to-editorconfig-file)하는 것이 좋습니다. 규칙 집합 파일 및 또는 전역 AnalyzerConfig 파일에서 충돌 하는 심각도 항목에 대 한 우선 순위 EditorConfig 는 _정의_ 되지 않습니다.

- 서로 다른 키를 사용 하는 관련 심각도 옵션의 우선 순위 규칙에 대 한 자세한 내용은 (예: 단일 규칙에 대해 서로 다른 심각도가 지정 된 경우 및 해당 규칙이 적용 되는 범주) [코드 분석 구성 옵션](configuration-options.md#precedence)을 참조 하세요.

## <a name="see-also"></a>참고 항목

- [EditorConfig vs global AnalyzerConfig 디자인 문제](https://github.com/dotnet/roslyn/issues/47707)
