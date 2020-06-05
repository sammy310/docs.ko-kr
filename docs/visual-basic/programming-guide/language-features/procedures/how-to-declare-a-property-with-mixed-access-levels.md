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
ms.openlocfilehash: f0f7aba25888544dfcc093906850ae7ada621182
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388247"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a><span data-ttu-id="6b6c9-102">방법: 액세스 수준이 혼합된 속성 선언(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b6c9-102">How to: Declare a Property with Mixed Access Levels (Visual Basic)</span></span>
<span data-ttu-id="6b6c9-103">`Get` `Set` 속성의 및 프로시저에 서로 다른 액세스 수준을 설정 하려면 문에 보다 관대 한 수준을 사용 하 `Property` 고 또는 문에서 더 제한적인 수준을 사용할 수 있습니다 `Get` `Set` .</span><span class="sxs-lookup"><span data-stu-id="6b6c9-103">If you want the `Get` and `Set` procedures on a property to have different access levels, you can use the more permissive level in the `Property` statement and the more restrictive level in either the `Get` or `Set` statement.</span></span> <span data-ttu-id="6b6c9-104">코드의 특정 부분에서 속성 값을 가져올 수 있도록 하 고 코드의 특정 부분에서 값을 변경할 수 있도록 하려면 속성에 대해 혼합 된 액세스 수준을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6c9-104">You use mixed access levels on a property when you want certain parts of the code to be able to get the property's value, and certain other parts of the code to be able to change the value.</span></span>  
  
 <span data-ttu-id="6b6c9-105">액세스 수준에 대 한 자세한 내용은 [Visual Basic의 액세스 수준](../declared-elements/access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6b6c9-105">For more information on access levels, see [Access levels in Visual Basic](../declared-elements/access-levels.md).</span></span>  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a><span data-ttu-id="6b6c9-106">혼합 된 액세스 수준으로 속성을 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="6b6c9-106">To declare a property with mixed access levels</span></span>  
  
1. <span data-ttu-id="6b6c9-107">일반적인 방법으로 속성을 선언 하 고 문에서 덜 제한적인 액세스 수준 (예:)을 지정 합니다 `Public` `Property` .</span><span class="sxs-lookup"><span data-stu-id="6b6c9-107">Declare the property in the normal way, and specify the less restrictive access level (such as `Public`) in the `Property` statement.</span></span>  
  
2. <span data-ttu-id="6b6c9-108">`Get` `Set` 보다 제한적인 액세스 수준을 지정 하는 또는 프로시저를 선언 합니다 (예: `Friend` ).</span><span class="sxs-lookup"><span data-stu-id="6b6c9-108">Declare either the `Get` or the `Set` procedure specifying the more restrictive access level (such as `Friend`).</span></span>  
  
3. <span data-ttu-id="6b6c9-109">다른 속성 프로시저에 대 한 액세스 수준을 지정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="6b6c9-109">Do not specify an access level on the other property procedure.</span></span> <span data-ttu-id="6b6c9-110">이 클래스는 문에 선언 된 액세스 수준을 전제로 `Property` 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6c9-110">It assumes the access level declared in the `Property` statement.</span></span> <span data-ttu-id="6b6c9-111">속성 프로시저 중 하나에 대해서만 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b6c9-111">You can restrict access on only one of the property procedures.</span></span>  
  
     [!code-vb[VbVbcnProcedures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#10)]  
  
     <span data-ttu-id="6b6c9-112">위의 예에서는 프로시저에 `Get` `Protected` 액세스 하는 동안 속성 자체와 동일한 액세스 권한을 가집니다 `Set` `Private` .</span><span class="sxs-lookup"><span data-stu-id="6b6c9-112">In the preceding example, the `Get` procedure has the same `Protected` access as the property itself, while the `Set` procedure has `Private` access.</span></span> <span data-ttu-id="6b6c9-113">에서 파생 된 클래스는 `employee` `salary` 값을 읽을 수 있지만 클래스 에서만 값을 `employee` 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b6c9-113">A class derived from `employee` can read the `salary` value, but only the `employee` class can set it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b6c9-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b6c9-114">See also</span></span>

- [<span data-ttu-id="6b6c9-115">절차</span><span class="sxs-lookup"><span data-stu-id="6b6c9-115">Procedures</span></span>](./index.md)
- [<span data-ttu-id="6b6c9-116">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="6b6c9-116">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="6b6c9-117">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="6b6c9-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="6b6c9-118">Property Statement</span><span class="sxs-lookup"><span data-stu-id="6b6c9-118">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="6b6c9-119">Visual Basic에서 속성과 변수의 차이점</span><span class="sxs-lookup"><span data-stu-id="6b6c9-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="6b6c9-120">방법: 속성 만들기</span><span class="sxs-lookup"><span data-stu-id="6b6c9-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="6b6c9-121">방법: 속성 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="6b6c9-121">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="6b6c9-122">방법: Visual Basic에서 기본 속성 선언 및 호출</span><span class="sxs-lookup"><span data-stu-id="6b6c9-122">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="6b6c9-123">방법: 속성 값 입력</span><span class="sxs-lookup"><span data-stu-id="6b6c9-123">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="6b6c9-124">방법: 속성에서 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="6b6c9-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
