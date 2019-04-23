---
title: '방법: 속성 (Visual Basic) 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, properties
- properties [Visual Basic]
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
ms.openlocfilehash: 91f34de36e88724ccab21097bf54a4604f7eee37
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59306718"
---
# <a name="how-to-create-a-property-visual-basic"></a><span data-ttu-id="78449-102">방법: 속성 (Visual Basic) 만들기</span><span class="sxs-lookup"><span data-stu-id="78449-102">How to: Create a Property (Visual Basic)</span></span>
<span data-ttu-id="78449-103">속성 정의 간에 묶습니다를 `Property` 문 및 `End Property` 문.</span><span class="sxs-lookup"><span data-stu-id="78449-103">You enclose a property definition between a `Property` statement and an `End Property` statement.</span></span> <span data-ttu-id="78449-104">이 정의 내에서 정의 `Get` 프로시저는 `Set` 프로시저 중 하나 또는 둘 다.</span><span class="sxs-lookup"><span data-stu-id="78449-104">Within this definition you define a `Get` procedure, a `Set` procedure, or both.</span></span> <span data-ttu-id="78449-105">이러한 프로시저 내에서 모든 속성의 코드에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78449-105">All the property's code lies within these procedures.</span></span>  
  
 <span data-ttu-id="78449-106">합니다 `Get` 속성의 값을 검색 하는 절차 및 `Set` 프로시저는 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="78449-106">The `Get` procedure retrieves the property's value, and the `Set` procedure stores a value.</span></span> <span data-ttu-id="78449-107">속성이 읽기/쓰기 액세스를 하려는 경우 두 프로시저를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78449-107">If you want the property to have read/write access, you must define both procedures.</span></span> <span data-ttu-id="78449-108">읽기 전용 속성에 대 한 정의 `Get`, 고 쓰기 전용 속성에 대 한 정의 `Set`합니다.</span><span class="sxs-lookup"><span data-stu-id="78449-108">For a read-only property, you define only `Get`, and for a write-only property, you define only `Set`.</span></span>  
  
### <a name="to-create-a-property"></a><span data-ttu-id="78449-109">속성을 만들려면</span><span class="sxs-lookup"><span data-stu-id="78449-109">To create a property</span></span>  
  
1. <span data-ttu-id="78449-110">외부 속성 또는 프로시저를 사용 하 여는 [Property 문](../../../../visual-basic/language-reference/statements/property-statement.md)고 뒤에 `End Property` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="78449-110">Outside any property or procedure, use a [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md), followed by an `End Property` statement.</span></span>  
  
2. <span data-ttu-id="78449-111">매개 변수를 사용 하는 속성, 경우에 따라는 `Property` 키워드 프로시저 이름이 매개 변수 목록 괄호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="78449-111">If the property takes parameters, follow the `Property` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>  
  
3. <span data-ttu-id="78449-112">괄호 다음에 `As` 절 속성의 값의 데이터 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78449-112">Follow the parentheses with an `As` clause to specify the data type of the property's value.</span></span> <span data-ttu-id="78449-113">쓰기 전용 속성에도 데이터 형식을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78449-113">You must specify the data type even for a write-only property.</span></span>  
  
4. <span data-ttu-id="78449-114">추가 `Get` 고 `Set` 프로시저를 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="78449-114">Add `Get` and `Set` procedures, as appropriate.</span></span> <span data-ttu-id="78449-115">다음 지침을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="78449-115">See the following directions.</span></span>  
  
### <a name="to-create-a-get-procedure-that-retrieves-a-property-value"></a><span data-ttu-id="78449-116">속성 값을 검색 하는 Get 프로시저를 만들려면</span><span class="sxs-lookup"><span data-stu-id="78449-116">To create a Get procedure that retrieves a property value</span></span>  
  
1. <span data-ttu-id="78449-117">간에 `Property` 및 `End Property` 문을 작성을 [Get 문을](../../../../visual-basic/language-reference/statements/get-statement.md)뒤를 `End Get` 문.</span><span class="sxs-lookup"><span data-stu-id="78449-117">Between the `Property` and `End Property` statements, write a [Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md), followed by an `End Get` statement.</span></span> <span data-ttu-id="78449-118">모든 매개 변수를 정의할 필요가 없습니다를 `Get` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="78449-118">You do not need to define any parameters for the `Get` procedure.</span></span>  
  
2. <span data-ttu-id="78449-119">사이의 속성의 값을 검색 하는 코드 문을 배치 합니다 `Get` 및 `End Get` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="78449-119">Place the code statements to retrieve the property's value between the `Get` and `End Get` statements.</span></span> <span data-ttu-id="78449-120">이 코드는 다른 계산 및 생성 하 고 속성의 값을 반환 하는 것 외에도 데이터 조작에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78449-120">This code can include other calculations and data manipulations in addition to generating and returning the property's value.</span></span>  
  
3. <span data-ttu-id="78449-121">사용 하 여를 `Return` 문을 호출 코드에 속성의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="78449-121">Use a `Return` statement to return the property's value to the calling code.</span></span>  
  
 <span data-ttu-id="78449-122">작성 해야 합니다는 `Get` 읽기 / 쓰기 속성 및 읽기 전용 속성에 대 한 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="78449-122">You must write a `Get` procedure for a read-write property and for a read-only property.</span></span> <span data-ttu-id="78449-123">정의할 수 없습니다는 `Get` 쓰기 전용 속성에 대 한 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="78449-123">You must not define a `Get` procedure for a write-only property.</span></span>  
  
