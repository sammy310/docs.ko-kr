---
title: '방법: 복합 컨트롤 작성'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], creating composite controls
- user controls [Windows Forms], creating
- user controls [Windows Forms], inheriting from
- composite controls [Windows Forms], creating
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
ms.openlocfilehash: 7b0ee8efa62175e2ced2a810ca6dd76e8adc103b
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039891"
---
# <a name="how-to-author-composite-controls"></a><span data-ttu-id="211a8-102">방법: 복합 컨트롤 작성</span><span class="sxs-lookup"><span data-stu-id="211a8-102">How to: Author Composite Controls</span></span>

<span data-ttu-id="211a8-103">여러 가지 방법으로 복합 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-103">Composite controls can be employed in many ways.</span></span> <span data-ttu-id="211a8-104">Windows 데스크톱 애플리케이션 프로젝트의 일부로 작성하고 프로젝트의 양식에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-104">You can author them as part of a Windows desktop application project, and use them only on forms in the project.</span></span> <span data-ttu-id="211a8-105">또는 Windows 컨트롤 라이브러리 프로젝트에서 작성하고 프로젝트를 어셈블리로 컴파일하고 다른 프로젝트에서 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-105">Or you can author them in a Windows Control Library project, compile the project into an assembly, and use the controls in other projects.</span></span> <span data-ttu-id="211a8-106">이를 상속 하거나 시각적 상속을 사용 하 여 특별 한 목적으로 신속 하 게 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-106">You can even inherit from them and use visual inheritance to customize them quickly for special purposes.</span></span>

