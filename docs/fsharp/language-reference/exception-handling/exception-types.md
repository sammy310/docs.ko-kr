---
title: 예외 형식
description: 'F # 예외 형식을 정의 하 고 사용 하는 방법에 대해 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 8b4ceec31a2d68abbcd025812ffeeefc0c090efb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557231"
---
# <a name="exception-types"></a><span data-ttu-id="91bd9-103">예외 형식</span><span class="sxs-lookup"><span data-stu-id="91bd9-103">Exception Types</span></span>

<span data-ttu-id="91bd9-104">F #에는 두 가지 범주의 예외, 즉 .NET 예외 형식과 F # 예외 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91bd9-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="91bd9-105">이 항목에서는 F # 예외 형식을 정의 하 고 사용 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="91bd9-105">This topic describes how to define and use F# exception types.</span></span>

## <a name="syntax"></a><span data-ttu-id="91bd9-106">구문</span><span class="sxs-lookup"><span data-stu-id="91bd9-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="91bd9-107">설명</span><span class="sxs-lookup"><span data-stu-id="91bd9-107">Remarks</span></span>

<span data-ttu-id="91bd9-108">이전 구문에서 *예외 형식은* 새 F # 예외 형식의 이름이 고, *인수 형식은* 이 형식의 예외를 발생 시킬 때 제공할 수 있는 인수의 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="91bd9-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="91bd9-109">*인수 형식*에 튜플 형식을 사용 하 여 여러 인수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91bd9-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="91bd9-110">F # 예외에 대 한 일반적인 정의는 다음과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="91bd9-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="91bd9-111">다음과 같이 함수를 사용 하 여이 형식의 예외를 생성할 수 있습니다 `raise` .</span><span class="sxs-lookup"><span data-stu-id="91bd9-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="91bd9-112">다음 예제와 같이 식의 필터에서 직접 F # 예외 형식을 사용할 수 있습니다 `try...with` .</span><span class="sxs-lookup"><span data-stu-id="91bd9-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="91bd9-113">F #의 키워드를 사용 하 여 정의 하는 예외 형식은 `exception` 에서 상속 되는 새 형식입니다 `System.Exception` .</span><span class="sxs-lookup"><span data-stu-id="91bd9-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>

## <a name="see-also"></a><span data-ttu-id="91bd9-114">참조</span><span class="sxs-lookup"><span data-stu-id="91bd9-114">See also</span></span>

- [<span data-ttu-id="91bd9-115">예외 처리</span><span class="sxs-lookup"><span data-stu-id="91bd9-115">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="91bd9-116">예외: `raise` 함수</span><span class="sxs-lookup"><span data-stu-id="91bd9-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)
- [<span data-ttu-id="91bd9-117">예외 계층</span><span class="sxs-lookup"><span data-stu-id="91bd9-117">Exception Hierarchy</span></span>](../../../standard/exceptions/index.md)
