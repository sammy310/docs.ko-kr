---
title: Return 문
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: efc85a3a844898345aa2d16926ba0e35d7346d1b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333010"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="66728-102">Return 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66728-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="66728-103">`Function`, `Sub`, `Get`, `Set`또는 `Operator` 프로시저를 호출한 코드에 대 한 제어를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="66728-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66728-104">구문</span><span class="sxs-lookup"><span data-stu-id="66728-104">Syntax</span></span>  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="66728-105">파트</span><span class="sxs-lookup"><span data-stu-id="66728-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="66728-106">`Function`, `Get`또는 `Operator` 프로시저에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="66728-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="66728-107">호출 코드에 반환 될 값을 나타내는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="66728-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66728-108">주의</span><span class="sxs-lookup"><span data-stu-id="66728-108">Remarks</span></span>  
 <span data-ttu-id="66728-109">`Sub` 또는 `Set` 프로시저에서 `Return` 문은 `Exit Sub` 또는 `Exit Property` 문과 같으며 `expression`를 제공 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66728-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="66728-110">`Function`, `Get`또는 `Operator` 프로시저에서 `Return` 문은 `expression`을 포함 해야 하며 `expression`는 프로시저의 반환 형식으로 변환할 수 있는 데이터 형식으로 계산 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66728-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="66728-111">`Function` 또는 `Get` 프로시저에서는 프로시저 이름에 식을 할당 하 여 반환 값으로 사용 하 고 `Exit Function` 또는 `Exit Property` 문을 실행 하는 방법도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66728-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="66728-112">`Operator` 프로시저에서는 `Return expression`를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66728-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="66728-113">동일한 프로시저에 필요한 만큼 `Return` 문을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66728-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66728-114">`Finally` 블록의 코드는 `Try` 또는 `Catch` 블록에서 `Return` 문이 발생 한 후에 실행 되지만 해당 `Return` 문이 실행 되기 전에 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66728-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="66728-115">`Finally` 블록에는 `Return` 문을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66728-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66728-116">예제</span><span class="sxs-lookup"><span data-stu-id="66728-116">Example</span></span>  
 <span data-ttu-id="66728-117">다음 예제에서는 프로시저에서 다른 작업을 수행할 필요가 없을 때 `Return` 문을 여러 번 사용 하 여 호출 코드로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="66728-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="66728-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66728-118">See also</span></span>

- [<span data-ttu-id="66728-119">Function 문</span><span class="sxs-lookup"><span data-stu-id="66728-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="66728-120">Sub 문</span><span class="sxs-lookup"><span data-stu-id="66728-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="66728-121">Get 문</span><span class="sxs-lookup"><span data-stu-id="66728-121">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="66728-122">Set 문</span><span class="sxs-lookup"><span data-stu-id="66728-122">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="66728-123">Operator 문</span><span class="sxs-lookup"><span data-stu-id="66728-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="66728-124">Property 문</span><span class="sxs-lookup"><span data-stu-id="66728-124">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="66728-125">Exit 문</span><span class="sxs-lookup"><span data-stu-id="66728-125">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="66728-126">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="66728-126">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
