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
ms.openlocfilehash: cdb58e32c30c8e6c1662fb698ac5576c3f71258c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404202"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="0fd5c-102">Return 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0fd5c-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="0fd5c-103">`Function`,, `Sub` `Get` , `Set` 또는 `Operator` 프로시저를 호출한 코드로 제어를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fd5c-104">구문</span><span class="sxs-lookup"><span data-stu-id="0fd5c-104">Syntax</span></span>  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="0fd5c-105">부분</span><span class="sxs-lookup"><span data-stu-id="0fd5c-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="0fd5c-106">`Function`, `Get` 또는 프로시저에 필요 `Operator` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="0fd5c-107">호출 코드에 반환 될 값을 나타내는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fd5c-108">설명</span><span class="sxs-lookup"><span data-stu-id="0fd5c-108">Remarks</span></span>  
 <span data-ttu-id="0fd5c-109">`Sub`또는 프로시저에서 `Set` `Return` 문은 `Exit Sub` 또는 `Exit Property` 문과 같으며 `expression` 제공 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="0fd5c-110">`Function`, `Get` 또는 `Operator` 프로시저에서 `Return` 문은를 포함 해야 `expression` 하며, `expression` 프로시저의 반환 형식으로 변환할 수 있는 데이터 형식으로 계산 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="0fd5c-111">`Function`또는 프로시저에서 `Get` 프로시저 이름에 식을 할당 하 여 반환 값으로 사용 하 고 또는 문을 실행 하는 방법도 있습니다 `Exit Function` `Exit Property` .</span><span class="sxs-lookup"><span data-stu-id="0fd5c-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="0fd5c-112">프로시저에서 `Operator` 를 사용 해야 `Return expression` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="0fd5c-113">`Return`동일한 프로시저에 적절 한 수의 문을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0fd5c-114">블록의 코드는 `Finally` `Return` 또는 블록의 문이 발견 된 후에 실행 되며 `Try` `Catch` 해당 문이 실행 되기 전에 실행 됩니다 `Return` .</span><span class="sxs-lookup"><span data-stu-id="0fd5c-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="0fd5c-115">`Return`문은 블록에 포함 될 수 없습니다 `Finally` .</span><span class="sxs-lookup"><span data-stu-id="0fd5c-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fd5c-116">예제</span><span class="sxs-lookup"><span data-stu-id="0fd5c-116">Example</span></span>  
 <span data-ttu-id="0fd5c-117">다음 예제에서는 `Return` 문을 여러 번 사용 하 여 프로시저에서 다른 작업을 수행할 필요가 없을 때 호출 코드로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="0fd5c-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="0fd5c-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0fd5c-118">See also</span></span>

- [<span data-ttu-id="0fd5c-119">Function 문</span><span class="sxs-lookup"><span data-stu-id="0fd5c-119">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="0fd5c-120">Sub 문</span><span class="sxs-lookup"><span data-stu-id="0fd5c-120">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="0fd5c-121">Get 문</span><span class="sxs-lookup"><span data-stu-id="0fd5c-121">Get Statement</span></span>](get-statement.md)
- [<span data-ttu-id="0fd5c-122">Set 문</span><span class="sxs-lookup"><span data-stu-id="0fd5c-122">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="0fd5c-123">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="0fd5c-123">Operator Statement</span></span>](operator-statement.md)
- [<span data-ttu-id="0fd5c-124">Property Statement</span><span class="sxs-lookup"><span data-stu-id="0fd5c-124">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="0fd5c-125">Exit 문</span><span class="sxs-lookup"><span data-stu-id="0fd5c-125">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="0fd5c-126">Try...Catch...Finally 명령문</span><span class="sxs-lookup"><span data-stu-id="0fd5c-126">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
