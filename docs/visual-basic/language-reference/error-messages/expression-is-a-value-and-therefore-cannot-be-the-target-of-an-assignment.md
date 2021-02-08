---
description: '다음에 대 한 자세한 정보: BC30068: Expression이 값 이므로 할당 대상일 수 없습니다.'
title: 식이 값이므로 할당 대상일 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: 424ce9cb0183153454bc068e9da940948b737c47
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796368"
---
# <a name="bc30068-expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a><span data-ttu-id="be28d-103">BC30068: 식이 값 이므로 할당 대상일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be28d-103">BC30068: Expression is a value and therefore cannot be the target of an assignment</span></span>

<span data-ttu-id="be28d-104">문에서 식에 값을 할당 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="be28d-104">A statement attempts to assign a value to an expression.</span></span> <span data-ttu-id="be28d-105">런타임에 쓰기 가능한 변수, 속성 또는 배열 요소에만 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be28d-105">You can assign a value only to a writable variable, property, or array element at run time.</span></span> <span data-ttu-id="be28d-106">다음 예에서는이 오류가 발생할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="be28d-106">The following example illustrates how this error can occur.</span></span>

```vb
Dim yesterday As Integer
ReadOnly maximum As Integer = 45
yesterday + 1 = DatePart(DateInterval.Day, Now)
' The preceding line is an ERROR because of an expression on the left.
maximum = 50
' The preceding line is an ERROR because maximum is declared ReadOnly.
```

<span data-ttu-id="be28d-107">속성과 배열 요소에도 유사한 예제가 적용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be28d-107">Similar examples could apply to properties and array elements.</span></span>

<span data-ttu-id="be28d-108">**간접 액세스.**</span><span class="sxs-lookup"><span data-stu-id="be28d-108">**Indirect Access.**</span></span> <span data-ttu-id="be28d-109">값 형식을 통해 간접적으로 액세스 하는 경우에도이 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be28d-109">Indirect access through a value type can also generate this error.</span></span> <span data-ttu-id="be28d-110">를 통해 간접적으로 액세스 하 여의 값을 설정 하려고 시도 하는 다음 코드 예제를 고려 합니다 <xref:System.Drawing.Point> <xref:System.Windows.Forms.Control.Location%2A> .</span><span class="sxs-lookup"><span data-stu-id="be28d-110">Consider the following code example, which attempts to set the value of <xref:System.Drawing.Point> by accessing it indirectly through <xref:System.Windows.Forms.Control.Location%2A>.</span></span>

```vb
' Assume this code runs inside Form1.
Dim exitButton As New System.Windows.Forms.Button()
exitButton.Text = "Exit this form"
exitButton.Location.X = 140
' The preceding line is an ERROR because of no storage for Location.
```

<span data-ttu-id="be28d-111">이전 예제의 마지막 문은 속성이 반환 하는 구조에 대 한 임시 할당만 만들기 때문에 실패 <xref:System.Drawing.Point> <xref:System.Windows.Forms.Control.Location%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="be28d-111">The last statement of the preceding example fails because it creates only a temporary allocation for the <xref:System.Drawing.Point> structure returned by the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span> <span data-ttu-id="be28d-112">구조체는 값 형식이 며 문이 실행 된 후에는 임시 구조가 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be28d-112">A structure is a value type, and the temporary structure is not retained after the statement runs.</span></span> <span data-ttu-id="be28d-113">에 대 한 변수를 선언 하 고 사용 하 여 문제를 해결 하면 <xref:System.Windows.Forms.Control.Location%2A> 구조에 대 한 보다 영구적인 할당을 만들 수 <xref:System.Drawing.Point> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be28d-113">The problem is resolved by declaring and using a variable for <xref:System.Windows.Forms.Control.Location%2A>, which creates a more permanent allocation for the <xref:System.Drawing.Point> structure.</span></span> <span data-ttu-id="be28d-114">다음 예제에서는 이전 예제의 마지막 문을 바꿀 수 있는 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="be28d-114">The following example shows code that can replace the last statement of the preceding example.</span></span>

```vb
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)
exitButton.Location = exitLocation
```

<span data-ttu-id="be28d-115">**오류 ID:** BC30068</span><span class="sxs-lookup"><span data-stu-id="be28d-115">**Error ID:** BC30068</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="be28d-116">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="be28d-116">To correct this error</span></span>

- <span data-ttu-id="be28d-117">문이 식에 값을 할당 하는 경우 식을 쓰기 가능한 단일 변수, 속성 또는 배열 요소로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="be28d-117">If the statement assigns a value to an expression, replace the expression with a single writable variable, property, or array element.</span></span>

- <span data-ttu-id="be28d-118">문에서 값 형식 (일반적으로 구조체)을 통해 간접적으로 액세스 하는 경우 값 형식을 저장할 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="be28d-118">If the statement makes indirect access through a value type (usually a structure), create a variable to hold the value type.</span></span>

- <span data-ttu-id="be28d-119">적절 한 구조 (또는 다른 값 형식)를 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="be28d-119">Assign the appropriate structure (or other value type) to the variable.</span></span>

- <span data-ttu-id="be28d-120">변수를 사용 하 여 속성에 액세스 하 고 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="be28d-120">Use the variable to access the property to assign it a value.</span></span>

## <a name="see-also"></a><span data-ttu-id="be28d-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be28d-121">See also</span></span>

- [<span data-ttu-id="be28d-122">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="be28d-122">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="be28d-123">문</span><span class="sxs-lookup"><span data-stu-id="be28d-123">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="be28d-124">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="be28d-124">Troubleshooting Procedures</span></span>](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
