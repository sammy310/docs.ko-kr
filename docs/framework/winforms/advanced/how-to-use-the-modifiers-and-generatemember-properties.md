---
title: '방법: Modifiers 및 GenerateMember 속성 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Designer_GenerateMember
- Designer_Modifiers
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
ms.openlocfilehash: 612d323305c2dbd4698c6d687fb19ec36983bde4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143912"
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a><span data-ttu-id="d2d49-102">방법: Modifiers 및 GenerateMember 속성 사용</span><span class="sxs-lookup"><span data-stu-id="d2d49-102">How to: Use the Modifiers and GenerateMember Properties</span></span>
<span data-ttu-id="d2d49-103">디자인 환경에서 두 개의 속성을 제공 구성 요소를 Windows Form에 넣을 때: `GenerateMember` 고 `Modifiers`입니다.</span><span class="sxs-lookup"><span data-stu-id="d2d49-103">When you place a component on a Windows Form, two properties are provided by the design environment: `GenerateMember` and `Modifiers`.</span></span> <span data-ttu-id="d2d49-104">`GenerateMember` 속성 Windows Forms 디자이너 구성 요소에 대 한 멤버 변수를 생성 하는 경우를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d49-104">The `GenerateMember` property specifies when the Windows Forms Designer generates a member variable for a component.</span></span> <span data-ttu-id="d2d49-105">`Modifiers` 속성은 해당 멤버 변수에 할당 하는 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="d2d49-105">The `Modifiers` property is the access modifier assigned to that member variable.</span></span> <span data-ttu-id="d2d49-106">경우의 값을 `GenerateMember` 속성은 `false`의 값은 `Modifiers` 속성이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d49-106">If the value of the `GenerateMember` property is `false`, the value of the `Modifiers` property has no effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d2d49-107">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d49-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d2d49-108">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d49-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="d2d49-109">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2d49-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-specify-whether-a-component-is-a-member-of-the-form"></a><span data-ttu-id="d2d49-110">구성 요소 폼의 멤버 인지 여부를 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="d2d49-110">To specify whether a component is a member of the form</span></span>  
  
1.  <span data-ttu-id="d2d49-111">Windows Forms 디자이너에서 폼을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d2d49-111">In the Windows Forms Designer, open your form.</span></span>  
  
2.  <span data-ttu-id="d2d49-112">엽니다는 **도구 상자**, 양식에서 세 가지를 배치 하 고 <xref:System.Windows.Forms.Button> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="d2d49-112">Open the **Toolbox**, and on the form, place three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
3.  <span data-ttu-id="d2d49-113">설정 합니다 `GenerateMember` 하 고 `Modifiers` 각각에 대 한 속성 <xref:System.Windows.Forms.Button> 컨트롤은 다음 표에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d49-113">Set the `GenerateMember` and `Modifiers` properties for each <xref:System.Windows.Forms.Button> control according to the following table.</span></span>  
  
    |<span data-ttu-id="d2d49-114">단추 이름</span><span class="sxs-lookup"><span data-stu-id="d2d49-114">Button name</span></span>|<span data-ttu-id="d2d49-115">GenerateMember 값</span><span class="sxs-lookup"><span data-stu-id="d2d49-115">GenerateMember value</span></span>|<span data-ttu-id="d2d49-116">한정자 값</span><span class="sxs-lookup"><span data-stu-id="d2d49-116">Modifiers value</span></span>|  
    |-----------------|--------------------------|---------------------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|<span data-ttu-id="d2d49-117">변경 안 함</span><span class="sxs-lookup"><span data-stu-id="d2d49-117">No change</span></span>|  
  
4.  <span data-ttu-id="d2d49-118">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d49-118">Build the solution.</span></span>  
  
5.  <span data-ttu-id="d2d49-119">**솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d49-119">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
6.  <span data-ttu-id="d2d49-120">엽니다는 **Form1** 노드를 고를 **코드 편집기**을 엽니다는 **Form1.Designer.vb** 또는 **Form1.Designer.cs** 파일.</span><span class="sxs-lookup"><span data-stu-id="d2d49-120">Open the **Form1** node, and in the **Code Editor**,open the **Form1.Designer.vb** or **Form1.Designer.cs** file.</span></span> <span data-ttu-id="d2d49-121">이 파일은 Windows Forms 디자이너에서 생성 된 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d49-121">This file contains the code emitted by the Windows Forms Designer.</span></span>  
  
7.  <span data-ttu-id="d2d49-122">세 개의 단추에 대 한 선언을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d49-122">Find the declarations for the three buttons.</span></span> <span data-ttu-id="d2d49-123">다음 코드 예제에서는 지정 된 차이점을 보여 줍니다.는 `GenerateMember` 고 `Modifiers` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d2d49-123">The following code example shows the differences specified by the `GenerateMember` and `Modifiers` properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  <span data-ttu-id="d2d49-124">기본적으로 Windows Forms 디자이너를 할당 합니다 `private` (`Friend` Visual Basic의) 처럼 컨테이너 컨트롤에는 한정자 <xref:System.Windows.Forms.Panel>합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d49-124">By default, the Windows Forms Designer assigns the `private` (`Friend` in Visual Basic) modifier to container controls like <xref:System.Windows.Forms.Panel>.</span></span> <span data-ttu-id="d2d49-125">경우 베이스가 <xref:System.Windows.Forms.UserControl> 또는 <xref:System.Windows.Forms.Form> 컨테이너 컨트롤에 상속 된 컨트롤 및 폼에 새 자식 항목을 허용 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2d49-125">If your base <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Form> has a container control, it will not accept new children in inherited controls and forms.</span></span> <span data-ttu-id="d2d49-126">솔루션은 기본 컨테이너 컨트롤의 한정자를 변경할 `protected` 또는 `public`합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d49-126">The solution is to change the modifier of the base container control to `protected` or `public`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2d49-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="d2d49-127">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="d2d49-128">Windows Forms 시각적 상속</span><span class="sxs-lookup"><span data-stu-id="d2d49-128">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="d2d49-129">연습: 시각적 상속 데모</span><span class="sxs-lookup"><span data-stu-id="d2d49-129">Walkthrough: Demonstrating Visual Inheritance</span></span>](walkthrough-demonstrating-visual-inheritance.md)
- [<span data-ttu-id="d2d49-130">방법: Windows Forms 상속</span><span class="sxs-lookup"><span data-stu-id="d2d49-130">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
