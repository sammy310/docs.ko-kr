---
title: '방법: 선언 및 Visual Basic의 기본 속성을 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
ms.openlocfilehash: 9ca9a0ccdac3ac13429928233a0c09d58427ce74
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665769"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="a5137-102">방법: 선언 및 Visual Basic의 기본 속성을 호출</span><span class="sxs-lookup"><span data-stu-id="a5137-102">How to: Declare and Call a Default Property in Visual Basic</span></span>
<span data-ttu-id="a5137-103">A *속성의 기본값을* 지정 하지 않고 코드에 액세스할 수 있는 클래스 또는 구조체 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-103">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="a5137-104">코드 이름은 호출 하는 경우 클래스 또는 구조 및 제외 속성을 하 고 컨텍스트 속성에 대 한 액세스 허용, Visual Basic 있을 경우 해당 클래스 또는 구조체의 기본 속성에 대 한 액세스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-104">When calling code names a class or structure but not a property, and the context allows access to a property, Visual Basic resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="a5137-105">클래스 또는 구조체만 가질 수 있습니다 기본 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-105">A class or structure can have at most one default property.</span></span> <span data-ttu-id="a5137-106">그러나 기본 속성을 오버 로드할 수 있으며 둘 이상의 버전이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-106">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="a5137-107">자세한 내용은 [기본](../../../../visual-basic/language-reference/modifiers/default.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-107">For more information, see [Default](../../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="a5137-108">기본 속성을 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="a5137-108">To declare a default property</span></span>  
  
1. <span data-ttu-id="a5137-109">일반적인 방법으로 속성을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-109">Declare the property in the normal way.</span></span> <span data-ttu-id="a5137-110">지정 하지 않으면 합니다 `Shared` 또는 `Private` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-110">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2. <span data-ttu-id="a5137-111">포함 된 `Default` 속성 선언에서 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-111">Include the `Default` keyword in the property declaration.</span></span>  
  
3. <span data-ttu-id="a5137-112">속성에 대 한 하나 이상의 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-112">Specify at least one parameter for the property.</span></span> <span data-ttu-id="a5137-113">하나 이상의 인수를 사용 하지 않는 기본 속성을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-113">You cannot define a default property that does not take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#17)]  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="a5137-114">기본 속성을 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="a5137-114">To call a default property</span></span>  
  
1. <span data-ttu-id="a5137-115">포함 하는 클래스 또는 구조체 형식의 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-115">Declare a variable of the containing class or structure type.</span></span>  
  
     [!code-vb[VbVbcnProcedures#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#16)]  
  
2. <span data-ttu-id="a5137-116">일반적으로 포함 하는 속성 이름 식에 변수 이름만을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-116">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     [!code-vb[VbVbcnProcedures#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#21)]  
  
3. <span data-ttu-id="a5137-117">인수 목록의 괄호를 사용 하 여 변수 이름을 뒤에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-117">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="a5137-118">기본 속성을 하나 이상의 인수를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-118">A default property must take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#20)]  
  
4. <span data-ttu-id="a5137-119">기본 속성 값을 검색할 식 또는 등호 다음에 인수 목록을 사용 하 여 변수 이름으로 사용 (`=`) 대입문에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-119">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#15)]  
  
5. <span data-ttu-id="a5137-120">기본 속성 값을 설정 하려면 대입문의 왼쪽에는 인수 목록을 사용 하 여 변수 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-120">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#14)]  
  
6. <span data-ttu-id="a5137-121">다른 속성에 액세스 하는 것 처럼에 항상 기본 속성 이름은 변수 이름과 함께 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-121">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     [!code-vb[VbVbcnProcedures#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="a5137-122">예제</span><span class="sxs-lookup"><span data-stu-id="a5137-122">Example</span></span>  
 <span data-ttu-id="a5137-123">다음 예제에서는 클래스의 기본 속성을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-123">The following example declares a default property on a class.</span></span>  
  
 [!code-vb[VbVbcnProcedures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="a5137-124">예제</span><span class="sxs-lookup"><span data-stu-id="a5137-124">Example</span></span>  
 <span data-ttu-id="a5137-125">다음 예제에서는 기본 속성을 호출 하는 방법을 보여 줍니다 `myProperty` 클래스에 `class1`입니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-125">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="a5137-126">값을 저장 하는 세 가지 대입문 `myProperty`, 및 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 호출 값을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-126">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#13)]  
  
 <span data-ttu-id="a5137-127">기본 속성의 가장 일반적인 용도 <xref:Microsoft.VisualBasic.Collection.Item%2A> 다양 한 컬렉션 클래스의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-127">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a5137-128">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="a5137-128">Robust Programming</span></span>  
 <span data-ttu-id="a5137-129">기본 속성 소스 코드의 문자를 약간 저하 될 수 있습니다 하지만 코드를 더 읽기 어렵다고 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-129">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="a5137-130">클래스 또는 구조체 이름으로 참조 하는 경우 호출 코드에서 클래스 또는 구조체에 익숙하지 않은 경우 수 없습니다 특정 클래스 또는 구조체 자체를 기본 속성을 참조 하는 액세스 하는 여부.</span><span class="sxs-lookup"><span data-stu-id="a5137-130">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="a5137-131">이 경우 미묘한 런타임 논리 오류나 컴파일러 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-131">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="a5137-132">항상 사용 하 여 기본 속성 오류 가능성을 다소 줄일 수 있습니다 합니다 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 컴파일러 형식 검사를 설정 하려면 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-132">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="a5137-133">사용 하 여 미리 정의 된 클래스 또는 구조체 코드에서 결정 해야 기본 속성이 있는지 여부와 하려는 경우 해당 이름 이란 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-133">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="a5137-134">이러한 단점 때문에 기본 속성을 정의 하지 않는 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-134">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="a5137-135">코드의 가독성을 높이기 위해 항상 모든 속성에 명시적으로 참조할 수도도 기본 속성 해야 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5137-135">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5137-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="a5137-136">See also</span></span>

- [<span data-ttu-id="a5137-137">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="a5137-137">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="a5137-138">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="a5137-138">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="a5137-139">Property 문</span><span class="sxs-lookup"><span data-stu-id="a5137-139">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="a5137-140">기본</span><span class="sxs-lookup"><span data-stu-id="a5137-140">Default</span></span>](../../../../visual-basic/language-reference/modifiers/default.md)
- [<span data-ttu-id="a5137-141">Visual Basic에서 속성과 변수의 차이점</span><span class="sxs-lookup"><span data-stu-id="a5137-141">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="a5137-142">방법: 속성 만들기</span><span class="sxs-lookup"><span data-stu-id="a5137-142">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="a5137-143">방법: 액세스 수준이 혼합된 된 속성 선언</span><span class="sxs-lookup"><span data-stu-id="a5137-143">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="a5137-144">방법: 속성 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="a5137-144">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="a5137-145">방법: 속성 값 입력</span><span class="sxs-lookup"><span data-stu-id="a5137-145">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="a5137-146">방법: 속성에서 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="a5137-146">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