### <a name="to-create-a-set-procedure-that-writes-a-propertys-value"></a><span data-ttu-id="78449-124">속성 값을 쓰는 집합 프로시저를 만들려면</span><span class="sxs-lookup"><span data-stu-id="78449-124">To create a Set procedure that writes a property's value</span></span>  
  
1. <span data-ttu-id="78449-125">간에 `Property` 및 `End Property` 문을 작성을 [Set 문을](../../../../visual-basic/language-reference/statements/set-statement.md)뒤를 `End Set` 문.</span><span class="sxs-lookup"><span data-stu-id="78449-125">Between the `Property` and `End Property` statements, write a [Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md), followed by an `End Set` statement.</span></span>  
  
2. <span data-ttu-id="78449-126">에 `Set` 문을 따릅니다는 `Set` 매개 변수 목록 괄호로 묶어 키워드.</span><span class="sxs-lookup"><span data-stu-id="78449-126">In the `Set` statement, follow the `Set` keyword with a parameter list in parentheses.</span></span> <span data-ttu-id="78449-127">이 매개 변수 목록 호출 코드에서 전달 된 값에 대 한 하나 이상의 값 매개 변수를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78449-127">This parameter list must include at least a value parameter for the value passed by the calling code.</span></span> <span data-ttu-id="78449-128">이 값 매개 변수의 기본 이름은 `Value`, 하지만 해당 하는 경우 다른 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78449-128">The default name for this value parameter is `Value`, but you can use a different name if appropriate.</span></span> <span data-ttu-id="78449-129">Value 매개 변수 데이터 형식이 해당 속성과 같은 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78449-129">The value parameter must have the same data type as the property itself.</span></span>  
  
3. <span data-ttu-id="78449-130">값은 속성을 저장 하는 코드 문을 배치 합니다 `Set` 및 `End Set` 문.</span><span class="sxs-lookup"><span data-stu-id="78449-130">Place the code statements to store a value in the property between the `Set` and `End Set` statements.</span></span> <span data-ttu-id="78449-131">이 코드는 다른 계산 및 유효성 검사 및 속성의 값을 저장 하는 것 외에도 데이터 조작에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78449-131">This code can include other calculations and data manipulations in addition to validating and storing the property's value.</span></span>  
  
4. <span data-ttu-id="78449-132">호출 코드에서 제공 된 값에 적용할 값 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="78449-132">Use the value parameter to accept the value supplied by the calling code.</span></span> <span data-ttu-id="78449-133">대입문에서 직접이 값을 저장 하거나 저장할 내부 값을 계산 하는 식에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78449-133">You can either store this value directly in an assignment statement, or use it in an expression to calculate the internal value to be stored.</span></span>  
  
 <span data-ttu-id="78449-134">작성 해야 합니다는 `Set` 쓰기 전용 속성 및 읽기 / 쓰기 속성에 대 한 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="78449-134">You must write a `Set` procedure for a read-write property and for a write-only property.</span></span> <span data-ttu-id="78449-135">정의할 수 없습니다는 `Set` 읽기 전용 속성에 대 한 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="78449-135">You must not define a `Set` procedure for a read-only property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78449-136">예제</span><span class="sxs-lookup"><span data-stu-id="78449-136">Example</span></span>  
 <span data-ttu-id="78449-137">다음 예제에서는 두 구성 요소 이름, 첫 번째 이름과 마지막 이름으로 전체 이름을 저장 하는 읽기/쓰기 속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="78449-137">The following example creates a read/write property that stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="78449-138">호출 코드를 읽을 때 `fullName`, `Get` 프로시저는 두 구성 요소 이름을 결합을 전체 이름을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="78449-138">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="78449-139">호출 코드에서 새 전체 이름으로 할당 하는 경우는 `Set` 프로시저 두 구성 요소 이름으로 중단 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="78449-139">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="78449-140">공간을 찾지 못하면, 모든 첫 번째 이름으로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="78449-140">If it does not find a space, it stores it all as the first name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]  
  
 <span data-ttu-id="78449-141">다음 예제에서는 속성 프로시저를 호출 하는 일반적인 `fullName`합니다.</span><span class="sxs-lookup"><span data-stu-id="78449-141">The following example shows typical calls to the property procedures of `fullName`.</span></span> <span data-ttu-id="78449-142">속성 값을 설정 하는 첫 번째 호출 및 두 번째 호출에서 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="78449-142">The first call sets the property value and the second call retrieves it.</span></span>  
  
 [!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="78449-143">참고자료</span><span class="sxs-lookup"><span data-stu-id="78449-143">See also</span></span>

- [<span data-ttu-id="78449-144">절차</span><span class="sxs-lookup"><span data-stu-id="78449-144">Procedures</span></span>](./index.md)
- [<span data-ttu-id="78449-145">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="78449-145">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="78449-146">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="78449-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="78449-147">Visual Basic에서 속성과 변수의 차이점</span><span class="sxs-lookup"><span data-stu-id="78449-147">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="78449-148">방법: 액세스 수준이 혼합된 된 속성 선언</span><span class="sxs-lookup"><span data-stu-id="78449-148">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="78449-149">방법: 속성 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="78449-149">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="78449-150">방법: 선언 및 Visual Basic의 기본 속성을 호출</span><span class="sxs-lookup"><span data-stu-id="78449-150">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="78449-151">방법: 속성 값 입력</span><span class="sxs-lookup"><span data-stu-id="78449-151">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="78449-152">방법: 속성에서 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="78449-152">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
