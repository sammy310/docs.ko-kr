---
description: "' Typename '은 nullable 형식 이므로 ' typename ' 형식의 ' IsNot ' 피연산자는 ' n o n e '과만 비교할 수 있습니다."
title: "'typename'이(가) nullable 형식이므로 'typename' 형식의 'IsNot' 피연산자는 'Nothing'과(와)만 비교할 수 있습니다."
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 732c8bee2ae352824c7d50bba8b2b35598d6f53b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795991"
---
# <a name="bc32128-isnot-operand-of-type-typename-can-only-be-compared-to-nothing-because-typename-is-a-nullable-type"></a><span data-ttu-id="8b407-103">' Typename '은 nullable 형식 이므로 ' typename ' 형식의 ' IsNot ' 피연산자는 ' n u l l '과만 비교할 수 있습니다. BC32128</span><span class="sxs-lookup"><span data-stu-id="8b407-103">BC32128: 'IsNot' operand of type 'typename' can only be compared to 'Nothing', because 'typename' is a nullable type</span></span>

<span data-ttu-id="8b407-104">Nullable 값 형식으로 선언 된 변수가 연산자를 사용 하는 식과 비교 되었습니다 `Nothing` `IsNot` .</span><span class="sxs-lookup"><span data-stu-id="8b407-104">A variable declared as a nullable value type has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>

<span data-ttu-id="8b407-105">**오류 ID:** BC32128</span><span class="sxs-lookup"><span data-stu-id="8b407-105">**Error ID:** BC32128</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="8b407-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="8b407-106">To correct this error</span></span>

<span data-ttu-id="8b407-107">`Nothing` 연산자를 사용하여 nullable 형식을 `IsNot` 이외의 식과 비교하려면 다음 예제와 같이 nullable 형식에서 `GetType` 메서드를 호출하고 그 결과를 식과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="8b407-107">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>

```vb
Dim number? As Integer = 5

If number IsNot Nothing Then
  If number.GetType() IsNot Type.GetType("System.Int32") Then

  End If
End If
```

## <a name="see-also"></a><span data-ttu-id="8b407-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b407-108">See also</span></span>

- [<span data-ttu-id="8b407-109">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="8b407-109">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="8b407-110">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="8b407-110">IsNot Operator</span></span>](../operators/isnot-operator.md)
