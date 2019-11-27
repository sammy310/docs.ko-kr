---
title: '방법: 액세스 수준이 혼합된 속성 선언'
ms.date: 07/20/2015
helpviewer_keywords:
- access levels [Visual Basic], properties
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- mixed access levels
- Visual Basic code, properties
- properties [Visual Basic], access levels
- Property statement [Visual Basic], declaring mixed access levels
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
ms.openlocfilehash: d74e23f33fbf7d9d29ab84b9b1bd4fc08863ac48
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349692"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a><span data-ttu-id="5a5d2-102">방법: 액세스 수준이 혼합된 속성 선언(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a5d2-102">How to: Declare a Property with Mixed Access Levels (Visual Basic)</span></span>
<span data-ttu-id="5a5d2-103">속성의 `Get` 및 `Set` 프로시저에 서로 다른 액세스 수준을 설정 하려면 `Property` 문에서 보다 관대 한 수준을 사용 하 고 `Get` 또는 `Set` 문에서 더 제한적인 수준을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a5d2-103">If you want the `Get` and `Set` procedures on a property to have different access levels, you can use the more permissive level in the `Property` statement and the more restrictive level in either the `Get` or `Set` statement.</span></span> <span data-ttu-id="5a5d2-104">코드의 특정 부분에서 속성 값을 가져올 수 있도록 하 고 코드의 특정 부분에서 값을 변경할 수 있도록 하려면 속성에 대해 혼합 된 액세스 수준을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a5d2-104">You use mixed access levels on a property when you want certain parts of the code to be able to get the property's value, and certain other parts of the code to be able to change the value.</span></span>  
  
 <span data-ttu-id="5a5d2-105">액세스 수준에 대 한 자세한 내용은 [Visual Basic의 액세스 수준](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5a5d2-105">For more information on access levels, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a><span data-ttu-id="5a5d2-106">혼합 된 액세스 수준으로 속성을 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="5a5d2-106">To declare a property with mixed access levels</span></span>  
  
1. <span data-ttu-id="5a5d2-107">일반적인 방법으로 속성을 선언 하 고 `Property` 문에서 덜 제한적인 액세스 수준 (예: `Public`)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a5d2-107">Declare the property in the normal way, and specify the less restrictive access level (such as `Public`) in the `Property` statement.</span></span>  
  
2. <span data-ttu-id="5a5d2-108">더 제한적인 액세스 수준 (예: `Friend`)을 지정 하는 `Get` 또는 `Set` 프로시저를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a5d2-108">Declare either the `Get` or the `Set` procedure specifying the more restrictive access level (such as `Friend`).</span></span>  
  
3. <span data-ttu-id="5a5d2-109">다른 속성 프로시저에 대 한 액세스 수준을 지정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="5a5d2-109">Do not specify an access level on the other property procedure.</span></span> <span data-ttu-id="5a5d2-110">`Property` 문에서 선언 된 액세스 수준으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a5d2-110">It assumes the access level declared in the `Property` statement.</span></span> <span data-ttu-id="5a5d2-111">속성 프로시저 중 하나에 대해서만 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a5d2-111">You can restrict access on only one of the property procedures.</span></span>  
  
     [!code-vb[VbVbcnProcedures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#10)]  
  
     <span data-ttu-id="5a5d2-112">위의 예제에서 `Get` 프로시저는 속성 자체와 동일한 `Protected` 액세스를 가지 며 `Set` 프로시저에는 `Private` 액세스 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a5d2-112">In the preceding example, the `Get` procedure has the same `Protected` access as the property itself, while the `Set` procedure has `Private` access.</span></span> <span data-ttu-id="5a5d2-113">`employee`에서 파생 된 클래스는 `salary` 값을 읽을 수 있지만 `employee` 클래스만이 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a5d2-113">A class derived from `employee` can read the `salary` value, but only the `employee` class can set it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a5d2-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a5d2-114">See also</span></span>

- [<span data-ttu-id="5a5d2-115">절차</span><span class="sxs-lookup"><span data-stu-id="5a5d2-115">Procedures</span></span>](./index.md)
- [<span data-ttu-id="5a5d2-116">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="5a5d2-116">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="5a5d2-117">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="5a5d2-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="5a5d2-118">Property 문</span><span class="sxs-lookup"><span data-stu-id="5a5d2-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="5a5d2-119">Visual Basic에서 속성과 변수의 차이점</span><span class="sxs-lookup"><span data-stu-id="5a5d2-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="5a5d2-120">방법: 속성 만들기</span><span class="sxs-lookup"><span data-stu-id="5a5d2-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="5a5d2-121">방법: 속성 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="5a5d2-121">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="5a5d2-122">방법: Visual Basic에서 기본 속성 선언 및 호출</span><span class="sxs-lookup"><span data-stu-id="5a5d2-122">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="5a5d2-123">방법: 속성 값 입력</span><span class="sxs-lookup"><span data-stu-id="5a5d2-123">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="5a5d2-124">방법: 속성에서 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="5a5d2-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
