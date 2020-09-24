---
ms.openlocfilehash: b697bbf6844759de8babd4245667e7b333884ff8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538928"
---
### <a name="ca2200-rethrow-to-preserve-stack-details"></a><span data-ttu-id="83d36-101">CA2200: 스택 정보를 유지하도록 다시 throw하십시오.</span><span class="sxs-lookup"><span data-stu-id="83d36-101">CA2200: Rethrow to preserve stack details</span></span>

<span data-ttu-id="83d36-102">.NET 코드 분석기 규칙 [CA2200](/visualstudio/code-quality/ca2200)은 .NET 5.0부터 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="83d36-102">.NET code analyzer rule [CA2200](/visualstudio/code-quality/ca2200) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="83d36-103">이 규칙은 예외를 다시 throw하는 `catch` 블록에 대해 빌드 경고를 생성하며, 해당 예외는 `throw` 문에서 명시적으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="83d36-103">It produces a build warning for any `catch` blocks that rethrow an exception and the exception is explicitly specified in the `throw` statement.</span></span>

#### <a name="change-description"></a><span data-ttu-id="83d36-104">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="83d36-104">Change description</span></span>

<span data-ttu-id="83d36-105">.Net 5.0부터 .Net SDK에는 [.NET 소스 코드 분석기](../../../../docs/fundamentals/productivity/code-analysis.md)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="83d36-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="83d36-106">[CA2200](/visualstudio/code-quality/ca2200)을 포함하여 해당 규칙 중 여러 개가 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="83d36-106">Several of these rules are enabled, by default, including [CA2200](/visualstudio/code-quality/ca2200).</span></span> <span data-ttu-id="83d36-107">해당 규칙을 위반하는 코드가 프로젝트에 포함되고 프로젝트가 경고를 오류로 처리하도록 구성된 경우 해당 변경으로 인해 빌드의 호환성이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d36-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="83d36-108">규칙 CA2200은 예외가 다시 throw되고 `throw` 문에 예외 변수가 지정된 코드를 플래그 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="83d36-108">Rule CA2200 flags code where exceptions are rethrown and the exception variable is specified in the `throw` statement.</span></span> <span data-ttu-id="83d36-109">예외가 throw되는 경우 전달되는 정보의 일부는 스택 추적입니다.</span><span class="sxs-lookup"><span data-stu-id="83d36-109">When an exception is thrown, part of the information it carries is the stack trace.</span></span> <span data-ttu-id="83d36-110">스택 추적은 예외를 throw하는 메서드로 시작되고 예외를 catch하는 메서드로 종료되는 메서드 호출 계층 구조의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="83d36-110">The stack trace is a list of the method call hierarchy that starts with the method that throws the exception and ends with the method that catches the exception.</span></span> <span data-ttu-id="83d36-111">`throw` 문에 예외를 지정하여 예외가 다시 throw되는 경우 스택 추적은 현재 메서드에서 다시 시작되고 예외를 throw한 원래 메서드와 현재 메서드 간의 메서드 호출 목록이 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="83d36-111">If an exception is rethrown by specifying the exception in the `throw` statement, the stack trace restarts at the current method and the list of method calls between the original method that threw the exception and the current method is lost.</span></span> <span data-ttu-id="83d36-112">예외에서 원래 스택 추적 정보를 유지하려면 예외를 지정하지 않고 `throw` 문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83d36-112">To keep the original stack trace information with the exception, use the `throw` statement without specifying the exception.</span></span>

<span data-ttu-id="83d36-113">다음 코드 조각은 규칙 CA2200에 대한 경고를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83d36-113">The following code snippet does not produce a warning for rule CA2200.</span></span> <span data-ttu-id="83d36-114">그러나 주석 처리된 줄은 위반을 ‘트리거’합니다.</span><span class="sxs-lookup"><span data-stu-id="83d36-114">The commented line *would* trigger a violation, however.</span></span>

```csharp
catch (ArithmeticException e)
{
    // throw e;
    throw;
}
```

#### <a name="version-introduced"></a><span data-ttu-id="83d36-115">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="83d36-115">Version introduced</span></span>

<span data-ttu-id="83d36-116">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="83d36-116">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="83d36-117">권장 조치</span><span class="sxs-lookup"><span data-stu-id="83d36-117">Recommended action</span></span>

- <span data-ttu-id="83d36-118">예외를 명시적으로 지정하지 않고 예외를 다시 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="83d36-118">Rethrow exceptions without specifying the exception explicitly.</span></span> <span data-ttu-id="83d36-119">자세한 내용은 [CA2200](/visualstudio/code-quality/ca2200)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83d36-119">For more information, see [CA2200](/visualstudio/code-quality/ca2200).</span></span>

- <span data-ttu-id="83d36-120">코드 분석을 완전히 사용하지 않으려면 프로젝트 파일에서 `EnableNETAnalyzers`를 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="83d36-120">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="83d36-121">자세한 내용은 [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83d36-121">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="83d36-122">범주</span><span class="sxs-lookup"><span data-stu-id="83d36-122">Category</span></span>

<span data-ttu-id="83d36-123">코드 분석</span><span class="sxs-lookup"><span data-stu-id="83d36-123">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="83d36-124">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="83d36-124">Affected APIs</span></span>

<span data-ttu-id="83d36-125">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83d36-125">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
