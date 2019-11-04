---
title: '방법: 합성 컨트롤 제작'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], creating composite controls
- user controls [Windows Forms], creating
- user controls [Windows Forms], inheriting from
- composite controls [Windows Forms], creating
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 42ea424507b89576df8099fd4849dd2665135a55
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459429"
---
# <a name="how-to-author-composite-controls"></a><span data-ttu-id="57ce9-102">방법: 합성 컨트롤 제작</span><span class="sxs-lookup"><span data-stu-id="57ce9-102">How to: Author composite controls</span></span>

<span data-ttu-id="57ce9-103">여러 가지 방법으로 복합 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-103">Composite controls can be employed in many ways.</span></span> <span data-ttu-id="57ce9-104">Windows 데스크톱 애플리케이션 프로젝트의 일부로 작성하고 프로젝트의 양식에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-104">You can author them as part of a Windows desktop application project, and use them only on forms in the project.</span></span> <span data-ttu-id="57ce9-105">또는 Windows 컨트롤 라이브러리 프로젝트에서 작성하고 프로젝트를 어셈블리로 컴파일하고 다른 프로젝트에서 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-105">Or you can author them in a Windows Control Library project, compile the project into an assembly, and use the controls in other projects.</span></span> <span data-ttu-id="57ce9-106">이를 상속 하거나 시각적 상속을 사용 하 여 특별 한 목적으로 신속 하 게 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-106">You can even inherit from them and use visual inheritance to customize them quickly for special purposes.</span></span>

## <a name="to-author-a-composite-control"></a><span data-ttu-id="57ce9-107">복합 컨트롤을 작성하려면</span><span class="sxs-lookup"><span data-stu-id="57ce9-107">To author a composite control</span></span>

1. <span data-ttu-id="57ce9-108">Visual Studio에서 새 **Windows 응용 프로그램** 프로젝트를 만들고 이름을 **Democontrolhost**로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-108">In Visual Studio, create a new **Windows Application** project, and name it **DemoControlHost**.</span></span>

2. <span data-ttu-id="57ce9-109">**프로젝트** 메뉴에서 **사용자 정의 컨트롤 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-109">On the **Project** menu, click **Add User Control**.</span></span>

3. <span data-ttu-id="57ce9-110">**새 항목 추가** 대화 상자에서 클래스 파일(.cs 또는 .vb 파일)에 복합 컨트롤이 원하는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-110">In the **Add New Item** dialog box, give the class file (.vb or .cs file) the name you want the composite control to have.</span></span>

4. <span data-ttu-id="57ce9-111">**추가** 단추를 선택 하 여 복합 컨트롤의 클래스 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-111">Select the **Add** button to create the class file for the composite control.</span></span>

5. <span data-ttu-id="57ce9-112">**도구 상자**에서 복합 컨트롤 화면에 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-112">Add controls from the **Toolbox** to the composite control surface.</span></span>

6. <span data-ttu-id="57ce9-113">이벤트 프로시저에 복합 컨트롤 또는 구성원 컨트롤에 의해 발생한 이벤트를 처리하는 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-113">Place code in event procedures, to handle events raised by the composite control or by its constituent controls.</span></span>

7. <span data-ttu-id="57ce9-114">복합 컨트롤의 디자이너를 닫고 메시지가 나타나면 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-114">Close the designer for the composite control, and save the file when you are prompted.</span></span>

8. <span data-ttu-id="57ce9-115">**빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-115">On the **Build** menu, click **Build Solution**.</span></span>

     <span data-ttu-id="57ce9-116">사용자 지정 컨트롤을 **도구 상자**에 표시하기 위해 프로젝트를 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-116">The project must be built in order for custom controls to appear in the **Toolbox**.</span></span>

9. <span data-ttu-id="57ce9-117">**도구 상자**의 **DemoControlHost** 탭을 사용하여 컨트롤의 인스턴스를 `Form1`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-117">Use the **DemoControlHost** tab of the **Toolbox** to add instances of your control to `Form1`.</span></span>

## <a name="to-author-a-control-class-library"></a><span data-ttu-id="57ce9-118">컨트롤 클래스 라이브러리를 작성하려면</span><span class="sxs-lookup"><span data-stu-id="57ce9-118">To author a control class library</span></span>

1. <span data-ttu-id="57ce9-119">새 **Windows 컨트롤 라이브러리** 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-119">Open a new **Windows Control Library** project.</span></span>

     <span data-ttu-id="57ce9-120">기본적으로 프로젝트는 복합 컨트롤을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-120">By default, the project contains a composite control.</span></span>

