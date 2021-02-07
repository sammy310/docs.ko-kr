---
description: '자세한 정보: Call 문 (Visual Basic)'
title: Call 문
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 70e6c109621c3710ad9476a952e9c384a142ba3d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99674014"
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="25823-103">Call 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25823-103">Call Statement (Visual Basic)</span></span>

<span data-ttu-id="25823-104">`Function`, `Sub` 또는 DLL (동적 연결 라이브러리) 프로시저로 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="25823-104">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25823-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="25823-105">Syntax</span></span>  
  
```vb  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="25823-106">부분</span><span class="sxs-lookup"><span data-stu-id="25823-106">Parts</span></span>  

|||
|---|---|
|`procedureName`|<span data-ttu-id="25823-107">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="25823-107">Required.</span></span> <span data-ttu-id="25823-108">호출할 프로시저의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="25823-108">Name of the procedure to call.</span></span>|
|`argumentList`|<span data-ttu-id="25823-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="25823-109">Optional.</span></span> <span data-ttu-id="25823-110">프로시저를 호출할 때 프로시저에 전달 되는 인수를 나타내는 변수나 식의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="25823-110">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="25823-111">여러 인수를 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="25823-111">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="25823-112">을 포함 하는 경우 `argumentList` 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25823-112">If you include `argumentList`, you must enclose it in parentheses.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="25823-113">설명</span><span class="sxs-lookup"><span data-stu-id="25823-113">Remarks</span></span>

 <span data-ttu-id="25823-114">프로시저를 호출할 때 키워드를 사용할 수 있습니다 `Call` .</span><span class="sxs-lookup"><span data-stu-id="25823-114">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="25823-115">대부분의 프로시저 호출의 경우에는이 키워드를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25823-115">For most procedure calls, you aren’t required to use this  keyword.</span></span>

 <span data-ttu-id="25823-116">일반적으로 `Call` 호출 된 식이 식별자로 시작 하지 않는 경우 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="25823-116">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="25823-117">`Call`다른 용도로는 키워드를 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="25823-117">Use of the `Call` keyword for other uses isn't recommended.</span></span>

 <span data-ttu-id="25823-118">프로시저에서 값을 반환 하는 경우 문이 해당 값을 `Call` 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="25823-118">If the procedure returns a value, the `Call` statement discards it.</span></span>

## <a name="example"></a><span data-ttu-id="25823-119">예제</span><span class="sxs-lookup"><span data-stu-id="25823-119">Example</span></span>

 <span data-ttu-id="25823-120">다음 코드는 `Call` 키워드가 프로시저를 호출 하는 데 필요한 두 가지 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25823-120">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="25823-121">두 예제에서 호출 된 식은 식별자로 시작 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25823-121">In both examples, the called expression doesn't start with an identifier.</span></span>

 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a><span data-ttu-id="25823-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25823-122">See also</span></span>

- [<span data-ttu-id="25823-123">Function 문</span><span class="sxs-lookup"><span data-stu-id="25823-123">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="25823-124">Sub 문</span><span class="sxs-lookup"><span data-stu-id="25823-124">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="25823-125">Declare 문</span><span class="sxs-lookup"><span data-stu-id="25823-125">Declare Statement</span></span>](declare-statement.md)
- [<span data-ttu-id="25823-126">람다 식</span><span class="sxs-lookup"><span data-stu-id="25823-126">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
