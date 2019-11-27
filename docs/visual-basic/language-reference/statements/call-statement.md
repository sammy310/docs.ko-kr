---
title: Call 문
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 7de194ea23827e08c49f4519c1000708a4bd91b4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350155"
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="af157-102">Call 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af157-102">Call Statement (Visual Basic)</span></span>

<span data-ttu-id="af157-103">`Function`, `Sub`또는 DLL (동적 연결 라이브러리) 프로시저로 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="af157-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af157-104">구문</span><span class="sxs-lookup"><span data-stu-id="af157-104">Syntax</span></span>  
  
```vb  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="af157-105">요소</span><span class="sxs-lookup"><span data-stu-id="af157-105">Parts</span></span>  

|||
|---|---|
|`procedureName`|<span data-ttu-id="af157-106">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="af157-106">Required.</span></span> <span data-ttu-id="af157-107">호출할 프로시저의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="af157-107">Name of the procedure to call.</span></span>|
|`argumentList`|<span data-ttu-id="af157-108">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="af157-108">Optional.</span></span> <span data-ttu-id="af157-109">프로시저를 호출할 때 프로시저에 전달 되는 인수를 나타내는 변수나 식의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="af157-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="af157-110">여러 인수를 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="af157-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="af157-111">`argumentList`를 포함 하는 경우 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af157-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="af157-112">주의</span><span class="sxs-lookup"><span data-stu-id="af157-112">Remarks</span></span>

 <span data-ttu-id="af157-113">프로시저를 호출할 때 `Call` 키워드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af157-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="af157-114">대부분의 프로시저 호출의 경우에는이 키워드를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af157-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>

 <span data-ttu-id="af157-115">일반적으로 호출 된 식이 식별자로 시작 하지 않는 경우 `Call` 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="af157-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="af157-116">다른 용도로는 `Call` 키워드를 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="af157-116">Use of the `Call` keyword for other uses isn't recommended.</span></span>

 <span data-ttu-id="af157-117">프로시저에서 값을 반환 하는 경우 `Call` 문은 해당 값을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="af157-117">If the procedure returns a value, the `Call` statement discards it.</span></span>

## <a name="example"></a><span data-ttu-id="af157-118">예제</span><span class="sxs-lookup"><span data-stu-id="af157-118">Example</span></span>

 <span data-ttu-id="af157-119">다음 코드에서는 `Call` 키워드가 프로시저를 호출 하는 데 필요한 두 가지 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="af157-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="af157-120">두 예제에서 호출 된 식은 식별자로 시작 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af157-120">In both examples, the called expression doesn't start with an identifier.</span></span>

 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a><span data-ttu-id="af157-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af157-121">See also</span></span>

- [<span data-ttu-id="af157-122">Function 문</span><span class="sxs-lookup"><span data-stu-id="af157-122">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="af157-123">Sub 문</span><span class="sxs-lookup"><span data-stu-id="af157-123">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="af157-124">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="af157-124">Declare Statement</span></span>](declare-statement.md)
- [<span data-ttu-id="af157-125">람다 식</span><span class="sxs-lookup"><span data-stu-id="af157-125">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
