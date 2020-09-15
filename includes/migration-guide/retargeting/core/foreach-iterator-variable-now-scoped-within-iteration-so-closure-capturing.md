---
ms.openlocfilehash: 9a2d6a25a8ab1b8bf65b947557802e0805a7f826
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617199"
---
### <a name="foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a><span data-ttu-id="88f59-101">Foreach 반복자 변수는 이제 반복 내에서 범위가 지정되므로 클로저 캡처 의미가 다름(C#5에서)</span><span class="sxs-lookup"><span data-stu-id="88f59-101">Foreach iterator variable is now scoped within the iteration, so closure capturing semantics are different (in C#5)</span></span>

#### <a name="details"></a><span data-ttu-id="88f59-102">설명</span><span class="sxs-lookup"><span data-stu-id="88f59-102">Details</span></span>

<span data-ttu-id="88f59-103">C#5(Visual Studio 2012)부터 `foreach` 반복기 변수는 반복 내에서 범위가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="88f59-103">Beginning with C# 5 (Visual Studio 2012), `foreach` iterator variables are scoped within the iteration.</span></span> <span data-ttu-id="88f59-104">이것은 코드가 이전에 `foreach`의 클로저에 포함되지 않기 위해 변수에 종속되었던 경우 중단이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88f59-104">This can cause breaks if code was previously depending on the variables to not be included in the `foreach`'s closure.</span></span> <span data-ttu-id="88f59-105">이러한 변경의 증상은 대리자에게 전달된 반복기 변수가 대리자가 호출된 때의 값이 아닌 대리자가 생성된 때의 값으로 처리된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="88f59-105">The symptom of this change is that an iterator variable passed to a delegate is treated as the value it has at the time the delegate is created, rather than the value it has at the time the delegate is invoked.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="88f59-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="88f59-106">Suggestion</span></span>

<span data-ttu-id="88f59-107">이상적으로 코드는 새 컴파일러 동작을 예상하도록 업데이트되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f59-107">Ideally, code should be updated to expect the new compiler behavior.</span></span> <span data-ttu-id="88f59-108">이전의 의미 체계가 필요한 경우 반복기 변수는 루프 외부에 명시적으로 배치된 별도의 변수로 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88f59-108">If the old semantics are required, the iterator variable can be replaced with a separate variable which is explicitly placed outside of the loop's scope.</span></span>

| <span data-ttu-id="88f59-109">이름</span><span class="sxs-lookup"><span data-stu-id="88f59-109">Name</span></span>    | <span data-ttu-id="88f59-110">값</span><span class="sxs-lookup"><span data-stu-id="88f59-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="88f59-111">Scope</span><span class="sxs-lookup"><span data-stu-id="88f59-111">Scope</span></span>   | <span data-ttu-id="88f59-112">주요함</span><span class="sxs-lookup"><span data-stu-id="88f59-112">Major</span></span>       |
| <span data-ttu-id="88f59-113">버전</span><span class="sxs-lookup"><span data-stu-id="88f59-113">Version</span></span> | <span data-ttu-id="88f59-114">4.5</span><span class="sxs-lookup"><span data-stu-id="88f59-114">4.5</span></span>         |
| <span data-ttu-id="88f59-115">형식</span><span class="sxs-lookup"><span data-stu-id="88f59-115">Type</span></span>    | <span data-ttu-id="88f59-116">대상 변경</span><span class="sxs-lookup"><span data-stu-id="88f59-116">Retargeting</span></span> |
