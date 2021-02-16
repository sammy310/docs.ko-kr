---
description: '자세한 정보: 연습: 인터페이스 만들기 및 구현 (Visual Basic)'
title: 인터페이스 만들기 및 구현
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: 058011d311fdecba626a59228816f9bced319c97
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468423"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="e3504-103">연습: 인터페이스 만들기 및 구현(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3504-103">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>

<span data-ttu-id="e3504-104">인터페이스는 속성, 메서드 및 이벤트의 특성을 설명 하지만, 구현 세부 정보는 구조체 또는 클래스까지 그대로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-104">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="e3504-105">이 연습에서는 인터페이스를 선언 하 고 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-105">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e3504-106">이 연습에서는 사용자 인터페이스를 만드는 방법에 대 한 정보를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-106">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a><span data-ttu-id="e3504-107">인터페이스를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="e3504-107">To define an interface</span></span>
  
1. <span data-ttu-id="e3504-108">새 Visual Basic Windows 애플리케이션 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-108">Open a new Visual Basic Windows Application project.</span></span>  
  
2. <span data-ttu-id="e3504-109">**프로젝트** 메뉴에서 **모듈 추가** 를 클릭 하 여 프로젝트에 새 모듈을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-109">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3. <span data-ttu-id="e3504-110">새 모듈의 이름을로 `Module1.vb` 하 고 **추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-110">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="e3504-111">새 모듈의 코드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-111">The code for the new module is displayed.</span></span>  
  
4. <span data-ttu-id="e3504-112">`TestInterface` `Module1` 및 문 사이에를 입력 하 `Interface TestInterface` `Module` 고 enter 키를 눌러 내에 명명 된 인터페이스를 정의 `End Module` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-112">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="e3504-113">**코드 편집기** 는 키워드를 들여쓰기 하 `Interface` 고 `End Interface` 문을 추가 하 여 코드 블록을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-113">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5. <span data-ttu-id="e3504-114">및 문 사이에 다음 코드를 배치 하 여 인터페이스에 대 한 속성, 메서드 및 이벤트를 정의 합니다 `Interface` `End Interface` .</span><span class="sxs-lookup"><span data-stu-id="e3504-114">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a><span data-ttu-id="e3504-115">구현</span><span class="sxs-lookup"><span data-stu-id="e3504-115">Implementation</span></span>

 <span data-ttu-id="e3504-116">인터페이스 멤버를 선언 하는 데 사용 되는 구문은 클래스 멤버를 선언 하는 데 사용 되는 구문과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-116">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="e3504-117">이러한 차이는 인터페이스에 구현 코드가 포함 될 수 없다는 사실을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-117">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
### <a name="to-implement-the-interface"></a><span data-ttu-id="e3504-118">인터페이스를 구현 하려면</span><span class="sxs-lookup"><span data-stu-id="e3504-118">To implement the interface</span></span>
  
1. <span data-ttu-id="e3504-119">문 뒤에 문 뒤에 다음 문을 추가 하 여 라는 클래스를 추가 하 `ImplementationClass` `Module1` `End Interface` `End Module` 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-119">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     <span data-ttu-id="e3504-120">통합 개발 환경 내에서 작업 하는 경우 ENTER 키를 누르면 **코드 편집기** 에서 일치 하는 문을 제공 합니다 `End Class` .</span><span class="sxs-lookup"><span data-stu-id="e3504-120">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2. <span data-ttu-id="e3504-121">`Implements` `ImplementationClass` 클래스에서 구현 하는 인터페이스의 이름을로 하는 다음 문을에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-121">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     <span data-ttu-id="e3504-122">클래스 또는 구조체의 맨 위에 있는 다른 항목과 별도로 나열 되는 경우 `Implements` 문은 클래스 또는 구조체가 인터페이스를 구현 한다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-122">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="e3504-123">통합 개발 환경 내에서 작업 하는 경우 ENTER 키를 누를 때에 필요한 클래스 멤버를 **코드 편집기** 에서 구현 `TestInterface` 하 고 다음 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-123">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3. <span data-ttu-id="e3504-124">통합 개발 환경 내에서 작업 하지 않는 경우 인터페이스의 모든 멤버를 구현 해야 합니다 `MyInterface` .</span><span class="sxs-lookup"><span data-stu-id="e3504-124">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="e3504-125">`ImplementationClass`, 및를 구현 하려면에 다음 코드를 추가 합니다 `Event1` `Method1` `Prop1` .</span><span class="sxs-lookup"><span data-stu-id="e3504-125">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     <span data-ttu-id="e3504-126">`Implements`문은 구현 중인 인터페이스와 인터페이스 멤버의 이름을로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-126">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4. <span data-ttu-id="e3504-127">`Prop1`속성 값을 저장 한 클래스에 전용 필드를 추가 하 여의 정의를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-127">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     <span data-ttu-id="e3504-128">Get 접근자 속성에서의 값을 반환 합니다 `pval` .</span><span class="sxs-lookup"><span data-stu-id="e3504-128">Return the value of the `pval` from the property get accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     <span data-ttu-id="e3504-129">`pval`속성 집합 접근자에서 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-129">Set the value of `pval` in the property set accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5. <span data-ttu-id="e3504-130">`Method1`다음 코드를 추가 하 여의 정의를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-130">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="e3504-131">인터페이스 구현을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="e3504-131">To test the implementation of the interface</span></span>
  
