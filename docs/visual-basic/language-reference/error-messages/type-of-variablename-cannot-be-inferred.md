---
description: '자세한 정보: <variablename> 루프 범위와 단계 변수는 같은 형식으로 확장 되지 않으므로 BC30982: type의 형식을 유추할 수 없습니다.'
title: 루프 범위와 단계 변수는 같은 형식으로 변환할 수 없으므로 '<variablename>' 형식을 확대 변환할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: 399e021500813127df6ecede2534783df09ac8dc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641163"
---
# <a name="bc30982-type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a><span data-ttu-id="5255c-103">BC30982: \<variablename> 루프 범위와 단계 변수가 동일한 형식으로 확장 되지 않으므로 ' '의 형식을 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5255c-103">BC30982: Type of '\<variablename>' cannot be inferred because the loop bounds and the step variable do not widen to the same type</span></span>

<span data-ttu-id="5255c-104">`For...Next`다음 조건이 true 이기 때문에 컴파일러가 루프 제어 변수의 데이터 형식을 유추할 수 없는 루프를 작성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5255c-104">You have written a `For...Next` loop in which the compiler cannot infer a data type for the loop control variable because the following conditions are true:</span></span>

- <span data-ttu-id="5255c-105">`As` 절을 사용하여 루프 제어 변수의 데이터 형식을 지정하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="5255c-105">The data type of the loop control variable is not specified with an `As` clause.</span></span>

- <span data-ttu-id="5255c-106">루프 범위와 단계 변수에 두 개 이상의 데이터 형식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5255c-106">The loop bounds and step variable contain at least two data types.</span></span>

- <span data-ttu-id="5255c-107">데이터 형식 간에 표준 변환이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5255c-107">No standard conversions exist between the data types.</span></span>

 <span data-ttu-id="5255c-108">따라서 컴파일러가 루프 제어 변수의 데이터 형식을 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5255c-108">Therefore, the compiler cannot infer the data type of a loop's control variable.</span></span>

 <span data-ttu-id="5255c-109">다음 예제에서 단계 변수는 문자이 고 루프 범위는 두 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="5255c-109">In the following example, the step variable is a character and the loop bounds are both integers.</span></span> <span data-ttu-id="5255c-110">문자와 정수 사이에는 표준 변환이 없기 때문에이 오류가 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5255c-110">Because there is no standard conversion between characters and integers, this error is reported.</span></span>

```vb
Dim stepVar = "1"c
Dim m = 0
Dim n = 20

' Not valid.
' For i = 1 To 10 Step stepVar
    ' Loop processing
' Next
```

<span data-ttu-id="5255c-111">**오류 ID:** BC30982</span><span class="sxs-lookup"><span data-stu-id="5255c-111">**Error ID:** BC30982</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="5255c-112">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="5255c-112">To correct this error</span></span>

- <span data-ttu-id="5255c-113">필요에 따라 루프 범위와 단계 변수의 형식을 변경 하 여 그 중 하나 이상이 다른 형식으로 확장 될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5255c-113">Change the types of the loop bounds and step variable as necessary so that at least one of them is a type that the others widen to.</span></span> <span data-ttu-id="5255c-114">앞의 예제에서는의 형식을로 변경 합니다 `stepVar` `Integer` .</span><span class="sxs-lookup"><span data-stu-id="5255c-114">In the preceding example, change the type of `stepVar` to `Integer`.</span></span>

  ```vb
  Dim stepVar = 1
  ```

  <span data-ttu-id="5255c-115">또는</span><span class="sxs-lookup"><span data-stu-id="5255c-115">-or-</span></span>

  ```vb
  Dim stepVar As Integer = 1
  ```

- <span data-ttu-id="5255c-116">명시적 변환 함수를 사용 하 여 루프 범위와 단계 변수를 적절 한 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5255c-116">Use explicit conversion functions to convert the loop bounds and step variable to the appropriate types.</span></span> <span data-ttu-id="5255c-117">앞의 예제에서 `Val` 함수를에 적용 `stepVar` 합니다.</span><span class="sxs-lookup"><span data-stu-id="5255c-117">In the preceding example, apply the `Val` function to `stepVar`.</span></span>

  ```vb
  For i = 1 To 10 Step Val(stepVar)
      ' Loop processing
  Next
  ```

## <a name="see-also"></a><span data-ttu-id="5255c-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5255c-118">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="5255c-119">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="5255c-119">For...Next Statement</span></span>](../statements/for-next-statement.md)
- [<span data-ttu-id="5255c-120">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="5255c-120">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="5255c-121">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="5255c-121">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="5255c-122">Option Infer 문</span><span class="sxs-lookup"><span data-stu-id="5255c-122">Option Infer Statement</span></span>](../statements/option-infer-statement.md)
- [<span data-ttu-id="5255c-123">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="5255c-123">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="5255c-124">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="5255c-124">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