2. <span data-ttu-id="57ce9-121">위의 절차에서 설명한 대로 컨트롤 및 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-121">Add controls and code as described in the procedure above.</span></span>

3. <span data-ttu-id="57ce9-122">변경할 클래스를 상속하려는 컨트롤을 선택하고 이 컨트롤의 **한정자** 속성을 **개인**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-122">Choose a control you do not want inheriting classes to change, and set the **Modifiers** property of this control to **Private**.</span></span>

4. <span data-ttu-id="57ce9-123">DLL을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-123">Build the DLL.</span></span>

## <a name="to-inherit-from-a-composite-control-in-a-control-class-library"></a><span data-ttu-id="57ce9-124">컨트롤 클래스 라이브러리의 복합 컨트롤에서 상속하려면</span><span class="sxs-lookup"><span data-stu-id="57ce9-124">To inherit from a composite control in a control class library</span></span>

1. <span data-ttu-id="57ce9-125">**파일** 메뉴에서 **추가**를 가리키고 **새 프로젝트**를 선택하여 새 **Windows 애플리케이션** 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-125">On the **File** menu, point to **Add** and select **New Project** to add a new **Windows Application** project to the solution.</span></span>

2. <span data-ttu-id="57ce9-126">**솔루션 탐색기**에서 새 프로젝트의 **References** 폴더를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택하여 **참조 추가** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-126">In **Solution Explorer**, right-click the **References** folder for the new project and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

3. <span data-ttu-id="57ce9-127">**프로젝트** 탭을 선택하고 컨트롤 라이브러리 프로젝트를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-127">Select the **Projects** tab and double-click your control library project.</span></span>

4. <span data-ttu-id="57ce9-128">**빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-128">On the **Build** menu, click **Build Solution**.</span></span>

5. <span data-ttu-id="57ce9-129">**솔루션 탐색기**에서 컨트롤 라이브러리 프로젝트를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **새 항목 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-129">In **Solution Explorer**, right-click your control library project and select **Add New Item** from the shortcut menu.</span></span>

6. <span data-ttu-id="57ce9-130">**새 항목 추가** 대화 상자에서 **상속된 사용자 정의 컨트롤** 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-130">Select the **Inherited User Control** template from the **Add New Item** dialog box.</span></span>

7. <span data-ttu-id="57ce9-131">**상속 선택** 대화 상자에서 상속하려는 컨트롤을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-131">In the **Inheritance Picker** dialog box, double-click the control you want to inherit from.</span></span>

     <span data-ttu-id="57ce9-132">새 컨트롤을 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-132">A new control is added to your project.</span></span>

8. <span data-ttu-id="57ce9-133">새 컨트롤에 대한 시각적 디자이너를 열고 추가 구성 요소 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-133">Open the visual designer for the new control and add additional constituent controls.</span></span>

     <span data-ttu-id="57ce9-134">DLL의 복합 컨트롤에서 상속된 구성 요소 컨트롤을 볼 수 있으며 **한정자** 속성이 **공용**인 컨트롤의 속성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-134">You can see the constituent controls that were inherited from the composite control in your DLL, and you can alter the properties of controls whose **Modifiers** property is **Public**.</span></span> <span data-ttu-id="57ce9-135">**한정자** 속성이 **개인**인 컨트롤의 속성을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57ce9-135">You cannot change the properties of the control whose **Modifiers** property is **Private**.</span></span>

## <a name="see-also"></a><span data-ttu-id="57ce9-136">참조</span><span class="sxs-lookup"><span data-stu-id="57ce9-136">See also</span></span>

- [<span data-ttu-id="57ce9-137">연습: 합성 컨트롤 제작</span><span class="sxs-lookup"><span data-stu-id="57ce9-137">Walkthrough: Authoring a Composite Control</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [<span data-ttu-id="57ce9-138">연습: Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="57ce9-138">Walkthrough: Inheriting from a Windows Forms Control</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
- [<span data-ttu-id="57ce9-139">컨트롤 형식 권장 사항</span><span class="sxs-lookup"><span data-stu-id="57ce9-139">Control Type Recommendations</span></span>](control-type-recommendations.md)
- [<span data-ttu-id="57ce9-140">방법: Windows Forms 컨트롤 제작</span><span class="sxs-lookup"><span data-stu-id="57ce9-140">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="57ce9-141">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="57ce9-141">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
