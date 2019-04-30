---
title: Call 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 755443a99a1ad8b0430a76d2dba1ff27472d4c9d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945069"
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="ac4c0-102">Call 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac4c0-102">Call Statement (Visual Basic)</span></span>
<span data-ttu-id="ac4c0-103">컨트롤을 전송 하는 `Function`, `Sub`, 또는 동적 연결 라이브러리 (DLL) 프로시저.</span><span class="sxs-lookup"><span data-stu-id="ac4c0-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac4c0-104">구문</span><span class="sxs-lookup"><span data-stu-id="ac4c0-104">Syntax</span></span>  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="ac4c0-105">요소</span><span class="sxs-lookup"><span data-stu-id="ac4c0-105">Parts</span></span>  
|||
|---|---|
|`procedureName`|<span data-ttu-id="ac4c0-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="ac4c0-106">Required.</span></span> <span data-ttu-id="ac4c0-107">호출 프로시저의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ac4c0-107">Name of the procedure to call.</span></span>|
|`argumentList`|<span data-ttu-id="ac4c0-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ac4c0-108">Optional.</span></span> <span data-ttu-id="ac4c0-109">변수 또는 호출 될 때 프로시저에 전달 되는 인수를 나타내는 식의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ac4c0-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="ac4c0-110">여러 인수는 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac4c0-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="ac4c0-111">포함 하는 경우 `argumentList`를 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4c0-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="ac4c0-112">설명</span><span class="sxs-lookup"><span data-stu-id="ac4c0-112">Remarks</span></span>  
 <span data-ttu-id="ac4c0-113">사용할 수는 `Call` 키워드 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4c0-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="ac4c0-114">대부분의 프로시저 호출에이 키워드를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac4c0-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>  
  
 <span data-ttu-id="ac4c0-115">일반적으로 사용 하 여 `Call` 키워드 호출된 식 식별자로 시작 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac4c0-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="ac4c0-116">사용 된 `Call` 키워드 다른 용도로 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac4c0-116">Use of the `Call` keyword for other uses isn’t recommended.</span></span>  
  
 <span data-ttu-id="ac4c0-117">프로시저는 값을 반환 하는 경우는 `Call` 문을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4c0-117">If the procedure returns a value, the `Call` statement discards it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac4c0-118">예제</span><span class="sxs-lookup"><span data-stu-id="ac4c0-118">Example</span></span>  
 <span data-ttu-id="ac4c0-119">다음 코드는 두 가지 예제를 보여 줍니다. 여기서는 `Call` 키워드는 프로시저를 호출 하는 데 필요한 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4c0-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="ac4c0-120">두 예제에서는 호출된 식 식별자를 사용 하 여 시작 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac4c0-120">In both examples, the called expression doesn't start with an identifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a><span data-ttu-id="ac4c0-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="ac4c0-121">See also</span></span>

- [<span data-ttu-id="ac4c0-122">Function 문</span><span class="sxs-lookup"><span data-stu-id="ac4c0-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="ac4c0-123">Sub 문</span><span class="sxs-lookup"><span data-stu-id="ac4c0-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="ac4c0-124">Declare 문</span><span class="sxs-lookup"><span data-stu-id="ac4c0-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="ac4c0-125">람다 식</span><span class="sxs-lookup"><span data-stu-id="ac4c0-125">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