> [!NOTE]
> <span data-ttu-id="211a8-107">Web Forms에서 사용할 복합 컨트롤을 작성하려는 경우 [사용자 지정 ASP.NET 서버 컨트롤 개발](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="211a8-107">If you want to author a composite control to use on Web Forms, see [Developing Custom ASP.NET Server Controls](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>

## <a name="to-author-a-composite-control"></a><span data-ttu-id="211a8-108">복합 컨트롤을 작성하려면</span><span class="sxs-lookup"><span data-stu-id="211a8-108">To author a composite control</span></span>

1. <span data-ttu-id="211a8-109">Visual Studio에서 라는 `DemoControlHost`새 **Windows 응용 프로그램** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-109">In Visual Studio, create a new **Windows Application** project called `DemoControlHost`.</span></span>

2. <span data-ttu-id="211a8-110">**프로젝트** 메뉴에서 **사용자 정의 컨트롤 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-110">On the **Project** menu, click **Add User Control**.</span></span>

3. <span data-ttu-id="211a8-111">**새 항목 추가** 대화 상자에서 클래스 파일(.cs 또는 .vb 파일)에 복합 컨트롤이 원하는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-111">In the **Add New Item** dialog box, give the class file (.vb or .cs file) the name you want the composite control to have.</span></span>

4. <span data-ttu-id="211a8-112">**추가** 단추를 선택 하 여 복합 컨트롤의 클래스 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-112">Select the **Add** button to create the class file for the composite control.</span></span>

5. <span data-ttu-id="211a8-113">**도구 상자**에서 복합 컨트롤 화면에 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-113">Add controls from the **Toolbox** to the composite control surface.</span></span>

6. <span data-ttu-id="211a8-114">이벤트 프로시저에 복합 컨트롤 또는 구성원 컨트롤에 의해 발생한 이벤트를 처리하는 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-114">Place code in event procedures, to handle events raised by the composite control or by its constituent controls.</span></span>

7. <span data-ttu-id="211a8-115">복합 컨트롤의 디자이너를 닫고 메시지가 나타나면 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-115">Close the designer for the composite control, and save the file when you are prompted.</span></span>

8. <span data-ttu-id="211a8-116">**빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-116">On the **Build** menu, click **Build Solution**.</span></span>

     <span data-ttu-id="211a8-117">사용자 지정 컨트롤을 **도구 상자**에 표시하기 위해 프로젝트를 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-117">The project must be built in order for custom controls to appear in the **Toolbox**.</span></span>

9. <span data-ttu-id="211a8-118">**도구 상자**의 **DemoControlHost** 탭을 사용하여 컨트롤의 인스턴스를 `Form1`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-118">Use the **DemoControlHost** tab of the **Toolbox** to add instances of your control to `Form1`.</span></span>

## <a name="to-author-a-control-class-library"></a><span data-ttu-id="211a8-119">컨트롤 클래스 라이브러리를 작성하려면</span><span class="sxs-lookup"><span data-stu-id="211a8-119">To author a control class library</span></span>

1. <span data-ttu-id="211a8-120">새 **Windows 컨트롤 라이브러리** 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-120">Open a new **Windows Control Library** project.</span></span>

     <span data-ttu-id="211a8-121">기본적으로 프로젝트는 복합 컨트롤을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-121">By default, the project contains a composite control.</span></span>

2. <span data-ttu-id="211a8-122">위의 절차에서 설명한 대로 컨트롤 및 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-122">Add controls and code as described in the procedure above.</span></span>

3. <span data-ttu-id="211a8-123">변경할 클래스를 상속하려는 컨트롤을 선택하고 이 컨트롤의 **한정자** 속성을 **개인**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-123">Choose a control you do not want inheriting classes to change, and set the **Modifiers** property of this control to **Private**.</span></span>

4. <span data-ttu-id="211a8-124">DLL을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-124">Build the DLL.</span></span>

## <a name="to-inherit-from-a-composite-control-in-a-control-class-library"></a><span data-ttu-id="211a8-125">컨트롤 클래스 라이브러리의 복합 컨트롤에서 상속하려면</span><span class="sxs-lookup"><span data-stu-id="211a8-125">To inherit from a composite control in a control class library</span></span>

1. <span data-ttu-id="211a8-126">**파일** 메뉴에서 **추가**를 가리키고 **새 프로젝트**를 선택하여 새 **Windows 응용 프로그램** 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-126">On the **File** menu, point to **Add** and select **New Project** to add a new **Windows Application** project to the solution.</span></span>

2. <span data-ttu-id="211a8-127">**솔루션 탐색기**에서 새 프로젝트의 **References** 폴더를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택하여 **참조 추가** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-127">In **Solution Explorer**, right-click the **References** folder for the new project and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

3. <span data-ttu-id="211a8-128">**프로젝트** 탭을 선택하고 컨트롤 라이브러리 프로젝트를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-128">Select the **Projects** tab and double-click your control library project.</span></span>

4. <span data-ttu-id="211a8-129">**빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-129">On the **Build** menu, click **Build Solution**.</span></span>

5. <span data-ttu-id="211a8-130">**솔루션 탐색기**에서 컨트롤 라이브러리 프로젝트를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **새 항목 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-130">In **Solution Explorer**, right-click your control library project and select **Add New Item** from the shortcut menu.</span></span>

6. <span data-ttu-id="211a8-131">**새 항목 추가** 대화 상자에서 **상속된 사용자 정의 컨트롤** 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-131">Select the **Inherited User Control** template from the **Add New Item** dialog box.</span></span>

7. <span data-ttu-id="211a8-132">**상속 선택** 대화 상자에서 상속하려는 컨트롤을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-132">In the **Inheritance Picker** dialog box, double-click the control you want to inherit from.</span></span>

     <span data-ttu-id="211a8-133">새 컨트롤을 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-133">A new control is added to your project.</span></span>

8. <span data-ttu-id="211a8-134">새 컨트롤에 대한 시각적 디자이너를 열고 추가 구성 요소 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-134">Open the visual designer for the new control and add additional constituent controls.</span></span>

     <span data-ttu-id="211a8-135">DLL의 복합 컨트롤에서 상속된 구성 요소 컨트롤을 볼 수 있으며 **한정자** 속성이 **공용**인 컨트롤의 속성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-135">You can see the constituent controls that were inherited from the composite control in your DLL, and you can alter the properties of controls whose **Modifiers** property is **Public**.</span></span> <span data-ttu-id="211a8-136">**한정자** 속성이 **개인**인 컨트롤의 속성을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="211a8-136">You cannot change the properties of the control whose **Modifiers** property is **Private**.</span></span>

## <a name="see-also"></a><span data-ttu-id="211a8-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="211a8-137">See also</span></span>

- [<span data-ttu-id="211a8-138">연습: Visual Basic를 사용 하 여 복합 컨트롤 작성</span><span class="sxs-lookup"><span data-stu-id="211a8-138">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [<span data-ttu-id="211a8-139">연습: 시각적 개체를 사용 하 여 복합 컨트롤 작성C#</span><span class="sxs-lookup"><span data-stu-id="211a8-139">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [<span data-ttu-id="211a8-140">연습: Visual Basic를 사용 하 여 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="211a8-140">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)
- [<span data-ttu-id="211a8-141">연습: 시각적 개체를 사용 하 여 Windows Forms 컨트롤에서 상속C#</span><span class="sxs-lookup"><span data-stu-id="211a8-141">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
- [<span data-ttu-id="211a8-142">컨트롤 형식 권장 사항</span><span class="sxs-lookup"><span data-stu-id="211a8-142">Control Type Recommendations</span></span>](control-type-recommendations.md)
- [<span data-ttu-id="211a8-143">방법: Windows Forms에 대 한 Author 컨트롤</span><span class="sxs-lookup"><span data-stu-id="211a8-143">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="211a8-144">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="211a8-144">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
