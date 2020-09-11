---
ms.openlocfilehash: bba9659b92e5aabc276c585929c99898316036c5
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2020
ms.locfileid: "89359139"
---
### <a name="hardware-intrinsic-issupported-checks-may-differ-for-nested-types"></a><span data-ttu-id="7f1c6-101">중첩 형식의 경우 하드웨어 내장 IsSupported 검사가 다를 수 있음</span><span class="sxs-lookup"><span data-stu-id="7f1c6-101">Hardware intrinsic IsSupported checks may differ for nested types</span></span>

<span data-ttu-id="7f1c6-102">`<Isa>`에서 <xref:System.Runtime.Intrinsics.X86?displayProperty=nameWithType> 네임스페이스의 클래스를 참조하는 `<Isa>.X64.IsSupported`를 확인할 경우 이전 버전의 .NET과는 다른 결과가 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c6-102">Checking `<Isa>.X64.IsSupported`, where `<Isa>` refers to the classes in the <xref:System.Runtime.Intrinsics.X86?displayProperty=nameWithType> namespace, may now produce a different result to previous versions of .NET.</span></span>

> [!TIP]
> <span data-ttu-id="7f1c6-103">*ISA*는 업계 표준 아키텍처의 약어입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c6-103">*ISA* stands for industry standard architecture.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7f1c6-104">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="7f1c6-104">Version introduced</span></span>

<span data-ttu-id="7f1c6-105">5.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="7f1c6-105">5.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="7f1c6-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="7f1c6-106">Change description</span></span>

<span data-ttu-id="7f1c6-107">이전 버전의 .NET에서는 <xref:System.Runtime.Intrinsics.X86.Aes?displayProperty=nameWithType>과 같은 <xref:System.Runtime.Intrinsics.X86> 하드웨어 내장 형식 중 일부가 중첩된 `X64` 클래스를 노출하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c6-107">In previous versions of .NET, some of the <xref:System.Runtime.Intrinsics.X86> hardware-intrinsic types, for example, <xref:System.Runtime.Intrinsics.X86.Aes?displayProperty=nameWithType>, didn't expose a nested `X64` class.</span></span> <span data-ttu-id="7f1c6-108">해당 형식에 대해 `<Isa>.X64.IsSupported`를 호출하면 부모 클래스 `<Isa>`에 중첩된 `X64` 클래스의 `IsSupported` 속성으로 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c6-108">For these types, calling `<Isa>.X64.IsSupported` resolved to an `IsSupported` property on a nested `X64` class of a parent class of `<Isa>`.</span></span> <span data-ttu-id="7f1c6-109">즉, `<Isa>.IsSupported`에서 `false`를 반환하는 경우에도 속성이 `true`를 반환할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c6-109">This meant that the property could return `true` even when `<Isa>.IsSupported` returns `false`.</span></span>

<span data-ttu-id="7f1c6-110">.NET 5.0 이상 버전에서는 모든 <xref:System.Runtime.Intrinsics.X86> 형식이 적절하게 지원을 보고하는 중첩된 `X64` 클래스를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c6-110">In .NET 5.0 and later versions, all of the <xref:System.Runtime.Intrinsics.X86> types expose a nested `X64` class that appropriately reports support.</span></span> <span data-ttu-id="7f1c6-111">따라서 일반 계층 구조가 올바르게 유지되고, `<Isa>.X64.IsSupported`가 `true`이면 `<Isa>.IsSupported`도 `true`로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c6-111">This ensures that the general hierarchy remains correct, and that if `<Isa>.X64.IsSupported` is `true`, then `<Isa>.IsSupported` can also be assumed to be `true`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="7f1c6-112">변경 이유</span><span class="sxs-lookup"><span data-stu-id="7f1c6-112">Reason for change</span></span>

<span data-ttu-id="7f1c6-113">`<Isa>.X64.IsSupported`가 `true`이면 `<Isa>.IsSupported`도 `true`로 암시되도록 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c6-113">It was intended that if `<Isa>.X64.IsSupported` is `true`, `<Isa>.IsSupported` is also implied to be `true`.</span></span> <span data-ttu-id="7f1c6-114">그러나 C#에서 멤버 확인이 작동하는 방식 때문에 중첩된 `X64` 클래스가 없는 클래스에서 해당 사례가 아니고 사용자 코드 버그가 발생하는 상황이 노출되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c6-114">However, due to how member resolution works in C#, classes that didn't have a nested `X64` class exposed a situation where this wasn't always the case and led to bugs in user code.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7f1c6-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="7f1c6-115">Recommended action</span></span>

<span data-ttu-id="7f1c6-116">필요한 경우 `IsSupported`를 검사하여 적절한 ISA를 확인하는 코드를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c6-116">If necessary, adjust code that checks `IsSupported` to check for the appropriate ISA.</span></span>

#### <a name="category"></a><span data-ttu-id="7f1c6-117">범주</span><span class="sxs-lookup"><span data-stu-id="7f1c6-117">Category</span></span>

<span data-ttu-id="7f1c6-118">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="7f1c6-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7f1c6-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="7f1c6-119">Affected APIs</span></span>

- <xref:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported`

-->
