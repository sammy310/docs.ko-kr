---
ms.openlocfilehash: 5f1a8af37a305ab0904801002dd99e17e8eca62e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616124"
---
### <a name="two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a><span data-ttu-id="da76b-101">Public이 아닌 setter를 사용하는 속성에 양방향 데이터 바인딩을 지원하지 않음</span><span class="sxs-lookup"><span data-stu-id="da76b-101">Two-way data-binding to a property with a non-public setter is not supported</span></span>

#### <a name="details"></a><span data-ttu-id="da76b-102">설명</span><span class="sxs-lookup"><span data-stu-id="da76b-102">Details</span></span>

<span data-ttu-id="da76b-103">public setter가 없는 속성에 데이터 바인딩을 시도하는 것은 지원된 적이 없는 시나리오였습니다.</span><span class="sxs-lookup"><span data-stu-id="da76b-103">Attempting to data bind to a property without a public setter has never been a supported scenario.</span></span> <span data-ttu-id="da76b-104">.NET Framework 4.5.1부터는 이 시나리오가 <xref:System.InvalidOperationException?displayProperty=fullName>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="da76b-104">Beginning in the .NET Framework 4.5.1, this scenario will throw an <xref:System.InvalidOperationException?displayProperty=fullName>.</span></span> <span data-ttu-id="da76b-105">이 새로운 예외는 구체적으로 .NET Framework 4.5.1을 대상으로 하는 응용 프로그램만 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="da76b-105">Note that this new exception will only be thrown for apps that specifically target the .NET Framework 4.5.1.</span></span> <span data-ttu-id="da76b-106">응용 프로그램이 .NET Framework 4.5를 대상으로 하는 경우 호출이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="da76b-106">If an app targets the .NET Framework 4.5, the call will be allowed.</span></span> <span data-ttu-id="da76b-107">응용 프로그램이 특정 .NET Framework 버전을 대상으로 하지 않는 경우 바인딩은 단방향으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="da76b-107">If the app does not target a particular .NET Framework version, the binding will be treated as one-way.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="da76b-108">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="da76b-108">Suggestion</span></span>

<span data-ttu-id="da76b-109">응용 프로그램은 단방향 바인딩을 사용하거나 속성의 setter를 공개적으로 노출하도록 업데이트되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da76b-109">The app should be updated to either use one-way binding, or expose the property's setter publicly.</span></span> <span data-ttu-id="da76b-110">또는 .NET Framework 4.5를 대상으로 하면 응용 프로그램이 이전 동작을 실행하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da76b-110">Alternatively, targeting the .NET Framework 4.5 will cause the app to exhibit the old behavior.</span></span>

| <span data-ttu-id="da76b-111">이름</span><span class="sxs-lookup"><span data-stu-id="da76b-111">Name</span></span>    | <span data-ttu-id="da76b-112">값</span><span class="sxs-lookup"><span data-stu-id="da76b-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="da76b-113">Scope</span><span class="sxs-lookup"><span data-stu-id="da76b-113">Scope</span></span>   | <span data-ttu-id="da76b-114">부</span><span class="sxs-lookup"><span data-stu-id="da76b-114">Minor</span></span>       |
| <span data-ttu-id="da76b-115">버전</span><span class="sxs-lookup"><span data-stu-id="da76b-115">Version</span></span> | <span data-ttu-id="da76b-116">4.5.1</span><span class="sxs-lookup"><span data-stu-id="da76b-116">4.5.1</span></span>       |
| <span data-ttu-id="da76b-117">형식</span><span class="sxs-lookup"><span data-stu-id="da76b-117">Type</span></span>    | <span data-ttu-id="da76b-118">대상 변경</span><span class="sxs-lookup"><span data-stu-id="da76b-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="da76b-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="da76b-119">Affected APIs</span></span>

- <xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType>
