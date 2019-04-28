---
title: 예외 형식
description: 정의 및 사용 하는 방법을 알아봅니다 F# 예외 형식입니다.
ms.date: 05/16/2016
ms.openlocfilehash: ed721dd0dc46a486fafeac2fa4c096800995ccb7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772725"
---
# <a name="exception-types"></a><span data-ttu-id="267e7-103">예외 형식</span><span class="sxs-lookup"><span data-stu-id="267e7-103">Exception Types</span></span>

<span data-ttu-id="267e7-104">두 종류의 예외 F#:.NET 예외 형식 및 F# 예외 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="267e7-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="267e7-105">이 항목 정의 및 사용 하는 방법을 설명 F# 예외 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="267e7-105">This topic describes how to define and use F# exception types.</span></span>

## <a name="syntax"></a><span data-ttu-id="267e7-106">구문</span><span class="sxs-lookup"><span data-stu-id="267e7-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="267e7-107">설명</span><span class="sxs-lookup"><span data-stu-id="267e7-107">Remarks</span></span>

<span data-ttu-id="267e7-108">이전 구문에서 *예외 형식을* 의 새 이름입니다 F# 예외 형식 및 *인수 형식* 이 유형의 예외를 발생 시킬 때 제공할 수 있는 인수 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="267e7-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="267e7-109">튜플 형식을 사용 하 여 여러 인수를 지정할 수 있습니다 *인수 형식*합니다.</span><span class="sxs-lookup"><span data-stu-id="267e7-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="267e7-110">에 대 한 일반적인 정의 F# 예외는 다음 예제와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="267e7-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="267e7-111">사용 하 여이 형식의 예외를 생성할 수는 `raise` 함수를 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="267e7-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="267e7-112">사용할 수 있습니다는 F# 에 있는 필터에서 직접 예외 형식을 `try...with` 다음 예와에서 같이 식입니다.</span><span class="sxs-lookup"><span data-stu-id="267e7-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="267e7-113">사용 하 여 정의 하는 예외 형식 합니다 `exception` 키워드 F# 에서 상속 되는 새 유형이 `System.Exception`합니다.</span><span class="sxs-lookup"><span data-stu-id="267e7-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>

## <a name="see-also"></a><span data-ttu-id="267e7-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="267e7-114">See also</span></span>

- [<span data-ttu-id="267e7-115">예외 처리</span><span class="sxs-lookup"><span data-stu-id="267e7-115">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="267e7-116">예외: `raise` 함수</span><span class="sxs-lookup"><span data-stu-id="267e7-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)
- [<span data-ttu-id="267e7-117">예외 계층</span><span class="sxs-lookup"><span data-stu-id="267e7-117">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)