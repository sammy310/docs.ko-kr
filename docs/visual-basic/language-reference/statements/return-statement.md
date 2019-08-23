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
ms.openlocfilehash: af49ea95d7f9d01072190ac3ccf6ba2f1041347e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957667"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="692e0-102">Return 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="692e0-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="692e0-103">`Function` ,`Sub`, ,`Set`또는 프로시저`Operator` 를 호출한 코드로 제어를 반환 합니다. `Get`</span><span class="sxs-lookup"><span data-stu-id="692e0-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="692e0-104">구문</span><span class="sxs-lookup"><span data-stu-id="692e0-104">Syntax</span></span>  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="692e0-105">부분</span><span class="sxs-lookup"><span data-stu-id="692e0-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="692e0-106">`Function` ,`Get`또는 프로시저`Operator` 에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="692e0-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="692e0-107">호출 코드에 반환 될 값을 나타내는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="692e0-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="692e0-108">설명</span><span class="sxs-lookup"><span data-stu-id="692e0-108">Remarks</span></span>  
 <span data-ttu-id="692e0-109">`Sub` 또는 프로시저에서`Return` 문은 `Exit Sub` 또는`expression` 문과 같으며 제공`Exit Property` 되지 않아야 합니다. `Set`</span><span class="sxs-lookup"><span data-stu-id="692e0-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="692e0-110">`Function`, 또는프로시저`Operator` 에서 문은를 포함`expression`해야 하며`expression` , 프로시저의 반환 형식으로 변환할 수 있는 데이터 형식으로 계산 되어야 합니다. `Return` `Get`</span><span class="sxs-lookup"><span data-stu-id="692e0-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="692e0-111">또는 프로시저에서 프로시저 이름에 식을 할당 하 여 반환 값으로 사용 하 고 `Exit Function` 또는 `Exit Property` 문을 실행 하는 방법도 있습니다. `Get` `Function`</span><span class="sxs-lookup"><span data-stu-id="692e0-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="692e0-112">프로시저에서를 사용 `Return expression`해야 합니다. `Operator`</span><span class="sxs-lookup"><span data-stu-id="692e0-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="692e0-113">동일한 프로시저에 적절 한 `Return` 수의 문을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="692e0-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="692e0-114">`Finally` 블록의 코드는 `Try` 또는 `Return` `Return` 블록의 문이 발견 된 후에 실행 되며 해당 문이 실행 되기 전에 실행 됩니다. `Catch`</span><span class="sxs-lookup"><span data-stu-id="692e0-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="692e0-115">`Return` 문은 블록`Finally` 에 포함 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="692e0-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="692e0-116">예제</span><span class="sxs-lookup"><span data-stu-id="692e0-116">Example</span></span>  
 <span data-ttu-id="692e0-117">다음 예제에서는 `Return` 문을 여러 번 사용 하 여 프로시저에서 다른 작업을 수행할 필요가 없을 때 호출 코드로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="692e0-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="692e0-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="692e0-118">See also</span></span>

- [<span data-ttu-id="692e0-119">Function 문</span><span class="sxs-lookup"><span data-stu-id="692e0-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="692e0-120">Sub 문</span><span class="sxs-lookup"><span data-stu-id="692e0-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="692e0-121">Get 문</span><span class="sxs-lookup"><span data-stu-id="692e0-121">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="692e0-122">Set 문</span><span class="sxs-lookup"><span data-stu-id="692e0-122">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="692e0-123">Operator 문</span><span class="sxs-lookup"><span data-stu-id="692e0-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="692e0-124">Property 문</span><span class="sxs-lookup"><span data-stu-id="692e0-124">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="692e0-125">Exit 문</span><span class="sxs-lookup"><span data-stu-id="692e0-125">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="692e0-126">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="692e0-126">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
