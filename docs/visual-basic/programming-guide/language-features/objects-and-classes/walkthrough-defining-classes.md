---
description: '자세한 정보: 연습: 클래스 정의 (Visual Basic)'
title: 클래스 정의
ms.date: 07/20/2015
helpviewer_keywords:
- execution [Visual Basic], ending
- objects [Visual Basic], initializing
- Initialize event [Visual Basic]
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
ms.openlocfilehash: a97e04b92db3387966afa410d5697a05b482ae09
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100438790"
---
# <a name="walkthrough-defining-classes-visual-basic"></a><span data-ttu-id="5c861-103">연습: 클래스 정의(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c861-103">Walkthrough: Defining Classes (Visual Basic)</span></span>

<span data-ttu-id="5c861-104">이 연습에서는 클래스를 정의 하는 방법을 보여 줍니다 .이 클래스를 사용 하 여 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-104">This walkthrough demonstrates how to define classes, which you can then use to create objects.</span></span> <span data-ttu-id="5c861-105">또한 새 클래스에 속성 및 메서드를 추가 하는 방법과 개체를 초기화 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-105">It also shows you how to add properties and methods to the new class, and demonstrates how to initialize an object.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a><span data-ttu-id="5c861-106">클래스를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="5c861-106">To define a class</span></span>
  
1. <span data-ttu-id="5c861-107">**파일** 메뉴에서 **새 프로젝트** 를 클릭 하 여 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-107">Create a project by clicking **New Project** on the **File** menu.</span></span> <span data-ttu-id="5c861-108">**새 프로젝트** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-108">The **New Project** dialog box appears.</span></span>  
  
2. <span data-ttu-id="5c861-109">Visual Basic 프로젝트 템플릿 목록에서 Windows 응용 프로그램을 선택 하 여 새 프로젝트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-109">Select Windows Application from the list of Visual Basic project templates to display the new project.</span></span>  
  
3. <span data-ttu-id="5c861-110">**프로젝트** 메뉴에서 **클래스 추가** 를 클릭 하 여 프로젝트에 새 클래스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-110">Add a new class to the project by clicking **Add Class** on the **Project** menu.</span></span> <span data-ttu-id="5c861-111">**새 항목 추가** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-111">The **Add New Item** dialog box appears.</span></span>  
  
4. <span data-ttu-id="5c861-112">**클래스** 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-112">Select the **Class** template.</span></span>  
  
5. <span data-ttu-id="5c861-113">새 클래스의 이름을로 `UserNameInfo.vb` 지정한 다음 **추가** 를 클릭 하 여 새 클래스에 대 한 코드를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-113">Name the new class `UserNameInfo.vb`, and then click **Add** to display the code for the new class.</span></span>  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    > <span data-ttu-id="5c861-114">Visual Basic **코드 편집기** 를 사용 하 여 `Class` 키워드와 새 클래스의 이름을 차례로 입력 하 여 시작 폼에 클래스를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-114">You can use the Visual Basic **Code Editor** to add a class to your startup form by typing the `Class` keyword followed by the name of the new class.</span></span> <span data-ttu-id="5c861-115">**코드 편집기** 는 해당 문을 제공 합니다 `End Class` .</span><span class="sxs-lookup"><span data-stu-id="5c861-115">The **Code Editor** provides a corresponding `End Class` statement for you.</span></span>  
  
