---
title: 코드 분석 경고 표시 안 함
description: .NET 코드 분석 위반을 표시 하지 않을 수 있는 다양 한 방법을 알아봅니다.
ms.date: 01/28/2021
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- code analysis, suppress warnings
- suppress code analysis warnings
ms.openlocfilehash: b08e93089975a59fabfeb0daaf6a2a6454b2c7e8
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99217266"
---
# <a name="how-to-suppress-code-analysis-warnings"></a>코드 분석 경고를 표시 하지 않는 방법

이 문서에서는 .NET 앱을 빌드할 때 코드 분석에서 경고를 표시 하지 않을 수 있는 다양 한 방법을 설명 합니다.

> [!TIP]
> Visual Studio를 개발 환경으로 사용 *하는 경우 전구 메뉴에* 경고를 표시 하지 않도록 코드를 생성 하는 옵션이 제공 됩니다. 자세한 내용은 [위반 표시 안 함](/visualstudio/code-quality/use-roslyn-analyzers?#suppress-violations)을 참조 하세요.

## <a name="disable-the-rule"></a>규칙 사용 안 함

경고를 발생 시키는 코드 분석 규칙을 사용 하지 않도록 설정 하 여 전체 파일 또는 프로젝트에 대 한 규칙을 사용 하지 않도록 설정 합니다 (사용 하는 [구성 파일](configuration-files.md) 의 범위에 따라 다름). 규칙을 사용 하지 않도록 설정 하려면 구성 파일에서 해당 심각도를로 설정 `none` 합니다.

```ini
[*.{cs,vb}]
dotnet_diagnostic.<rule-ID>.severity = none
```

규칙 심각도에 대 한 자세한 내용은 [규칙 심각도 구성](~/docs/fundamentals/code-analysis/configuration-options.md#severity-level)을 참조 하세요.

## <a name="use-a-preprocessor-directive"></a>전처리기 지시문 사용

[#Pragma warning (c #)](../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) 또는 [Disable (Visual Basic)](../../visual-basic/language-reference/directives/disable-enable.md) 지시어를 사용 하 여 특정 코드 줄에 대해서만 경고를 표시 하지 않습니다.

```csharp
    try { ... }
    catch (Exception e)
    {
#pragma warning disable CA2200 // Rethrow to preserve stack details
        throw e;
#pragma warning restore CA2200 // Rethrow to preserve stack details
    }
```

```vb
    Try
        ...
    Catch e As Exception
#Disable Warning CA2200 ' Rethrow to preserve stack details
        Throw e
#Enable Warning CA2200 ' Rethrow to preserve stack details
    End Try
```

## <a name="use-the-suppressmessageattribute"></a>SuppressMessageAttribute 사용

를 사용 하 여 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 소스 파일 또는 프로젝트에 대 한 전역 비 표시 오류 (*GlobalSuppressions.cs* 또는 *globalsuppressions* 표시 파일)에서 경고를 표시 하지 않을 수 있습니다. 이 특성은 프로젝트 또는 파일의 특정 부분 에서만 경고를 표시 하지 않도록 하는 방법을 제공 합니다.

특성에 필요한 두 개의 위치 매개 변수는 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 규칙 및 *규칙 ID* 의 *범주* 입니다. 다음 코드 조각은 `"Usage"` `"CA2200:Rethrow to preserve stack details"` 이러한 매개 변수에 대해 및를 전달 합니다.

```csharp
[System.Diagnostics.CodeAnalysis.SuppressMessage("Usage", "CA2200:Rethrow to preserve stack details", Justification = "Not production code.")]
private static void IngorableCharacters()
{
    try
    {
        ...
    }
    catch (Exception e)
    {
        throw e;
    }
}
```

전역 비 표시 오류 (suppression) 파일에 특성을 추가 하는 경우, 예를 들어 표시 안 함의 [범위](xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Scope) 를 원하는 수준으로 `"member"` 합니다. 속성을 사용 하 여 경고를 표시 하지 않아야 하는 API를 지정 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Target> 합니다.

```csharp
[assembly: SuppressMessage("Usage", "CA2200:Rethrow to preserve stack details", Justification = "Not production code.", Scope = "member", Target = "~M:MyApp.Program.IngorableCharacters")]
```

명시적으로 제공 된 사용자 원본에 매핑되지 않는 컴파일러 생성 코드에 대 한 경고를 표시 하지 않으려면 비 표시 오류 (suppression) 특성을 전역 비 표시 오류 파일에 넣어야 합니다. 예를 들어 다음 코드는 컴파일러에서 내보낸 생성자에 대 한 위반을 억제 합니다.

```csharp
[module: SuppressMessage("Microsoft.Design", "CA1055:AbstractTypesDoNotHavePublicConstructors", Scope="member", Target="MyTools.Type..ctor()")]
```

## <a name="see-also"></a>참고 항목

- [위반 표시 안 함 (Visual Studio)](/visualstudio/code-quality/use-roslyn-analyzers?#suppress-violations)
