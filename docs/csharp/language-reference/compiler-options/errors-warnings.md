---
description: 오류 및 경고에 대한 C# 컴파일러 옵션입니다. 이러한 옵션은 경고를 억제하거나 사용하도록 설정하고 경고를 오류로 제어합니다.
title: C# 컴파일러 옵션 - 오류 및 경고
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- WarningLevel compiler option [C#]
- TreatWarningsAsErrors compiler option [C#]
- WarningsAsErrors compiler option [C#]
- WarningsNotAsErrors compiler option [C#]
- DisabledWarnings compiler option [C#]
- CodeAnalysisRuleSet compiler option [C#]
- ErrorLog compiler option [C#]
- ReportAnalyzer compiler option [C#]
ms.openlocfilehash: 2bdda13d6b8b2b75d80c228da678a5b7fbcb8892
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103482497"
---
# <a name="c-compiler-options-to-report-errors-and-warnings"></a>오류 및 경고를 보고하는 C# 컴파일러 옵션

다음 옵션은 컴파일러가 오류 및 경고를 보고하는 방법을 제어합니다. 새 MSBuild 구문은 **굵게** 표시됩니다. 이전 *csc.exe* 구문은 `code style`에 표시됩니다.

- **WarningLevel** / `-warn`: 경고 수준을 설정합니다.
- **TreatWarningsAsErrors** / `-warnaserror`: 모든 경고를 오류로 처리
- **WarningsAsErrors** / `-warnaserror`: 하나 이상의 경고를 오류로 처리
- **WarningsNotAsErrors** / `-warnaserror`: 하나 이상의 경고를 오류로 처리하지 않음
- **DisabledWarnings** / `-nowarn`: 비활성화된 경고 목록을 설정합니다.
- **CodeAnalysisRuleSet** / `-ruleset`: 특정 진단을 비활성화하는 규칙 집합 파일을 지정합니다.
- **ErrorLog** / `-errorlog`: 모든 컴파일러와 분석기 진단을 로그할 파일을 지정합니다.
- **ReportAnalyzer** / `-reportanalyzer`: 실행 시간과 같은 추가 분석기 정보를 보고합니다.

## <a name="warninglevel"></a>WarningLevel

**WarningLevel** 옵션은 컴파일러에서 표시할 경고 수준을 지정합니다.

```xml
<WarningLevel>3</WarningLevel>
```

요소 값은 컴파일에 대해 표시할 경고 수준입니다. 숫자가 낮을수록 높은 심각도 경고만 표시됩니다. 숫자가 높을수록 더 많은 경고가 표시됩니다. 값은 0 또는 양의 정수여야 합니다.

|경고 수준|의미|
|-------------------|-------------|
|0|모든 경고 메시지 내보내기를 끕니다.|
|1|심각한 경고 메시지를 표시합니다.|  
|2|수준 1 경고와 덜 심각한 특정 경고(예: 클래스 멤버 숨기기에 대한 경고)를 표시합니다.|
|3|수준 2 경고와 덜 심각한 특정 경고(예: 항상 `true` 또는 `false`로 평가되는 식에 대한 경고)를 표시합니다.|
|4(기본값)|모든 수준 3 경고와 정보 경고를 표시합니다.|
|5|수준 4 경고와 함께 C# 9.0에 제공된 컴파일러의 [추가 경고](https://github.com/dotnet/roslyn/blob/a6013f3213c902c0973b2d371c3007217d610533/docs/compilers/CSharp/Warnversion%20Warning%20Waves.md)를 표시합니다.|
|5보다 큼|5보다 큰 값은 5로 처리됩니다. 컴파일러가 새 경고 수준으로 업데이트된 경우 항상 모든 경고가 표시되도록 하려면 임의의 큰 값(예: `9999`)을 입력합니다.

오류 또는 경고에 대한 정보를 가져오려면 도움말 색인에서 오류 코드를 조회할 수 있습니다. 오류 또는 경고에 대한 정보를 가져오는 다른 방법은 [C# 컴파일러 오류](../compiler-messages/index.md)를 참조하세요. [**TreatWarningsAsErrors**](#treatwarningsaserrors)를 사용하여 모든 경고를 오류로 처리합니다. [**DisabledWarnings**](#disabledwarnings)를 사용하여 특정 경고를 비활성화합니다.  

## <a name="treatwarningsaserrors"></a>TreatWarningsAsErrors

**TreatWarningsAsErrors** 옵션은 모든 경고를 오류로 처리합니다. **TreatWarningsAsErrors** 를 사용하여 일부 경고만 오류로 설정할 수도 있습니다. **TreatWarningsAsErrors** 를 설정한 경우 **TreatWarningsAsErrors** 를 사용하여 오류로 처리하면 안 되는 경고를 나열할 수 있습니다.

```xml
<TreatWarningsAsErrors></TreatWarningsAsErrors>
```

대신 모든 경고 메시지가 오류로 보고됩니다. 빌드 프로세스가 중단됩니다(출력 파일이 빌드되지 않음). 기본적으로 **TreatWarningsAsErrors** 는 적용되지 않습니다. 즉, 경고가 출력 파일을 생성하지 못합니다. 필요에 따라 몇 개의 특정 경고만 오류로 처리하려는 경우 오류로 처리할 경고 번호의 쉼표로 구분된 목록을 지정할 수 있습니다. 모든 Null 허용 여부 경고 집합은 [**Null 허용**](language.md#nullable) 축약형을 사용하여 지정할 수 있습니다. [**WarningLevel**](#warninglevel)을 사용하여 컴파일러에서 표시할 경고 수준을 지정합니다. [**DisabledWarnings**](#disabledwarnings)를 사용하여 특정 경고를 비활성화합니다.

## <a name="warningsaserrors-and-warningsnotaserrors"></a>WarningsAsErrors 및 WarningsNotAsErrors

**WarningsAsErrors** 및 **WarningsNotAsErrors** 옵션은 경고 목록에 대해 **TreatWarningsAsErrors** 옵션을 재정의합니다.

경고 0219 및 0168을 오류로 설정합니다.

```xml
<WarningsAsErrors>0219,0168</WarningsAsErrors>
```

오류와 동일한 경고를 비활성화합니다.

```xml
<WarningsNotAsErrors>0219,0168</WarningsNotAsErrors>
```

**WarningsAsErrors** 를 사용하여 경고 세트를 오류로 구성합니다. **WarningsNotAsErrors** 를 사용하여 모든 경고를 오류로 설정한 경우 오류가 아니어야 하는 경고 세트를 구성합니다.

## <a name="disabledwarnings"></a>DisabledWarnings

**DisabledWarnings** 옵션을 사용하면 컴파일러에서 하나 이상의 경고를 표시하지 않을 수 있습니다. 여러 경고 번호를 쉼표로 구분합니다.

```xml
<DisabledWarnings>number1, number2</DisabledWarnings>
```

`number1`, `number2` 컴파일러에서 표시하지 않으려는 경고 번호입니다. 경고 식별자의 숫자 부분을 지정합니다. 예를 들어 *CS0028* 을 표시하지 않으려면 `<DisabledWarnings>28</DisabledWarnings>`를 지정할 수 있습니다. 컴파일러는 이전 릴리스에서 유효했지만 제거된 **DisabledWarnings** 에 전달된 경고 번호를 자동으로 무시합니다. 예를 들어 *CS0679* 는 Visual Studio .NET 2002의 컴파일러에서 유효했지만 이후에 제거되었습니다.

 다음 경고는 **DisabledWarnings** 옵션으로 표시되지 않도록 설정할 수 없습니다.

- 컴파일러 경고(수준 1) CS2002  
- 컴파일러 경고(수준 1) CS2023
- 컴파일러 경고(수준 1) CS2029

## <a name="codeanalysisruleset"></a>CodeAnalysisRuleSet

특정 진단을 구성하는 규칙 집합 파일을 지정합니다.

```xml
<CodeAnalysisRuleSet>MyConfiguration.ruleset</CodeAnalysisRuleSet>
```

여기서 `MyConfiguration.ruleset`은 규칙 집합 파일의 경로입니다. 규칙 집합 사용에 대한 자세한 내용은 [규칙 집합에 대한 Visual Studio 설명서](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules)의 문서를 참조하세요.

## <a name="errorlog"></a>ErrorLog

모든 컴파일러와 분석기 진단을 로그할 파일을 지정합니다.

```xml
<ErrorLog>MyConfiguration.ruleset</ErrorLog>
```

**ErrorLog** 옵션을 사용하면 컴파일러에서 [SARIF(정적 분석 결과 교환 형) 로그](https://github.com/microsoft/sarif-tutorials/blob/main/docs/1-Introduction.md#:~:text=What%20is%20SARIF%3F,for%20use%20by%20simpler%20tools)를 출력할 수 있습니다. SARIF 로그는 일반적으로 컴파일러 및 분석기 진단의 결과를 분석하는 도구에서 읽습니다.

## <a name="reportanalyzer"></a>ReportAnalyzer

실행 시간과 같은 추가적인 분석 정보를 보고합니다.

```xml
<ReportAnalyzer>true</ReportAnalyzer>
```

**ReportAnalyzer** 옵션을 사용하면 컴파일러가 빌드에서 분석기의 성능 특성을 자세히 설명하는 추가 MSBuild 로그 정보를 내보냅니다. 일반적으로 분석기 작성자가 분석기의 유효성을 검사하는 과정에서 사용합니다.
