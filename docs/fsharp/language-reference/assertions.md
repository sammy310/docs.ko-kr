---
title: 어설션
description: "' Assert ' 식을 F# 프로그래밍 언어에서 식을 테스트 하는 데 사용 하는 디버깅 기능으로 사용 하는 방법에 대해 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: b8b7e9662143b432d650f87515d4af31cced4149
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630030"
---
# <a name="assertions"></a><span data-ttu-id="b4af3-103">어설션</span><span class="sxs-lookup"><span data-stu-id="b4af3-103">Assertions</span></span>

<span data-ttu-id="b4af3-104">`assert` 식은 식을 테스트 하는 데 사용할 수 있는 디버깅 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="b4af3-105">디버그 모드에서 실패 시 어설션에서 시스템 오류 대화 상자를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="b4af3-106">구문</span><span class="sxs-lookup"><span data-stu-id="b4af3-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="b4af3-107">설명</span><span class="sxs-lookup"><span data-stu-id="b4af3-107">Remarks</span></span>

<span data-ttu-id="b4af3-108">식 `assert` 의 형식은 `bool -> unit`입니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="b4af3-109">이전 구문에서 *condition* 은 테스트할 부울 식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-109">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="b4af3-110">식이로 `true`평가 되 면 실행이 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-110">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="b4af3-111">로 `false`평가 되 면 시스템 오류 대화 상자가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-111">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="b4af3-112">오류 대화 상자에 실패 한 문자열 **어설션이**포함 된 캡션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-112">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="b4af3-113">이 대화 상자에는 어설션 오류가 발생 한 위치를 나타내는 스택 추적이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-113">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="b4af3-114">디버그 모드에서 컴파일할 때만 어설션 검사가 활성화 됩니다. 즉, 상수가 `DEBUG` 정의 된 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-114">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="b4af3-115">기본적으로 프로젝트 시스템에서 상수는 `DEBUG` 디버그 구성에 정의 되지만 릴리스 구성에는 정의 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-115">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="b4af3-116">예외 처리를 사용 하 F# 여 어설션 실패 오류를 catch 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-116">The assertion failure error cannot be caught by using F# exception handling.</span></span>

> [!NOTE]
> <span data-ttu-id="b4af3-117">함수 `assert` 는를 <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-117">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="b4af3-118">예제</span><span class="sxs-lookup"><span data-stu-id="b4af3-118">Example</span></span>

<span data-ttu-id="b4af3-119">다음 코드 예에서는 `assert` 식을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-119">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="b4af3-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="b4af3-120">See also</span></span>

- [<span data-ttu-id="b4af3-121">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="b4af3-121">F# Language Reference</span></span>](index.md)
