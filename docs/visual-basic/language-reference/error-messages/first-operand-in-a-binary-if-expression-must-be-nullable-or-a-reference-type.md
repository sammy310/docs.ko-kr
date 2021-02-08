---
description: "자세한 내용은 다음에 대해 자세히 알아보세요. BC33107: 이항 ' If ' 식의 첫 번째 피연산자는 nullable 이거나 참조 형식 이어야 합니다."
title: "'If' 이항 식의 첫 번째 피연산자는 nullable이거나 참조 형식이어야 합니다."
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: 4a0037680e31a8220cb796e6d8f3215139e01b20
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796251"
---
# <a name="bc33107-first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a><span data-ttu-id="d9098-103">BC33107: 이항 ' If ' 식의 첫 번째 피연산자는 nullable 이거나 참조 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9098-103">BC33107: First operand in a binary 'If' expression must be nullable or a reference type</span></span>

<span data-ttu-id="d9098-104">식에는 `If` 두 개 또는 세 개의 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9098-104">An `If` expression can take either two or three arguments.</span></span> <span data-ttu-id="d9098-105">두 개의 인수만 전송 하는 경우 첫 번째 인수는 참조 형식 이거나 nullable 값 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9098-105">When you send only two arguments, the first argument must be a reference type or a nullable value type.</span></span> <span data-ttu-id="d9098-106">첫 번째 인수가 이외의 값으로 계산 되 면 `Nothing` 해당 값이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9098-106">If the first argument evaluates to anything other than `Nothing`, its value is returned.</span></span> <span data-ttu-id="d9098-107">첫 번째 인수가로 계산 되는 경우 `Nothing` 두 번째 인수가 계산 되어 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9098-107">If the first argument evaluates to `Nothing`, the second argument is evaluated and returned.</span></span>

 <span data-ttu-id="d9098-108">예를 들어, 다음 코드에는 세 개의 인수와 두 개의 인수를 사용 하는 식이 포함 되어 있습니다 `If` .</span><span class="sxs-lookup"><span data-stu-id="d9098-108">For example, the following code contains two `If` expressions, one with three arguments and one with two arguments.</span></span> <span data-ttu-id="d9098-109">식은 동일한 값을 계산 하 고 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9098-109">The expressions calculate and return the same value.</span></span>

```vb
' firstChoice is a nullable value type.
Dim firstChoice? As Integer = Nothing
Dim secondChoice As Integer = 1128
' If expression with three arguments.
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))
' If expression with two arguments.
Console.WriteLine(If(firstChoice, secondChoice))
```

 <span data-ttu-id="d9098-110">다음 식에서이 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9098-110">The following expressions cause this error:</span></span>

```vb
Dim choice1 = 4
Dim choice2 = 5
Dim booleanVar = True

' Not valid.
'Console.WriteLine(If(choice1 < choice2, 1))
' Not valid.
'Console.WriteLine(If(booleanVar, "Test returns True."))
```

 <span data-ttu-id="d9098-111">**오류 ID:** BC33107</span><span class="sxs-lookup"><span data-stu-id="d9098-111">**Error ID:** BC33107</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d9098-112">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="d9098-112">To correct this error</span></span>

- <span data-ttu-id="d9098-113">첫 번째 인수가 nullable 값 형식 또는 참조 형식이 되도록 코드를 변경할 수 없는 경우에는 세 인수 식으로 변환 하거나 문으로 변환 하는 것이 좋습니다 `If` `If...Then...Else` .</span><span class="sxs-lookup"><span data-stu-id="d9098-113">If you cannot change the code so that the first argument is a nullable value type or reference type, consider converting to a three-argument `If` expression, or to an `If...Then...Else` statement.</span></span>

```vb
Console.WriteLine(If(choice1 < choice2, 1, 2))
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))
```

## <a name="see-also"></a><span data-ttu-id="d9098-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9098-114">See also</span></span>

- [<span data-ttu-id="d9098-115">If 연산자</span><span class="sxs-lookup"><span data-stu-id="d9098-115">If Operator</span></span>](../operators/if-operator.md)
- [<span data-ttu-id="d9098-116">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="d9098-116">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
- [<span data-ttu-id="d9098-117">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="d9098-117">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
