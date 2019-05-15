---
title: 어설션
description: 식에서 테스트에 대 한 디버깅 기능으로 'assert' 식을 사용 하는 방법을 알아봅니다는 F# 프로그래밍 언어입니다.
ms.date: 05/16/2016
ms.openlocfilehash: 5fe24195c7548e9fbb927e4b95b752c7a963c6b3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642047"
---
# <a name="assertions"></a><span data-ttu-id="be0ec-103">어설션</span><span class="sxs-lookup"><span data-stu-id="be0ec-103">Assertions</span></span>

<span data-ttu-id="be0ec-104">`assert` 식 식을 테스트 하는 데 사용할 수 있는 디버깅 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="be0ec-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="be0ec-105">디버그 모드에서 실패 시 어설션에서 시스템 오류 대화 상자를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="be0ec-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="be0ec-106">구문</span><span class="sxs-lookup"><span data-stu-id="be0ec-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="be0ec-107">설명</span><span class="sxs-lookup"><span data-stu-id="be0ec-107">Remarks</span></span>

<span data-ttu-id="be0ec-108">합니다 `assert` 식에 형식 `bool -> unit`합니다.</span><span class="sxs-lookup"><span data-stu-id="be0ec-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="be0ec-109">이전 구문에서 *조건을* 테스트 하는 부울 식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be0ec-109">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="be0ec-110">식이 계산 되는 경우 `true`, 영향을 받지 않고 계속 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="be0ec-110">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="be0ec-111">이면 `false`, 시스템 오류 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="be0ec-111">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="be0ec-112">오류 대화 상자에 문자열을 포함 하는 캡션이 **어설션 오류**합니다.</span><span class="sxs-lookup"><span data-stu-id="be0ec-112">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="be0ec-113">대화 상자에 어설션 오류가 발생 한 위치를 지정 하는 스택 추적을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="be0ec-113">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="be0ec-114">디버그 모드에서 컴파일할 때에 가능 어설션 검사 즉, 경우 상수 `DEBUG` 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be0ec-114">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="be0ec-115">프로젝트 시스템에서 기본적으로 `DEBUG` 상수 릴리스 구성에 없습니다. 디버그 구성에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be0ec-115">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="be0ec-116">어설션 실패 오류를 사용 하 여 발생 수 없습니다 F# 예외 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="be0ec-116">The assertion failure error cannot be caught by using F# exception handling.</span></span>

> [!NOTE]
> <span data-ttu-id="be0ec-117">합니다 `assert` 함수는 <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="be0ec-117">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="be0ec-118">예제</span><span class="sxs-lookup"><span data-stu-id="be0ec-118">Example</span></span>

<span data-ttu-id="be0ec-119">다음 코드 예제에서는 `assert` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="be0ec-119">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="be0ec-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="be0ec-120">See also</span></span>

- [<span data-ttu-id="be0ec-121">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="be0ec-121">F# Language Reference</span></span>](index.md)
