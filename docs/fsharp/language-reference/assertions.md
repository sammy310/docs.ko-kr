---
title: 어설션
description: "' Assert ' 식을 F# 프로그래밍 언어에서 식을 테스트 하는 데 사용 하는 디버깅 기능으로 사용 하는 방법에 대해 알아봅니다."
ms.date: 10/22/2019
ms.openlocfilehash: 430db20e5ca307ba43a72e678a0424e03b0ac381
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799066"
---
# <a name="assertions"></a><span data-ttu-id="66832-103">어설션</span><span class="sxs-lookup"><span data-stu-id="66832-103">Assertions</span></span>

<span data-ttu-id="66832-104">`assert` 식은 식을 테스트 하는 데 사용할 수 있는 디버깅 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="66832-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="66832-105">디버그 모드에서 실패 시 어설션에서 시스템 오류 대화 상자를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="66832-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="66832-106">구문</span><span class="sxs-lookup"><span data-stu-id="66832-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="66832-107">주의</span><span class="sxs-lookup"><span data-stu-id="66832-107">Remarks</span></span>

<span data-ttu-id="66832-108">`assert` 식의 형식이 `bool -> unit`입니다.</span><span class="sxs-lookup"><span data-stu-id="66832-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="66832-109">`assert` 함수는 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>으로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66832-109">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="66832-110">즉, 해당 동작은 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>를 직접 호출 하는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="66832-110">This means its behavior is identical to having called <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> directly.</span></span>

<span data-ttu-id="66832-111">디버그 모드에서 컴파일할 때만 어설션 검사가 활성화 됩니다. 즉, 상수 `DEBUG` 정의 된 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="66832-111">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="66832-112">프로젝트 시스템에서 기본적으로 `DEBUG` 상수는 디버그 구성에 정의 되어 있지만 릴리스 구성에는 정의 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66832-112">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="66832-113">예외 처리를 사용 하 F# 여 어설션 실패 오류를 catch 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66832-113">The assertion failure error cannot be caught by using F# exception handling.</span></span>

## <a name="example"></a><span data-ttu-id="66832-114">예제</span><span class="sxs-lookup"><span data-stu-id="66832-114">Example</span></span>

<span data-ttu-id="66832-115">다음 코드 예제에서는 `assert` 식을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="66832-115">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="66832-116">참조</span><span class="sxs-lookup"><span data-stu-id="66832-116">See also</span></span>

- [<span data-ttu-id="66832-117">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="66832-117">F# Language Reference</span></span>](index.md)
