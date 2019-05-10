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
ms.openlocfilehash: 3fbaaae53aa60f6356c3a8daa0513de86ef2dacb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211288"
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a><span data-ttu-id="1039d-102">방법: Modifiers 및 GenerateMember 속성 사용</span><span class="sxs-lookup"><span data-stu-id="1039d-102">How to: Use the Modifiers and GenerateMember Properties</span></span>

<span data-ttu-id="1039d-103">디자인 환경에서 두 개의 속성을 제공 구성 요소를 Windows Form에 넣을 때: `GenerateMember` 고 `Modifiers`입니다.</span><span class="sxs-lookup"><span data-stu-id="1039d-103">When you place a component on a Windows Form, two properties are provided by the design environment: `GenerateMember` and `Modifiers`.</span></span> <span data-ttu-id="1039d-104">`GenerateMember` 속성 Windows Forms 디자이너 구성 요소에 대 한 멤버 변수를 생성 하는 경우를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1039d-104">The `GenerateMember` property specifies when the Windows Forms Designer generates a member variable for a component.</span></span> <span data-ttu-id="1039d-105">`Modifiers` 속성은 해당 멤버 변수에 할당 하는 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="1039d-105">The `Modifiers` property is the access modifier assigned to that member variable.</span></span> <span data-ttu-id="1039d-106">경우의 값을 `GenerateMember` 속성은 `false`의 값은 `Modifiers` 속성이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1039d-106">If the value of the `GenerateMember` property is `false`, the value of the `Modifiers` property has no effect.</span></span>

## <a name="specify-whether-a-component-is-a-member-of-the-form"></a><span data-ttu-id="1039d-107">구성 요소 폼의 멤버 인지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1039d-107">Specify whether a component is a member of the form</span></span>

1. <span data-ttu-id="1039d-108">Visual Studio Windows Forms 디자이너에서에서 폼을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1039d-108">In Visual Studio, in the Windows Forms Designer, open your form.</span></span>

2. <span data-ttu-id="1039d-109">엽니다는 **도구 상자**, 양식에서 세 가지를 배치 하 고 <xref:System.Windows.Forms.Button> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="1039d-109">Open the **Toolbox**, and on the form, place three <xref:System.Windows.Forms.Button> controls.</span></span>

3. <span data-ttu-id="1039d-110">설정 합니다 `GenerateMember` 하 고 `Modifiers` 각각에 대 한 속성 <xref:System.Windows.Forms.Button> 컨트롤은 다음 표에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="1039d-110">Set the `GenerateMember` and `Modifiers` properties for each <xref:System.Windows.Forms.Button> control according to the following table.</span></span>

    |<span data-ttu-id="1039d-111">단추 이름</span><span class="sxs-lookup"><span data-stu-id="1039d-111">Button name</span></span>|<span data-ttu-id="1039d-112">GenerateMember 값</span><span class="sxs-lookup"><span data-stu-id="1039d-112">GenerateMember value</span></span>|<span data-ttu-id="1039d-113">한정자 값</span><span class="sxs-lookup"><span data-stu-id="1039d-113">Modifiers value</span></span>|
    |-----------------|--------------------------|---------------------|
    |`button1`|`true`|`private`|
    |`button2`|`true`|`protected`|
    |`button3`|`false`|<span data-ttu-id="1039d-114">변경 안 함</span><span class="sxs-lookup"><span data-stu-id="1039d-114">No change</span></span>|

4. <span data-ttu-id="1039d-115">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="1039d-115">Build the solution.</span></span>

5. <span data-ttu-id="1039d-116">**솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1039d-116">In **Solution Explorer**, click the **Show All Files** button.</span></span>

6. <span data-ttu-id="1039d-117">엽니다는 **Form1** 노드를 고를 **코드 편집기**을 엽니다는 **Form1.Designer.vb** 또는 **Form1.Designer.cs** 파일.</span><span class="sxs-lookup"><span data-stu-id="1039d-117">Open the **Form1** node, and in the **Code Editor**,open the **Form1.Designer.vb** or **Form1.Designer.cs** file.</span></span> <span data-ttu-id="1039d-118">이 파일은 Windows Forms 디자이너에서 생성 된 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1039d-118">This file contains the code emitted by the Windows Forms Designer.</span></span>

7. <span data-ttu-id="1039d-119">세 개의 단추에 대 한 선언을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1039d-119">Find the declarations for the three buttons.</span></span> <span data-ttu-id="1039d-120">다음 코드 예제에서는 지정 된 차이점을 보여 줍니다.는 `GenerateMember` 고 `Modifiers` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1039d-120">The following code example shows the differences specified by the `GenerateMember` and `Modifiers` properties.</span></span>

     [!code-csharp[System.Windows.Forms.GenerateMember#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]

     [!code-csharp[System.Windows.Forms.GenerateMember#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]

> [!NOTE]
> <span data-ttu-id="1039d-121">기본적으로 Windows Forms 디자이너를 할당 합니다 `private` (`Friend` Visual Basic의) 처럼 컨테이너 컨트롤에는 한정자 <xref:System.Windows.Forms.Panel>합니다.</span><span class="sxs-lookup"><span data-stu-id="1039d-121">By default, the Windows Forms Designer assigns the `private` (`Friend` in Visual Basic) modifier to container controls like <xref:System.Windows.Forms.Panel>.</span></span> <span data-ttu-id="1039d-122">경우 베이스가 <xref:System.Windows.Forms.UserControl> 또는 <xref:System.Windows.Forms.Form> 컨테이너 컨트롤에 상속 된 컨트롤 및 폼에 새 자식 항목을 허용 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1039d-122">If your base <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Form> has a container control, it will not accept new children in inherited controls and forms.</span></span> <span data-ttu-id="1039d-123">솔루션은 기본 컨테이너 컨트롤의 한정자를 변경할 `protected` 또는 `public`합니다.</span><span class="sxs-lookup"><span data-stu-id="1039d-123">The solution is to change the modifier of the base container control to `protected` or `public`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1039d-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="1039d-124">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="1039d-125">Windows Forms 시각적 개체 상속</span><span class="sxs-lookup"><span data-stu-id="1039d-125">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="1039d-126">연습: 시각적 상속 설명</span><span class="sxs-lookup"><span data-stu-id="1039d-126">Walkthrough: Demonstrating Visual Inheritance</span></span>](walkthrough-demonstrating-visual-inheritance.md)
- [<span data-ttu-id="1039d-127">방법: Windows Forms 상속</span><span class="sxs-lookup"><span data-stu-id="1039d-127">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
