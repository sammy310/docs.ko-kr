---
title: '호환성이 손상되는 변경: RC2에서 매개 변수 이름이 변경됨'
description: 일부 참조 어셈블리 매개 변수 이름이 .NET 5.0의 미리 보기 및 릴리스 후보 버전에서 변경된 핵심 .NET 라이브러리의 .NET 5.0 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 554a4fa9e08fdb504f380465496d7e7e9df85814
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759755"
---
# <a name="parameter-names-changed-in-rc2"></a><span data-ttu-id="f784c-103">RC2에서 매개 변수 이름이 변경됨</span><span class="sxs-lookup"><span data-stu-id="f784c-103">Parameter names changed in RC2</span></span>

<span data-ttu-id="f784c-104">참조 어셈블리의 일부 매개 변수 이름이 구현 어셈블리의 매개 변수 이름과 일치하도록 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f784c-104">Some reference assembly parameter names have changed to match parameter names in the implementation assemblies.</span></span>

## <a name="change-description"></a><span data-ttu-id="f784c-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="f784c-105">Change description</span></span>

<span data-ttu-id="f784c-106">이전 .NET 5.0 미리 보기 및 RC 버전에서는 [참조 어셈블리](../../../../standard/assembly/reference-assemblies.md)의 일부 매개 변수 이름이 구현 어셈블리의 해당 매개 변수와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f784c-106">In previous .NET 5.0 preview and RC versions, some [reference assembly](../../../../standard/assembly/reference-assemblies.md) parameter names are different to their corresponding parameters in the implementation assembly.</span></span> <span data-ttu-id="f784c-107">이로 인해 명명된 인수와 리플렉션을 사용하는 동안 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f784c-107">This can cause problems while using named arguments and reflection.</span></span>

<span data-ttu-id="f784c-108">.NET 5.0 RC2에서는 참조 어셈블리의 일치하지 않는 매개 변수 이름이 구현 어셈블리의 해당 매개 변수 이름과 정확히 일치하도록 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f784c-108">In .NET 5.0 RC2, these mismatched parameter names were updated in the reference assemblies to exactly match the corresponding parameter names in the implementation assemblies.</span></span>

<span data-ttu-id="f784c-109">다음 표에는 변경된 API 및 매개 변수 이름이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f784c-109">The following table shows the APIs and parameter names that changed.</span></span>

| <span data-ttu-id="f784c-110">API</span><span class="sxs-lookup"><span data-stu-id="f784c-110">API</span></span> | <span data-ttu-id="f784c-111">이전 매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="f784c-111">Old parameter name</span></span> | <span data-ttu-id="f784c-112">새 매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="f784c-112">New parameter name</span></span> |
| - | - | - |
| <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)> | `traceOptions` | `traceFlags` |
| <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=nameWithType> | `suffix` | `prefix` |

## <a name="reason-for-change"></a><span data-ttu-id="f784c-113">변경 이유</span><span class="sxs-lookup"><span data-stu-id="f784c-113">Reason for change</span></span>

<span data-ttu-id="f784c-114">일관성을 유지하고 명명된 인수와 리플렉션을 사용할 때 오류를 방지하기 위해 매개 변수 이름이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f784c-114">The parameter names were changed for consistency and to avoid failures when using named arguments and reflection.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="f784c-115">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="f784c-115">Version introduced</span></span>

<span data-ttu-id="f784c-116">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="f784c-116">5.0 RC2</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f784c-117">권장 조치</span><span class="sxs-lookup"><span data-stu-id="f784c-117">Recommended action</span></span>

<span data-ttu-id="f784c-118">매개 변수 이름 변경으로 인해 컴파일러 오류가 발생하는 경우 매개 변수 이름을 적절하게 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f784c-118">If you encounter a compiler error due to a parameter name change, update the parameter name accordingly.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="f784c-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="f784c-119">Affected APIs</span></span>

- <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)>
- <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `M:System.Diagnostics.ActivityContext.#ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)`
- `M:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)`

-->
