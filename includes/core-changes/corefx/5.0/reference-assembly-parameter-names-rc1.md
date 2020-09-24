---
ms.openlocfilehash: 760c9ce2427bc1f5e9276e66ecb6d2cf2ed83c16
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738824"
---
### <a name="parameter-names-changed-in-rc1"></a><span data-ttu-id="a5d28-101">RC1에서 매개 변수 이름이 변경됨</span><span class="sxs-lookup"><span data-stu-id="a5d28-101">Parameter names changed in RC1</span></span>

<span data-ttu-id="a5d28-102">참조 어셈블리의 일부 매개 변수 이름이 구현 어셈블리의 매개 변수 이름과 일치하도록 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d28-102">Some reference assembly parameter names have changed to match parameter names in the implementation assemblies.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a5d28-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="a5d28-103">Change description</span></span>

<span data-ttu-id="a5d28-104">이전 .NET 5.0 미리 보기 및 RC 버전에서는 [참조 어셈블리](../../../../docs/standard/assembly/reference-assemblies.md)의 일부 매개 변수 이름이 구현 어셈블리의 해당 매개 변수와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a5d28-104">In previous .NET 5.0 preview and RC versions, some [reference assembly](../../../../docs/standard/assembly/reference-assemblies.md) parameter names are different to their corresponding parameters in the implementation assembly.</span></span> <span data-ttu-id="a5d28-105">이로 인해 명명된 인수와 리플렉션을 사용하는 동안 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d28-105">This can cause problems while using named arguments and reflection.</span></span>

<span data-ttu-id="a5d28-106">.NET 5.0 RC2에서는 참조 어셈블리의 일치하지 않는 매개 변수 이름이 구현 어셈블리의 해당 매개 변수 이름과 정확히 일치하도록 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d28-106">In .NET 5.0 RC2, these mismatched parameter names were updated in the reference assemblies to exactly match the corresponding parameter names in the implementation assemblies.</span></span>

<span data-ttu-id="a5d28-107">다음 표에는 변경된 API 및 매개 변수 이름이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d28-107">The following table shows the APIs and parameter names that changed.</span></span>

| <span data-ttu-id="a5d28-108">API</span><span class="sxs-lookup"><span data-stu-id="a5d28-108">API</span></span> | <span data-ttu-id="a5d28-109">이전 매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="a5d28-109">Old parameter name</span></span> | <span data-ttu-id="a5d28-110">새 매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="a5d28-110">New parameter name</span></span> |
| - | - | - |
| <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)> | `traceOptions` | `traceFlags` |
| <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=nameWithType> | `suffix` | `prefix` |

#### <a name="reason-for-change"></a><span data-ttu-id="a5d28-111">변경 이유</span><span class="sxs-lookup"><span data-stu-id="a5d28-111">Reason for change</span></span>

<span data-ttu-id="a5d28-112">일관성을 유지하고 명명된 인수와 리플렉션을 사용할 때 오류를 방지하기 위해 매개 변수 이름이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d28-112">The parameter names were changed for consistency and to avoid failures when using named arguments and reflection.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a5d28-113">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="a5d28-113">Version introduced</span></span>

<span data-ttu-id="a5d28-114">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="a5d28-114">5.0 RC2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a5d28-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="a5d28-115">Recommended action</span></span>

<span data-ttu-id="a5d28-116">매개 변수 이름 변경으로 인해 컴파일러 오류가 발생하는 경우 매개 변수 이름을 적절하게 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d28-116">If you encounter a compiler error due to a parameter name change, update the parameter name accordingly.</span></span>

#### <a name="category"></a><span data-ttu-id="a5d28-117">범주</span><span class="sxs-lookup"><span data-stu-id="a5d28-117">Category</span></span>

<span data-ttu-id="a5d28-118">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="a5d28-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a5d28-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="a5d28-119">Affected APIs</span></span>

- <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)>
- <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Diagnostics.ActivityContext.#ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)`
- `M:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)`

-->