1. <span data-ttu-id="e3504-132">**솔루션 탐색기** 에서 프로젝트의 시작 폼을 마우스 오른쪽 단추로 클릭 하 고 **코드 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-132">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="e3504-133">편집기에서 시작 폼의 클래스를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-133">The editor displays the class for your startup form.</span></span> <span data-ttu-id="e3504-134">기본적으로 시작 폼이 호출 됩니다 `Form1` .</span><span class="sxs-lookup"><span data-stu-id="e3504-134">By default, the startup form is called `Form1`.</span></span>  
  
2. <span data-ttu-id="e3504-135">클래스에 다음 필드를 추가 합니다 `testInstance` `Form1` .</span><span class="sxs-lookup"><span data-stu-id="e3504-135">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     <span data-ttu-id="e3504-136">로 선언 `testInstance` 하면 `WithEvents` `Form1` 클래스가 해당 이벤트를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-136">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3. <span data-ttu-id="e3504-137">클래스에 다음 이벤트 처리기를 추가 하 `Form1` 여에서 발생 하는 이벤트를 처리 합니다 `testInstance` .</span><span class="sxs-lookup"><span data-stu-id="e3504-137">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4. <span data-ttu-id="e3504-138">클래스에 라는 서브루틴을 추가 `Test` `Form1` 하 여 구현 클래스를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-138">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     <span data-ttu-id="e3504-139">`Test`프로시저는를 구현 하는 클래스의 인스턴스 `MyInterface` 를 만들고, 해당 인스턴스를 필드에 할당 하 `testInstance` 고, 속성을 설정 하 고, 인터페이스를 통해 메서드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-139">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5. <span data-ttu-id="e3504-140">`Test`시작 폼의 프로시저에서 프로시저를 호출 하는 코드를 추가 합니다 `Form1 Load` .</span><span class="sxs-lookup"><span data-stu-id="e3504-140">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6. <span data-ttu-id="e3504-141">`Test`F5 키를 눌러 프로시저를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-141">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="e3504-142">"Prop1가 9로 설정 되었습니다." 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-142">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="e3504-143">확인을 클릭 하면 "Method1의 X 매개 변수가 5입니다." 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-143">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="e3504-144">확인을 클릭 하면 "이벤트를 catch 했습니다." 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3504-144">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3504-145">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e3504-145">See also</span></span>

- [<span data-ttu-id="e3504-146">Implements 문</span><span class="sxs-lookup"><span data-stu-id="e3504-146">Implements Statement</span></span>](../../../language-reference/statements/implements-statement.md)
- [<span data-ttu-id="e3504-147">인터페이스</span><span class="sxs-lookup"><span data-stu-id="e3504-147">Interfaces</span></span>](index.md)
- [<span data-ttu-id="e3504-148">Interface 문</span><span class="sxs-lookup"><span data-stu-id="e3504-148">Interface Statement</span></span>](../../../language-reference/statements/interface-statement.md)
- [<span data-ttu-id="e3504-149">Event 문</span><span class="sxs-lookup"><span data-stu-id="e3504-149">Event Statement</span></span>](../../../language-reference/statements/event-statement.md)
