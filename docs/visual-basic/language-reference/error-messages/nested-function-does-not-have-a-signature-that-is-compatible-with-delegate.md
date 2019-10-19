---
title: 중첩된 함수에 '<delegatename>' 대리자와 호환되는 시그니처가 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: d65c8eab661675c955ff6562098248c04036d6e7
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72580645"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a><span data-ttu-id="b71ee-102">중첩 된 함수에 ' \<delegatename > ' 대리자와 호환 되는 시그니처가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b71ee-102">Nested function does not have a signature that is compatible with delegate '\<delegatename>'</span></span>

<span data-ttu-id="b71ee-103">호환 되지 않는 시그니처가 있는 대리자에 람다 식이 할당 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b71ee-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="b71ee-104">예를 들어 다음 코드에서 대리자 `Del`에는 두 개의 정수 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b71ee-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>

```vb
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer
```

<span data-ttu-id="b71ee-105">하나의 인수를 포함 하는 람다 식이 형식 `Del`로 선언 된 경우이 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b71ee-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>

```vb
' Neither of these is valid.
' Dim lambda1 As Del = Function(n As Integer) n + 1
' Dim lambda2 As Del = Function(n) n + 1
```

<span data-ttu-id="b71ee-106">**오류 ID:** BC36532</span><span class="sxs-lookup"><span data-stu-id="b71ee-106">**Error ID:** BC36532</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="b71ee-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="b71ee-107">To correct this error</span></span>

<span data-ttu-id="b71ee-108">시그니처가 호환 되도록 대리자 정의 또는 할당 된 람다 식 중 하나를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b71ee-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>

## <a name="see-also"></a><span data-ttu-id="b71ee-109">참조</span><span class="sxs-lookup"><span data-stu-id="b71ee-109">See also</span></span>

- [<span data-ttu-id="b71ee-110">완화된 대리자 변환</span><span class="sxs-lookup"><span data-stu-id="b71ee-110">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="b71ee-111">람다 식</span><span class="sxs-lookup"><span data-stu-id="b71ee-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
