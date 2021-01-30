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
# <a name="how-to-suppress-code-analysis-warnings"></a><span data-ttu-id="615e1-103">코드 분석 경고를 표시 하지 않는 방법</span><span class="sxs-lookup"><span data-stu-id="615e1-103">How to suppress code analysis warnings</span></span>

<span data-ttu-id="615e1-104">이 문서에서는 .NET 앱을 빌드할 때 코드 분석에서 경고를 표시 하지 않을 수 있는 다양 한 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="615e1-104">This article covers the various ways you can suppress warnings from code analysis when you build your .NET app.</span></span>

> [!TIP]
> <span data-ttu-id="615e1-105">Visual Studio를 개발 환경으로 사용 *하는 경우 전구 메뉴에* 경고를 표시 하지 않도록 코드를 생성 하는 옵션이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="615e1-105">If you're using Visual Studio as your development environment, the *light bulb* menu provides options that generate the code to suppress warnings for you.</span></span> <span data-ttu-id="615e1-106">자세한 내용은 [위반 표시 안 함](/visualstudio/code-quality/use-roslyn-analyzers?#suppress-violations)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="615e1-106">For more information, see [Suppress violations](/visualstudio/code-quality/use-roslyn-analyzers?#suppress-violations).</span></span>

## <a name="disable-the-rule"></a><span data-ttu-id="615e1-107">규칙 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="615e1-107">Disable the rule</span></span>

<span data-ttu-id="615e1-108">경고를 발생 시키는 코드 분석 규칙을 사용 하지 않도록 설정 하 여 전체 파일 또는 프로젝트에 대 한 규칙을 사용 하지 않도록 설정 합니다 (사용 하는 [구성 파일](configuration-files.md) 의 범위에 따라 다름).</span><span class="sxs-lookup"><span data-stu-id="615e1-108">By disabling the code analysis rule that's causing the warning, you disable the rule for your entire file or project (depending on the scope of the [configuration file](configuration-files.md) that you use).</span></span> <span data-ttu-id="615e1-109">규칙을 사용 하지 않도록 설정 하려면 구성 파일에서 해당 심각도를로 설정 `none` 합니다.</span><span class="sxs-lookup"><span data-stu-id="615e1-109">To disable the rule, set its severity to `none` in the configuration file.</span></span>

```ini
[*.{cs,vb}]
dotnet_diagnostic.<rule-ID>.severity = none
```

<span data-ttu-id="615e1-110">규칙 심각도에 대 한 자세한 내용은 [규칙 심각도 구성](~/docs/fundamentals/code-analysis/configuration-options.md#severity-level)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="615e1-110">For more information about rule severities, see [Configure rule severity](~/docs/fundamentals/code-analysis/configuration-options.md#severity-level).</span></span>

## <a name="use-a-preprocessor-directive"></a><span data-ttu-id="615e1-111">전처리기 지시문 사용</span><span class="sxs-lookup"><span data-stu-id="615e1-111">Use a preprocessor directive</span></span>

<span data-ttu-id="615e1-112">[#Pragma warning (c #)](../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) 또는 [Disable (Visual Basic)](../../visual-basic/language-reference/directives/disable-enable.md) 지시어를 사용 하 여 특정 코드 줄에 대해서만 경고를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="615e1-112">Use a [#pragma warning (C#)](../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) or [Disable (Visual Basic)](../../visual-basic/language-reference/directives/disable-enable.md) directive to suppress the warning for only a specific line of code.</span></span>

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

## <a name="use-the-suppressmessageattribute"></a><span data-ttu-id="615e1-113">SuppressMessageAttribute 사용</span><span class="sxs-lookup"><span data-stu-id="615e1-113">Use the SuppressMessageAttribute</span></span>

<span data-ttu-id="615e1-114">를 사용 하 여 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 소스 파일 또는 프로젝트에 대 한 전역 비 표시 오류 (*GlobalSuppressions.cs* 또는 *globalsuppressions* 표시 파일)에서 경고를 표시 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="615e1-114">You can use a <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> to suppress a warning either in the source file or in a global suppressions file for the project (*GlobalSuppressions.cs* or *GlobalSuppressions.vb*).</span></span> <span data-ttu-id="615e1-115">이 특성은 프로젝트 또는 파일의 특정 부분 에서만 경고를 표시 하지 않도록 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="615e1-115">This attribute provides a way to suppress a warning in only certain parts of your project or file.</span></span>

<span data-ttu-id="615e1-116">특성에 필요한 두 개의 위치 매개 변수는 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 규칙 및 *규칙 ID* 의 *범주* 입니다.</span><span class="sxs-lookup"><span data-stu-id="615e1-116">The two required, positional parameters for the <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> attribute are the *category* of the rule and the *rule ID*.</span></span> <span data-ttu-id="615e1-117">다음 코드 조각은 `"Usage"` `"CA2200:Rethrow to preserve stack details"` 이러한 매개 변수에 대해 및를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="615e1-117">The following code snippet passes `"Usage"` and `"CA2200:Rethrow to preserve stack details"` for these parameters.</span></span>

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

<span data-ttu-id="615e1-118">전역 비 표시 오류 (suppression) 파일에 특성을 추가 하는 경우, 예를 들어 표시 안 함의 [범위](xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Scope) 를 원하는 수준으로 `"member"` 합니다.</span><span class="sxs-lookup"><span data-stu-id="615e1-118">If you add the attribute to the global suppressions file, you [scope](xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Scope) the suppression to the desired level, for example `"member"`.</span></span> <span data-ttu-id="615e1-119">속성을 사용 하 여 경고를 표시 하지 않아야 하는 API를 지정 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Target> 합니다.</span><span class="sxs-lookup"><span data-stu-id="615e1-119">You specify the API where the warning should be suppressed using the <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Target> property.</span></span>

```csharp
[assembly: SuppressMessage("Usage", "CA2200:Rethrow to preserve stack details", Justification = "Not production code.", Scope = "member", Target = "~M:MyApp.Program.IngorableCharacters")]
```

<span data-ttu-id="615e1-120">명시적으로 제공 된 사용자 원본에 매핑되지 않는 컴파일러 생성 코드에 대 한 경고를 표시 하지 않으려면 비 표시 오류 (suppression) 특성을 전역 비 표시 오류 파일에 넣어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="615e1-120">To suppress warnings for compiler-generated code that doesn't map to explicitly provided user source, you must put the suppression attribute in a global suppressions file.</span></span> <span data-ttu-id="615e1-121">예를 들어 다음 코드는 컴파일러에서 내보낸 생성자에 대 한 위반을 억제 합니다.</span><span class="sxs-lookup"><span data-stu-id="615e1-121">For example, the following code suppresses a violation against a compiler-emitted constructor:</span></span>

```csharp
[module: SuppressMessage("Microsoft.Design", "CA1055:AbstractTypesDoNotHavePublicConstructors", Scope="member", Target="MyTools.Type..ctor()")]
```

## <a name="see-also"></a><span data-ttu-id="615e1-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="615e1-122">See also</span></span>

- [<span data-ttu-id="615e1-123">위반 표시 안 함 (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="615e1-123">Suppress violations (Visual Studio)</span></span>](/visualstudio/code-quality/use-roslyn-analyzers?#suppress-violations)
