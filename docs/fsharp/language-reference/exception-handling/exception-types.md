---
title: 예외 형식
description: 예외 형식을 정의 하 고 사용 F# 하는 방법에 대해 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 8545fab50ff6338d1f1621710a838a200f9ac705
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630319"
---
# <a name="exception-types"></a><span data-ttu-id="cbcea-103">예외 형식</span><span class="sxs-lookup"><span data-stu-id="cbcea-103">Exception Types</span></span>

<span data-ttu-id="cbcea-104">에 F#는 .net 예외 형식 및 F# 예외 형식 이라는 두 가지 범주의 예외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbcea-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="cbcea-105">이 항목에서는 예외 형식을 정의 하 고 F# 사용 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbcea-105">This topic describes how to define and use F# exception types.</span></span>

## <a name="syntax"></a><span data-ttu-id="cbcea-106">구문</span><span class="sxs-lookup"><span data-stu-id="cbcea-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="cbcea-107">설명</span><span class="sxs-lookup"><span data-stu-id="cbcea-107">Remarks</span></span>

<span data-ttu-id="cbcea-108">이전 구문에서 *예외 형식은* 새 F# 예외 형식의 이름이 고, *인수 형식은* 이 형식의 예외를 발생 시킬 때 제공할 수 있는 인수의 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cbcea-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="cbcea-109">*인수 형식*에 튜플 형식을 사용 하 여 여러 인수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbcea-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="cbcea-110">F# 예외에 대 한 일반적인 정의는 다음과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbcea-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="cbcea-111">다음과 같이 `raise` 함수를 사용 하 여이 형식의 예외를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbcea-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="cbcea-112">다음 예제와 같이 F# `try...with` 식의 필터에서 직접 예외 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbcea-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="cbcea-113">에서 `exception` F# 키워드를 사용 하 여 정의 하는 예외 형식은에서 `System.Exception`상속 되는 새 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cbcea-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>

## <a name="see-also"></a><span data-ttu-id="cbcea-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="cbcea-114">See also</span></span>

- [<span data-ttu-id="cbcea-115">예외 처리</span><span class="sxs-lookup"><span data-stu-id="cbcea-115">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="cbcea-116">예외: `raise` 함수</span><span class="sxs-lookup"><span data-stu-id="cbcea-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)
- [<span data-ttu-id="cbcea-117">예외 계층</span><span class="sxs-lookup"><span data-stu-id="cbcea-117">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)