6. <span data-ttu-id="5c861-116">문과 문 사이에 다음 코드를 추가 하 여 클래스에 대 한 전용 필드를 정의 합니다 `Class` `End Class` .</span><span class="sxs-lookup"><span data-stu-id="5c861-116">Define a private field for the class by adding the following code between the `Class` and `End Class` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     <span data-ttu-id="5c861-117">필드를로 선언 하는 것은 `Private` 클래스 내 에서만 사용할 수 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-117">Declaring the field as `Private` means it can be used only within the class.</span></span> <span data-ttu-id="5c861-118">`Public`보다 많은 액세스 권한을 제공 하는와 같은 액세스 한정자를 사용 하 여 클래스 외부에서 필드를 사용할 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-118">You can make fields available from outside a class by using access modifiers such as `Public` that provide more access.</span></span> <span data-ttu-id="5c861-119">자세한 내용은 [Visual Basic의 액세스 수준](../declared-elements/access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5c861-119">For more information, see [Access levels in Visual Basic](../declared-elements/access-levels.md).</span></span>  
  
7. <span data-ttu-id="5c861-120">다음 코드를 추가 하 여 클래스에 대 한 속성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-120">Define a property for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8. <span data-ttu-id="5c861-121">다음 코드를 추가 하 여 클래스에 대 한 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-121">Define a method for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. <span data-ttu-id="5c861-122">이라는 프로시저를 추가 하 여 새 클래스에 대 한 매개 변수가 있는 생성자를 정의 합니다 `Sub New` .</span><span class="sxs-lookup"><span data-stu-id="5c861-122">Define a parameterized constructor for the new class by adding a procedure named `Sub New`:</span></span>  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     <span data-ttu-id="5c861-123">`Sub New`생성자는이 클래스를 기반으로 하는 개체를 만들 때 자동으로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-123">The `Sub New` constructor is called automatically when an object based on this class is created.</span></span> <span data-ttu-id="5c861-124">이 생성자는 사용자 이름을 포함 하는 필드의 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-124">This constructor sets the value of the field that holds the user name.</span></span>  
  
## <a name="to-create-a-button-to-test-the-class"></a><span data-ttu-id="5c861-125">클래스를 테스트 하는 단추를 만들려면</span><span class="sxs-lookup"><span data-stu-id="5c861-125">To create a button to test the class</span></span>
  
1. <span data-ttu-id="5c861-126">**솔루션 탐색기** 에서 해당 이름을 마우스 오른쪽 단추로 클릭 한 다음 **디자이너 보기** 를 클릭 하 여 시작 폼을 디자인 모드로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-126">Change the startup form to design mode by right-clicking its name in **Solution Explorer** and then clicking **View Designer**.</span></span> <span data-ttu-id="5c861-127">기본적으로 Windows 응용 프로그램 프로젝트의 시작 폼에는 form1.vb 라는 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-127">By default, the startup form for Windows Application projects is named Form1.vb.</span></span> <span data-ttu-id="5c861-128">그러면 기본 폼이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-128">The main form will then appear.</span></span>  
  
2. <span data-ttu-id="5c861-129">기본 폼에 단추를 추가 하 고 두 번 클릭 하 여 이벤트 처리기에 대 한 코드를 표시 합니다 `Button1_Click` .</span><span class="sxs-lookup"><span data-stu-id="5c861-129">Add a button to the main form and double-click it to display the code for the `Button1_Click` event handler.</span></span> <span data-ttu-id="5c861-130">다음 코드를 추가 하 여 테스트 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-130">Add the following code to call the test procedure:</span></span>  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a><span data-ttu-id="5c861-131">애플리케이션을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="5c861-131">To run your application</span></span>
  
1. <span data-ttu-id="5c861-132">F5 키를 눌러 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-132">Run your application by pressing F5.</span></span> <span data-ttu-id="5c861-133">폼의 단추를 클릭 하 여 테스트 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-133">Click the button on the form to call the test procedure.</span></span> <span data-ttu-id="5c861-134">`UserName`프로시저에서 개체의 메서드를 호출 했기 때문에 원래는 "일, 강현수" 이라는 메시지를 표시 합니다 `Capitalize` .</span><span class="sxs-lookup"><span data-stu-id="5c861-134">It displays a message stating that the original `UserName` is "MOORE, BOBBY", because the procedure called the `Capitalize` method of the object.</span></span>  
  
2. <span data-ttu-id="5c861-135">**확인** 을 클릭하여 메시지 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-135">Click **OK** to dismiss the message box.</span></span> <span data-ttu-id="5c861-136">`Button1 Click`이 프로시저는 속성의 값을 변경 `UserName` 하 고의 새 값 `UserName` 이 "Worden, Joe" 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c861-136">The `Button1 Click` procedure changes the value of the `UserName` property and displays a message stating that the new value of `UserName` is "Worden, Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c861-137">추가 정보</span><span class="sxs-lookup"><span data-stu-id="5c861-137">See also</span></span>

- [<span data-ttu-id="5c861-138">개체 지향 프로그래밍(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c861-138">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
- [<span data-ttu-id="5c861-139">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="5c861-139">Objects and Classes</span></span>](index.md)
