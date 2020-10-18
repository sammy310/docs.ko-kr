---
title: 중첩된 함수에 '<delegatename>' 대리자와 호환되는 시그니처가 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 0dde340164f1ba80d0e1d9fbb5d17ba6da0a5bc4
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160056"
---
# <a name="bc36532-nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a><span data-ttu-id="341c3-102">BC36532: 중첩 된 함수에 ' ' 대리자와 호환 되는 시그니처가 없습니다. \<delegatename></span><span class="sxs-lookup"><span data-stu-id="341c3-102">BC36532: Nested function does not have a signature that is compatible with delegate '\<delegatename>'</span></span>

<span data-ttu-id="341c3-103">호환 되지 않는 시그니처가 있는 대리자에 람다 식이 할당 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="341c3-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="341c3-104">예를 들어 다음 코드에서 대리자에는 `Del` 두 개의 정수 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="341c3-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>

```vb
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer
```

<span data-ttu-id="341c3-105">하나의 인수를 포함 하는 람다 식이 형식으로 선언 된 경우 오류가 발생 합니다 `Del` .</span><span class="sxs-lookup"><span data-stu-id="341c3-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>

```vb
' Neither of these is valid.
' Dim lambda1 As Del = Function(n As Integer) n + 1
' Dim lambda2 As Del = Function(n) n + 1
```

<span data-ttu-id="341c3-106">**오류 ID:** BC36532</span><span class="sxs-lookup"><span data-stu-id="341c3-106">**Error ID:** BC36532</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="341c3-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="341c3-107">To correct this error</span></span>

<span data-ttu-id="341c3-108">시그니처가 호환 되도록 대리자 정의 또는 할당 된 람다 식 중 하나를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="341c3-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>

## <a name="see-also"></a><span data-ttu-id="341c3-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="341c3-109">See also</span></span>

- [<span data-ttu-id="341c3-110">완화된 대리자 변환</span><span class="sxs-lookup"><span data-stu-id="341c3-110">Relaxed Delegate Conversion</span></span>](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="341c3-111">람다 식</span><span class="sxs-lookup"><span data-stu-id="341c3-111">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
