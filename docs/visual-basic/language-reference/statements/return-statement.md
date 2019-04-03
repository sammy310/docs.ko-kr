---
title: Return 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: 7f8ec0456576133d37dd19b5c0f8878a7ac57dab
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831729"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="35a74-102">Return 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35a74-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="35a74-103">호출한 코드로 제어가 되돌아갑니다를 `Function`, `Sub`를 `Get`를 `Set`, 또는 `Operator` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="35a74-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35a74-104">구문</span><span class="sxs-lookup"><span data-stu-id="35a74-104">Syntax</span></span>  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="35a74-105">파트</span><span class="sxs-lookup"><span data-stu-id="35a74-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="35a74-106">필요는 `Function`, `Get`, 또는 `Operator` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="35a74-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="35a74-107">호출 코드에 반환 될 값을 나타내는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="35a74-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35a74-108">설명</span><span class="sxs-lookup"><span data-stu-id="35a74-108">Remarks</span></span>  
 <span data-ttu-id="35a74-109">에 `Sub` 또는 `Set` 프로시저를 `Return` 문과 동일는 `Exit Sub` 또는 `Exit Property` 문 및 `expression` 제공 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a74-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="35a74-110">에 `Function`, `Get`, 또는 `Operator` 절차는 `Return` 문에 포함 되어야 합니다 `expression`, 및 `expression` 프로시저의 반환 형식으로 변환 될 수 있는 데이터 형식으로 계산 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a74-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="35a74-111">에 `Function` 또는 `Get` 프로시저 있습니다 식을 반환 값으로 처리 하는 프로시저 이름에 할당 한 다음 실행 하는 대안을 `Exit Function` 또는 `Exit Property` 문을.</span><span class="sxs-lookup"><span data-stu-id="35a74-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="35a74-112">에 `Operator` 를 사용 해야 프로시저 `Return expression`합니다.</span><span class="sxs-lookup"><span data-stu-id="35a74-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="35a74-113">만큼 포함할 수 있습니다 `Return` 문을 동일한 프로시저에 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a74-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35a74-114">코드를 `Finally` 블록 실행를 `Return` 문에서 `Try` 또는 `Catch` 만난 전에 블록은 `Return` 문을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a74-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="35a74-115">A `Return` 에 문의 포함할 수 없습니다는 `Finally` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="35a74-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35a74-116">예제</span><span class="sxs-lookup"><span data-stu-id="35a74-116">Example</span></span>  
 <span data-ttu-id="35a74-117">다음 예제에서는 `Return` 문을 여러 번 절차는 다른 작업을 수행 하지 않아도 되는 경우 호출 코드에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a74-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="35a74-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="35a74-118">See also</span></span>

- [<span data-ttu-id="35a74-119">Function 문</span><span class="sxs-lookup"><span data-stu-id="35a74-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="35a74-120">Sub 문</span><span class="sxs-lookup"><span data-stu-id="35a74-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="35a74-121">Get 문</span><span class="sxs-lookup"><span data-stu-id="35a74-121">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="35a74-122">Set 문</span><span class="sxs-lookup"><span data-stu-id="35a74-122">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="35a74-123">Operator 문</span><span class="sxs-lookup"><span data-stu-id="35a74-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="35a74-124">Property 문</span><span class="sxs-lookup"><span data-stu-id="35a74-124">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="35a74-125">Exit 문</span><span class="sxs-lookup"><span data-stu-id="35a74-125">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="35a74-126">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="35a74-126">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
