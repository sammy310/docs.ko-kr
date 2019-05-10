---
title: '방법: Windows Forms BindingNavigator 컨트롤을 사용하여 데이터 탐색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BindingNavigator control [Windows Forms], navigating data
- data [Windows Forms], navigating
- data navigation
- examples [Windows Forms], BindingNavigator control
ms.assetid: 0e5d4f34-bc9b-47cf-9b8d-93acbb1f1dbb
ms.openlocfilehash: 0702532627fe4425a7c5e3ade5530939c8df5500
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649240"
---
# <a name="how-to-navigate-data-with-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="2e00b-102">방법: Windows Forms BindingNavigator 컨트롤을 사용하여 데이터 탐색</span><span class="sxs-lookup"><span data-stu-id="2e00b-102">How to: Navigate Data with the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="2e00b-103">Windows Forms의 <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 통해 개발자는 자신이 만든 폼에서 간단한 데이터 탐색 및 조작 사용자 인터페이스를 최종 사용자에게 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e00b-103">The advent of the <xref:System.Windows.Forms.BindingNavigator> control in Windows Forms enables developers to provide end users with a simple data navigation and manipulation user interface on the forms they create.</span></span>  
  
 <span data-ttu-id="2e00b-104"><xref:System.Windows.Forms.BindingNavigator> 컨트롤은 데이터 집합의 첫 번째 레코드, 마지막 레코드, 다음 레코드 및 이전 레코드를 탐색하도록 미리 구성된 단추와 레코드 추가 및 삭제 단추가 있는 <xref:System.Windows.Forms.ToolStrip> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="2e00b-104">The <xref:System.Windows.Forms.BindingNavigator> control is a <xref:System.Windows.Forms.ToolStrip> control with buttons preconfigured for navigation to the first, last, next, and previous record in a data set, as well as buttons to add and delete records.</span></span> <span data-ttu-id="2e00b-105"><xref:System.Windows.Forms.BindingNavigator> 컨트롤은 <xref:System.Windows.Forms.ToolStrip> 컨트롤이므로 쉽게 단추를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e00b-105">Adding buttons to the <xref:System.Windows.Forms.BindingNavigator> control is easy, because it is a <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="2e00b-106">예제는 [방법: 저장, 로드를 추가 하 고 취소 단추는 Windows Forms BindingNavigator 컨트롤](load-save-and-cancel-bindingnavigator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2e00b-106">For examples, see [How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control](load-save-and-cancel-bindingnavigator.md).</span></span>  
  
 <span data-ttu-id="2e00b-107"><xref:System.Windows.Forms.BindingNavigator> 컨트롤의 각 단추에 대해 프로그래밍 방식으로 동일한 기능을 허용하는 <xref:System.Windows.Forms.BindingSource> 구성 요소의 해당 멤버가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e00b-107">For each button on the <xref:System.Windows.Forms.BindingNavigator> control, there is a corresponding member of the <xref:System.Windows.Forms.BindingSource> component that programmatically allows the same functionality.</span></span> <span data-ttu-id="2e00b-108">예를 들어 <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> 단추는 <xref:System.Windows.Forms.BindingSource> 구성 요소의 <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> 메서드에 해당하고 <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> 단추는 <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> 메서드에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="2e00b-108">For example, the <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> method of the <xref:System.Windows.Forms.BindingSource> component, the <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> method, and so on.</span></span> <span data-ttu-id="2e00b-109">따라서 <xref:System.Windows.Forms.BindingNavigator> 컨트롤이 데이터 레코드를 탐색할 수 있게 하려는 경우 해당 <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> 속성을 폼의 적절한 <xref:System.Windows.Forms.BindingSource> 구성 요소로 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e00b-109">As a result, enabling the <xref:System.Windows.Forms.BindingNavigator> control to navigate data records is a simple as setting its <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the appropriate <xref:System.Windows.Forms.BindingSource> component on the form.</span></span>  
  
### <a name="to-set-up-the-bindingnavigator-control"></a><span data-ttu-id="2e00b-110">BindingNavigator 컨트롤을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="2e00b-110">To set up the BindingNavigator control</span></span>  
  
1. <span data-ttu-id="2e00b-111">`bindingSource1`이라는 <xref:System.Windows.Forms.BindingSource> 구성 요소와 `textBox1` 및 `textBox2`라는 <xref:System.Windows.Forms.TextBox> 컨트롤 두 개를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e00b-111">Add a <xref:System.Windows.Forms.BindingSource> component named `bindingSource1` and two <xref:System.Windows.Forms.TextBox> controls named `textBox1` and `textBox2`.</span></span>  
  
2. <span data-ttu-id="2e00b-112">`bindingSource1`을 데이터에 바인딩하고 텍스트 상자 컨트롤을 `bindingSource1`에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="2e00b-112">Bind `bindingSource1` to data, and the textbox controls to `bindingSource1`.</span></span> <span data-ttu-id="2e00b-113">이렇게 하려면 다음 코드를 폼에 붙여넣고 폼의 생성자나 <xref:System.Windows.Forms.Form.Load> 이벤트 처리 메서드에서 `LoadData`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="2e00b-113">To do this, paste the following code into your form and call `LoadData` from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#2)]  
  
3. <span data-ttu-id="2e00b-114">`bindingNavigator1`이라는 <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 폼에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e00b-114">Add a <xref:System.Windows.Forms.BindingNavigator> control named `bindingNavigator1` to your form.</span></span>  
  
4. <span data-ttu-id="2e00b-115">`bindingNavigator1`의 <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> 속성을 `bindingSource1`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2e00b-115">Set the <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property for `bindingNavigator1` to `bindingSource1`.</span></span> <span data-ttu-id="2e00b-116">이 작업은 디자이너나 코드에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e00b-116">You can do this with the designer or in code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="2e00b-117">예제</span><span class="sxs-lookup"><span data-stu-id="2e00b-117">Example</span></span>  
 <span data-ttu-id="2e00b-118">다음 코드 예제는 앞에 나열된 단계의 전체 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="2e00b-118">The following code example is the complete example for the steps listed previously.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2e00b-119">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="2e00b-119">Compiling the Code</span></span>  
 <span data-ttu-id="2e00b-120">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2e00b-120">This example requires:</span></span>  
  
- <span data-ttu-id="2e00b-121">System, System.Data, System.Drawing, System.Windows.Forms and System.Xml 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="2e00b-121">References to the System, System.Data, System.Drawing, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="2e00b-122">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2e00b-122">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="2e00b-123">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e00b-123">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e00b-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="2e00b-124">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- [<span data-ttu-id="2e00b-125">BindingNavigator 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2e00b-125">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="2e00b-126">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2e00b-126">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
