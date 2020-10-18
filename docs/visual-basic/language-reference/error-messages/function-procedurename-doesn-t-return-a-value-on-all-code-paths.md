---
title: "'<procedurename>' 함수가 일부 코드 경로에 대해서만 값을 반환합니다."
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: 19b305e337767dfb34718aed7b665f142851bd36
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163365"
---
# <a name="bc42105-function-procedurename-doesnt-return-a-value-on-all-code-paths"></a><span data-ttu-id="61ba5-102">BC42105: ' \<procedurename> ' 함수가 일부 코드 경로에 대 한 값을 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61ba5-102">BC42105: Function '\<procedurename>' doesn't return a value on all code paths</span></span>

<span data-ttu-id="61ba5-103">' \<procedurename> ' 함수가 일부 코드 경로에 대해서만 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ba5-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="61ba5-104">' Return ' 문이 있나요?</span><span class="sxs-lookup"><span data-stu-id="61ba5-104">Are you missing a 'Return' statement?</span></span>

 <span data-ttu-id="61ba5-105">`Function`프로시저에 해당 코드를 통해 값을 반환 하지 않는 경로가 하나 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ba5-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>

 <span data-ttu-id="61ba5-106">다음과 같은 방법으로 프로시저에서 값을 반환할 수 있습니다 `Function` .</span><span class="sxs-lookup"><span data-stu-id="61ba5-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>

- <span data-ttu-id="61ba5-107">[반환 문에](../statements/return-statement.md)값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ba5-107">Include the value in a [Return Statement](../statements/return-statement.md).</span></span>

- <span data-ttu-id="61ba5-108">프로시저 이름에 값을 할당 한 `Function` 다음 `Exit Function` 문을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ba5-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>

- <span data-ttu-id="61ba5-109">프로시저 이름에 값을 할당 한 `Function` 다음 `End Function` 문을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ba5-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>

 <span data-ttu-id="61ba5-110">컨트롤이 또는로 전달 `Exit Function` `End Function` 되 고 프로시저 이름에 값을 할당 하지 않은 경우 프로시저는 반환 데이터 형식의 기본값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ba5-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="61ba5-111">자세한 내용은 [함수 문의](../statements/function-statement.md)"Behavior"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="61ba5-111">For more information, see "Behavior" in [Function Statement](../statements/function-statement.md).</span></span>

 <span data-ttu-id="61ba5-112">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="61ba5-112">By default, this message is a warning.</span></span> <span data-ttu-id="61ba5-113">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61ba5-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="61ba5-114">**오류 ID:** BC42105</span><span class="sxs-lookup"><span data-stu-id="61ba5-114">**Error ID:** BC42105</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="61ba5-115">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="61ba5-115">To correct this error</span></span>

- <span data-ttu-id="61ba5-116">제어 흐름 논리를 확인 하 고 반환을 발생 시키는 모든 문 앞에 값을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ba5-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>

     <span data-ttu-id="61ba5-117">항상 문을 사용 하는 경우 프로시저의 모든 반환에서 값을 반환 하도록 보장 하는 것이 더 쉽습니다 `Return` .</span><span class="sxs-lookup"><span data-stu-id="61ba5-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="61ba5-118">이 작업을 수행 하는 경우 앞의 마지막 문이 문 이어야 합니다 `End Function` `Return` .</span><span class="sxs-lookup"><span data-stu-id="61ba5-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="61ba5-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61ba5-119">See also</span></span>

- [<span data-ttu-id="61ba5-120">함수 프로시저</span><span class="sxs-lookup"><span data-stu-id="61ba5-120">Function Procedures</span></span>](../../programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="61ba5-121">Function 문</span><span class="sxs-lookup"><span data-stu-id="61ba5-121">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="61ba5-122">프로젝트 디자이너, 컴파일 페이지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61ba5-122">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
