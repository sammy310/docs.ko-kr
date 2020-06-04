---
title: "'typename'이(가) nullable 형식이므로 'typename' 형식의 'IsNot' 피연산자는 'Nothing'과(와)만 비교할 수 있습니다."
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: fb61b04021bd844fade94413b4f3b28b82f6411b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402800"
---
# <a name="isnot-operand-of-type-typename-can-only-be-compared-to-nothing-because-typename-is-a-nullable-type"></a><span data-ttu-id="66343-102">'typename'이(가) nullable 형식이므로 'typename' 형식의 'IsNot' 피연산자는 'Nothing'과(와)만 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66343-102">'IsNot' operand of type 'typename' can only be compared to 'Nothing', because 'typename' is a nullable type</span></span>

<span data-ttu-id="66343-103">Nullable 값 형식으로 선언 된 변수가 연산자를 사용 하는 식과 비교 되었습니다 `Nothing` `IsNot` .</span><span class="sxs-lookup"><span data-stu-id="66343-103">A variable declared as a nullable value type has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>

<span data-ttu-id="66343-104">**오류 ID:** BC32128</span><span class="sxs-lookup"><span data-stu-id="66343-104">**Error ID:** BC32128</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="66343-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="66343-105">To correct this error</span></span>

<span data-ttu-id="66343-106">`Nothing` 연산자를 사용하여 nullable 형식을 `IsNot` 이외의 식과 비교하려면 다음 예제와 같이 nullable 형식에서 `GetType` 메서드를 호출하고 그 결과를 식과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="66343-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>

```vb
Dim number? As Integer = 5

If number IsNot Nothing Then
  If number.GetType() IsNot Type.GetType("System.Int32") Then

  End If
End If
```

## <a name="see-also"></a><span data-ttu-id="66343-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66343-107">See also</span></span>

- [<span data-ttu-id="66343-108">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="66343-108">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="66343-109">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="66343-109">IsNot Operator</span></span>](../operators/isnot-operator.md)
