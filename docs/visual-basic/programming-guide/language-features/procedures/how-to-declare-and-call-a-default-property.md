---
description: '자세한 정보: 방법: 기본 속성 선언 및 호출 Visual Basic'
title: '방법: 기본 속성 선언 및 호출'
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
ms.openlocfilehash: 2a0e82fe89bb89613996f613930ace1aa6e41b7f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472451"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="a3431-103">방법: Visual Basic에서 기본 속성 선언 및 호출</span><span class="sxs-lookup"><span data-stu-id="a3431-103">How to: Declare and Call a Default Property in Visual Basic</span></span>

<span data-ttu-id="a3431-104">*기본 속성* 은 코드에서 지정 하지 않고 액세스할 수 있는 클래스 또는 구조체 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-104">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="a3431-105">호출 코드에서 클래스 또는 구조체의 이름을 지정할 수 있지만 속성이 아닌 경우, 컨텍스트는 속성에 대 한 액세스를 허용 하 고, Visual Basic는 해당 클래스 또는 구조체의 기본 속성 (있는 경우)에 대 한 액세스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-105">When calling code names a class or structure but not a property, and the context allows access to a property, Visual Basic resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="a3431-106">클래스 또는 구조체에는 최대 하나의 기본 속성만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-106">A class or structure can have at most one default property.</span></span> <span data-ttu-id="a3431-107">그러나 기본 속성을 오버 로드 하 고 둘 이상의 버전을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-107">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="a3431-108">자세한 내용은 [기본값](../../../language-reference/modifiers/default.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a3431-108">For more information, see [Default](../../../language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="a3431-109">기본 속성을 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="a3431-109">To declare a default property</span></span>  
  
1. <span data-ttu-id="a3431-110">일반적인 방법으로 속성을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-110">Declare the property in the normal way.</span></span> <span data-ttu-id="a3431-111">또는 키워드를 지정 하지 마십시오 `Shared` `Private` .</span><span class="sxs-lookup"><span data-stu-id="a3431-111">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2. <span data-ttu-id="a3431-112">`Default`속성 선언에 키워드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-112">Include the `Default` keyword in the property declaration.</span></span>  
  
3. <span data-ttu-id="a3431-113">속성에 대 한 매개 변수를 하나 이상 지정 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a3431-113">Specify at least one parameter for the property.</span></span> <span data-ttu-id="a3431-114">하나 이상의 인수를 사용 하지 않는 기본 속성을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-114">You cannot define a default property that does not take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#17)]  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="a3431-115">기본 속성을 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="a3431-115">To call a default property</span></span>  
  
1. <span data-ttu-id="a3431-116">포함 하는 클래스 또는 구조체 형식의 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-116">Declare a variable of the containing class or structure type.</span></span>  
  
     [!code-vb[VbVbcnProcedures#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#16)]  
  
2. <span data-ttu-id="a3431-117">일반적으로 속성 이름을 포함 하는 식에는 변수 이름만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-117">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     [!code-vb[VbVbcnProcedures#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#21)]  
  
3. <span data-ttu-id="a3431-118">변수 이름 뒤에 인수 목록이 괄호로 묶여 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-118">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="a3431-119">기본 속성은 하나 이상의 인수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-119">A default property must take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#20)]  
  
4. <span data-ttu-id="a3431-120">기본 속성 값을 검색 하려면 인수 목록과 함께 변수 이름을 식에 사용 하거나 대입문에 등호 () 기호를 사용 합니다 `=` .</span><span class="sxs-lookup"><span data-stu-id="a3431-120">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#15)]  
  
5. <span data-ttu-id="a3431-121">기본 속성 값을 설정 하려면 인수 목록과 함께 변수 이름을 대입문의 왼쪽에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-121">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#14)]  
  
6. <span data-ttu-id="a3431-122">다른 속성에 액세스 하는 것 처럼 항상 기본 속성 이름을 변수 이름과 함께 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-122">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     [!code-vb[VbVbcnProcedures#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="a3431-123">예</span><span class="sxs-lookup"><span data-stu-id="a3431-123">Example</span></span>  

 <span data-ttu-id="a3431-124">다음 예제에서는 클래스에 대 한 기본 속성을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-124">The following example declares a default property on a class.</span></span>  
  
 [!code-vb[VbVbcnProcedures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="a3431-125">예</span><span class="sxs-lookup"><span data-stu-id="a3431-125">Example</span></span>  

 <span data-ttu-id="a3431-126">다음 예제에서는 클래스에서 기본 속성을 호출 하는 방법을 보여 줍니다 `myProperty` `class1` .</span><span class="sxs-lookup"><span data-stu-id="a3431-126">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="a3431-127">세 개의 대입문은에 값 `myProperty` 을 저장 하 고 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 호출은 값을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-127">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#13)]  
  
 <span data-ttu-id="a3431-128">기본 속성의 가장 일반적인 용도는 <xref:Microsoft.VisualBasic.Collection.Item%2A> 다양 한 컬렉션 클래스의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-128">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a3431-129">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="a3431-129">Robust Programming</span></span>  

 <span data-ttu-id="a3431-130">기본 속성은 소스 코드 문자를 조금 줄일 수 있지만 코드를 읽기 어렵게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-130">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="a3431-131">호출 코드가 클래스 또는 구조체를 사용 하는 데 익숙하지 않은 경우 클래스 또는 구조체 이름에 대 한 참조를 만들 때 참조가 클래스나 구조체 자체에 액세스 하는지 아니면 기본 속성에 액세스 하는지 여부를 확신할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-131">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="a3431-132">이로 인해 컴파일러 오류 또는 미묘한 런타임 논리 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-132">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="a3431-133">항상 [Option Strict 문을](../../../language-reference/statements/option-strict-statement.md) 사용 하 여 컴파일러 유형 검사를로 설정 하 여 기본 속성 오류의 가능성을 약간 줄일 수 있습니다 `On` .</span><span class="sxs-lookup"><span data-stu-id="a3431-133">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="a3431-134">코드에서 미리 정의 된 클래스 또는 구조체를 사용 하려는 경우 기본 속성이 있는지 여부를 확인 하 고, 해당 하는 경우 이름을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-134">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="a3431-135">이러한 단점 때문에 기본 속성을 정의 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-135">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="a3431-136">코드 가독성을 위해 기본 속성도 항상 모든 속성을 명시적으로 참조 하는 것도 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3431-136">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3431-137">추가 정보</span><span class="sxs-lookup"><span data-stu-id="a3431-137">See also</span></span>

- [<span data-ttu-id="a3431-138">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="a3431-138">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="a3431-139">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="a3431-139">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="a3431-140">Property Statement</span><span class="sxs-lookup"><span data-stu-id="a3431-140">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="a3431-141">기본값</span><span class="sxs-lookup"><span data-stu-id="a3431-141">Default</span></span>](../../../language-reference/modifiers/default.md)
- [<span data-ttu-id="a3431-142">Visual Basic에서 속성과 변수의 차이점</span><span class="sxs-lookup"><span data-stu-id="a3431-142">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="a3431-143">방법: 속성 만들기</span><span class="sxs-lookup"><span data-stu-id="a3431-143">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="a3431-144">방법: 액세스 수준이 혼합된 속성 선언</span><span class="sxs-lookup"><span data-stu-id="a3431-144">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="a3431-145">방법: 속성 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="a3431-145">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="a3431-146">방법: 속성 값 입력</span><span class="sxs-lookup"><span data-stu-id="a3431-146">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="a3431-147">방법: 속성에서 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="a3431-147">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
