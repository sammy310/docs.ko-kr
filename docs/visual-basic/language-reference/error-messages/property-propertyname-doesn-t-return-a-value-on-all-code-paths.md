---
title: "'<propertyname>' 속성이 일부 코드 경로에 대해서만 값을 반환합니다."
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: a535a6b951dc9872109527f78d7de5f3fcdd3292
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821883"
---
# <a name="property-propertyname-doesnt-return-a-value-on-all-code-paths"></a><span data-ttu-id="3031c-102">속성 '\<propertyname >' 일부 코드 경로의 값을 반환 하지 않습니다</span><span class="sxs-lookup"><span data-stu-id="3031c-102">Property '\<propertyname>' doesn't return a value on all code paths</span></span>
<span data-ttu-id="3031c-103">속성 '\<propertyname >' 일부 코드 경로의 값을 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-103">Property '\<propertyname>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="3031c-104">이 결과를 사용하면 런타임에 null 참조 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-104">A null reference exception could occur at run time when the result is used.</span></span>  
  
 <span data-ttu-id="3031c-105">속성 `Get` 프로시저 값을 반환 하지 않는 해당 코드를 통해 하나 이상의 경로가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-105">A property `Get` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="3031c-106">속성에서 값을 반환할 수 있습니다 `Get` 다음 방법 중 하나에서 프로시저:</span><span class="sxs-lookup"><span data-stu-id="3031c-106">You can return a value from a property `Get` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="3031c-107">속성 이름에 값을 할당 하 고 다음을 수행할는 `Exit Property` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-107">Assign the value to the property name and then perform an `Exit Property` statement.</span></span>  
  
-   <span data-ttu-id="3031c-108">속성 이름에 값을 할당 하 고 다음을 수행 합니다 `End Get` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-108">Assign the value to the property name and then perform the `End Get` statement.</span></span>  
  
-   <span data-ttu-id="3031c-109">값을 포함 한 [Return 문이](../../../visual-basic/language-reference/statements/return-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-109">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="3031c-110">컨트롤을 전달 하는 경우 `Exit Property` 또는 `End Get` 속성 이름에 값을 할당 하지 않은 하 고는 `Get` 프로시저 속성의 데이터 형식의 기본 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-110">If control passes to `Exit Property` or `End Get` and you have not assigned any value to the property name, the `Get` procedure returns the default value of the property's data type.</span></span> <span data-ttu-id="3031c-111">자세한 내용은 "동작"를 참조 하세요 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="3031c-112">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-112">By default, this message is a warning.</span></span> <span data-ttu-id="3031c-113">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3031c-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="3031c-114">**오류 ID:** BC42107</span><span class="sxs-lookup"><span data-stu-id="3031c-114">**Error ID:** BC42107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3031c-115">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="3031c-115">To correct this error</span></span>  
  
-   <span data-ttu-id="3031c-116">제어 흐름 논리를 확인 하 고 반환 하는 모든 문 앞에 값을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="3031c-117">항상 사용 하는 경우 프로시저에서 모든 반환 값을 반환 하는 데 쉽습니다는 `Return` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="3031c-118">이렇게 하면, 앞의 마지막 문이 `End Get` 이어야 합니다는 `Return` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-118">If you do this, the last statement before `End Get` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3031c-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="3031c-119">See also</span></span>

- [<span data-ttu-id="3031c-120">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="3031c-120">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="3031c-121">Property 문</span><span class="sxs-lookup"><span data-stu-id="3031c-121">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="3031c-122">Get 문</span><span class="sxs-lookup"><span data-stu-id="3031c-122">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
