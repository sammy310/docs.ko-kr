---
description: '자세한 정보: BC33000: 연산자 선언은 +,-, *,,/, ^, &amp; , Like, Mod, And, or, Xor, Not,  <<,  >> 중 하나 여야 합니다.'
title: 연산자 선언은 +,-, *,-,-, ^, &amp; , Like, Mod, And, or, Xor, Not,  <<,  >>, =,  <>, <, <=, >, >=, CType, IsTrue, IsFalse 중 하나 여야 합니다.
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: 0ad82a6414387278622a10624952ebc35e7e9b83
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795562"
---
# <a name="bc33000-operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a><span data-ttu-id="bb79d-103">BC33000: 연산자 선언은 +,-, \*, \, /, ^, &amp; Like, Mod, And, or, Xor, Not, \<\<, >> 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb79d-103">BC33000: Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, \<\<, >>...</span></span>

<span data-ttu-id="bb79d-104">오버 로드할 수 있는 연산자만 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb79d-104">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="bb79d-105">다음 표에서는 선언할 수 있는 연산자를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb79d-105">The following table lists the operators you can declare.</span></span>

|<span data-ttu-id="bb79d-106">Type</span><span class="sxs-lookup"><span data-stu-id="bb79d-106">Type</span></span>|<span data-ttu-id="bb79d-107">연산자</span><span class="sxs-lookup"><span data-stu-id="bb79d-107">Operators</span></span>|
|----------|---------------|
|<span data-ttu-id="bb79d-108">단항</span><span class="sxs-lookup"><span data-stu-id="bb79d-108">Unary</span></span>|<span data-ttu-id="bb79d-109">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="bb79d-109">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|
|<span data-ttu-id="bb79d-110">이진</span><span class="sxs-lookup"><span data-stu-id="bb79d-110">Binary</span></span>|<span data-ttu-id="bb79d-111">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="bb79d-111">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|
|<span data-ttu-id="bb79d-112">변환(단항)</span><span class="sxs-lookup"><span data-stu-id="bb79d-112">Conversion (unary)</span></span>|`CType`|

 <span data-ttu-id="bb79d-113">`=`이진 목록의 연산자는 대입 연산자가 아닌 비교 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="bb79d-113">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>

 <span data-ttu-id="bb79d-114">**오류 ID:** BC33000</span><span class="sxs-lookup"><span data-stu-id="bb79d-114">**Error ID:** BC33000</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="bb79d-115">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="bb79d-115">To correct this error</span></span>

- <span data-ttu-id="bb79d-116">오버로드할 수 있는 연산자 집합에서 연산자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb79d-116">Select an operator from the set of overloadable operators.</span></span>

- <span data-ttu-id="bb79d-117">직접 오버로드할 수 없는 연산자 오버로드 기능이 필요할 경우 적절한 매개 변수를 사용하고 적절한 값을 반환하는 `Function` 프로시저를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bb79d-117">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb79d-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb79d-118">See also</span></span>

- [<span data-ttu-id="bb79d-119">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="bb79d-119">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="bb79d-120">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="bb79d-120">Operator Procedures</span></span>](../../programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="bb79d-121">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="bb79d-121">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="bb79d-122">방법: 변환 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="bb79d-122">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="bb79d-123">Function 문</span><span class="sxs-lookup"><span data-stu-id="bb79d-123">Function Statement</span></span>](../statements/function-statement.md)
