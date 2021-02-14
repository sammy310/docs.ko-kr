---
description: '자세한 정보: 방법: 프로시저를 다른 프로시저에 전달 Visual Basic'
title: '방법: 다른 프로시저에 프로시저 전달'
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: dfd75d1f58519365bfb6ac59892238b5322743f3
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434448"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="46d97-103">방법: Visual Basic에서 프로시저에 다른 프로시저 전달</span><span class="sxs-lookup"><span data-stu-id="46d97-103">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>

<span data-ttu-id="46d97-104">이 예제에서는 대리자를 사용 하 여 프로시저를 다른 프로시저에 전달 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46d97-104">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="46d97-105">대리자는 Visual Basic의 다른 형식 처럼 사용할 수 있는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="46d97-105">A delegate is a type that you can use like any other type in Visual Basic.</span></span> <span data-ttu-id="46d97-106">`AddressOf`연산자는 프로시저 이름에 적용 될 때 대리자 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d97-106">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="46d97-107">이 예제에는 연산자를 사용 하 여 얻은 다른 프로시저에 대 한 참조를 사용할 수 있는 대리자 매개 변수를 포함 하는 프로시저가 있습니다 `AddressOf` .</span><span class="sxs-lookup"><span data-stu-id="46d97-107">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="46d97-108">대리자 및 일치 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="46d97-108">Create the delegate and matching procedures</span></span>  
  
1. <span data-ttu-id="46d97-109">이라는 대리자를 만듭니다 `MathOperator` .</span><span class="sxs-lookup"><span data-stu-id="46d97-109">Create a delegate named `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. <span data-ttu-id="46d97-110">`AddNumbers`서명이 일치 하도록와 일치 하는 매개 변수 및 반환 값을 사용 하 여 라는 프로시저를 만듭니다 `MathOperator` .</span><span class="sxs-lookup"><span data-stu-id="46d97-110">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. <span data-ttu-id="46d97-111">`SubtractNumbers`와 일치 하는 서명을 사용 하 여 라는 이름의 프로시저를 만듭니다 `MathOperator` .</span><span class="sxs-lookup"><span data-stu-id="46d97-111">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. <span data-ttu-id="46d97-112">`DelegateTest`대리자를 매개 변수로 사용 하는 라는 프로시저를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="46d97-112">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="46d97-113">이 프로시저는 서명이 `AddNumbers` `SubtractNumbers` 시그니처와 일치 하기 때문에 또는에 대 한 참조를 수락할 수 있습니다 `MathOperator` .</span><span class="sxs-lookup"><span data-stu-id="46d97-113">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. <span data-ttu-id="46d97-114">대리자를 매개 변수로 사용 하 여 한 `Test` 번 호출 하 `DelegateTest` `AddNumbers` 고에 대 한 대리자를 매개 변수로 사용 하 여를 한 번 호출 하는 라는 프로시저를 만듭니다 `SubtractNumbers` .</span><span class="sxs-lookup"><span data-stu-id="46d97-114">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     <span data-ttu-id="46d97-115">`Test`가 호출 되 면 먼저 `AddNumbers` 및에 대 한 작동 결과 `5` `3` (8)를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d97-115">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="46d97-116">그런 다음 및에 대해 작동 하는 결과가 6 인 것으로 `SubtractNumbers` `9` `3` 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46d97-116">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46d97-117">추가 정보</span><span class="sxs-lookup"><span data-stu-id="46d97-117">See also</span></span>

- [<span data-ttu-id="46d97-118">대리자</span><span class="sxs-lookup"><span data-stu-id="46d97-118">Delegates</span></span>](index.md)
- [<span data-ttu-id="46d97-119">AddressOf 연산자</span><span class="sxs-lookup"><span data-stu-id="46d97-119">AddressOf Operator</span></span>](../../../language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="46d97-120">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="46d97-120">Delegate Statement</span></span>](../../../language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="46d97-121">방법: 대리자 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="46d97-121">How to: Invoke a Delegate Method</span></span>](how-to-invoke-a-delegate-method.md)
