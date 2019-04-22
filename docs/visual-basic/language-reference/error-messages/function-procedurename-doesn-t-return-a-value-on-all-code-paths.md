---
title: "'<procedurename>' 함수가 일부 코드 경로에 대해서만 값을 반환합니다."
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: badcfea4f24ba3858071e02ba47b8f77ab557f88
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58824834"
---
# <a name="function-procedurename-doesnt-return-a-value-on-all-code-paths"></a><span data-ttu-id="339f4-102">함수 '\<procedurename >' 일부 코드 경로의 값을 반환 하지 않습니다</span><span class="sxs-lookup"><span data-stu-id="339f4-102">Function '\<procedurename>' doesn't return a value on all code paths</span></span>
<span data-ttu-id="339f4-103">함수 '\<procedurename >' 일부 코드 경로의 값을 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="339f4-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="339f4-104">'Return' 문이 누락 되었습니까?</span><span class="sxs-lookup"><span data-stu-id="339f4-104">Are you missing a 'Return' statement?</span></span>  
  
 <span data-ttu-id="339f4-105">`Function` 프로시저 값을 반환 하지 않는 해당 코드를 통해 하나 이상의 경로가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="339f4-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="339f4-106">값을 반환할 수는 `Function` 다음 방법 중 하나에서 프로시저:</span><span class="sxs-lookup"><span data-stu-id="339f4-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="339f4-107">값을 포함 한 [Return 문이](../../../visual-basic/language-reference/statements/return-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="339f4-107">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
-   <span data-ttu-id="339f4-108">에 값을 할당 합니다 `Function` 프로시저 이름을 지정 하 고 다음을 수행할는 `Exit Function` 문.</span><span class="sxs-lookup"><span data-stu-id="339f4-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>  
  
-   <span data-ttu-id="339f4-109">에 값을 할당 합니다 `Function` 프로시저 이름을 지정 하 고 다음을 수행 합니다 `End Function` 문.</span><span class="sxs-lookup"><span data-stu-id="339f4-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>  
  
 <span data-ttu-id="339f4-110">컨트롤을 전달 하는 경우 `Exit Function` 또는 `End Function` 프로시저 이름에 값을 할당 하지 않은, 프로시저 반환 데이터 형식의 기본값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="339f4-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="339f4-111">자세한 내용은 "동작"를 참조 하세요 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="339f4-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="339f4-112">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="339f4-112">By default, this message is a warning.</span></span> <span data-ttu-id="339f4-113">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="339f4-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="339f4-114">**오류 ID:** BC42105</span><span class="sxs-lookup"><span data-stu-id="339f4-114">**Error ID:** BC42105</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="339f4-115">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="339f4-115">To correct this error</span></span>  
  
-   <span data-ttu-id="339f4-116">제어 흐름 논리를 확인 하 고 반환 하는 모든 문 앞에 값을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="339f4-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="339f4-117">항상 사용 하는 경우 프로시저에서 모든 반환 값을 반환 하는 데 쉽습니다는 `Return` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="339f4-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="339f4-118">이렇게 하면, 앞의 마지막 문이 `End Function` 이어야 합니다는 `Return` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="339f4-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="339f4-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="339f4-119">See also</span></span>

- [<span data-ttu-id="339f4-120">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="339f4-120">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="339f4-121">Function 문</span><span class="sxs-lookup"><span data-stu-id="339f4-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="339f4-122">프로젝트 디자이너, 컴파일 페이지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="339f4-122">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
