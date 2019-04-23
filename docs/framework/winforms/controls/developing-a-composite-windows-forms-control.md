---
title: Windows Forms 복합 컨트롤 개발
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
ms.openlocfilehash: bfbb9091d40652bdd1ae277f3a77feefbccbf080
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196465"
---
# <a name="developing-a-composite-windows-forms-control"></a><span data-ttu-id="08e54-102">Windows Forms 복합 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="08e54-102">Developing a Composite Windows Forms Control</span></span>
<span data-ttu-id="08e54-103">다른 Windows Forms 컨트롤을 결합하여 복합 Windows Forms 컨트롤을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08e54-103">You can develop a composite Windows Forms control by combining other Windows Forms controls.</span></span> <span data-ttu-id="08e54-104">파생 된 복합 컨트롤 <xref:System.Web.UI.UserControl> 사용자 컨트롤 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="08e54-104">Composite controls that derive from <xref:System.Web.UI.UserControl> are called user controls.</span></span> <span data-ttu-id="08e54-105">기본 클래스 <xref:System.Windows.Forms.UserControl>은 자식 컨트롤에 대한 키보드 라우팅을 제공하므로 자식 컨트롤이 포커스를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08e54-105">The base class, <xref:System.Windows.Forms.UserControl>, provides keyboard routing for the child controls, thus ensuring that child controls can receive focus.</span></span> <span data-ttu-id="08e54-106">사용자 정의 컨트롤의 예제를 참조 합니다 <xref:System.Windows.Forms.UserControl> 샘플 [방법: Windows Forms 컨트롤에서 특성 적용](how-to-apply-attributes-in-windows-forms-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="08e54-106">For an example of a user control, see the <xref:System.Windows.Forms.UserControl> sample in [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="08e54-107">Visual Studio에서 Windows Forms 디자이너는 사용자 컨트롤 작성에 대 한 다양 한 디자인 타임 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="08e54-107">The Windows Forms designer in Visual Studio provides rich design-time support for authoring user controls.</span></span>  
  
-   [<span data-ttu-id="08e54-108">방법: 컨트롤에 표시 된 도구 상자 항목 선택 대화 상자</span><span class="sxs-lookup"><span data-stu-id="08e54-108">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
  
-   [<span data-ttu-id="08e54-109">연습: Designerserializationvisibilityattribute를 사용 하 여 표준 형식의 컬렉션 직렬화</span><span class="sxs-lookup"><span data-stu-id="08e54-109">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](serializing-collections-designerserializationvisibilityattribute.md)  
  
-   [<span data-ttu-id="08e54-110">연습: 시각적 개체를 사용 하 여 Windows Forms 컨트롤에서 상속C#</span><span class="sxs-lookup"><span data-stu-id="08e54-110">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
  
-   [<span data-ttu-id="08e54-111">방법: 컨트롤에 대 한 도구 상자 비트맵 제공</span><span class="sxs-lookup"><span data-stu-id="08e54-111">How to: Provide a Toolbox Bitmap for a Control</span></span>](how-to-provide-a-toolbox-bitmap-for-a-control.md)  
  
-   [<span data-ttu-id="08e54-112">방법: 에서 상속 하는 기존 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="08e54-112">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)  
  
-   [<span data-ttu-id="08e54-113">연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버그</span><span class="sxs-lookup"><span data-stu-id="08e54-113">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
  
-   [<span data-ttu-id="08e54-114">방법: Control 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="08e54-114">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)  
  
-   [<span data-ttu-id="08e54-115">방법: UserControl의 런타임 동작 테스트</span><span class="sxs-lookup"><span data-stu-id="08e54-115">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
  
-   [<span data-ttu-id="08e54-116">방법: 디자인 타임에 컨트롤을 폼의 가장자리에 맞춤</span><span class="sxs-lookup"><span data-stu-id="08e54-116">How to: Align a Control to the Edges of Forms at Design Time</span></span>](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
  
-   [<span data-ttu-id="08e54-117">방법: UserControl 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="08e54-117">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)  
  
-   [<span data-ttu-id="08e54-118">방법: Windows forms 컨트롤 작성</span><span class="sxs-lookup"><span data-stu-id="08e54-118">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)  
  
-   [<span data-ttu-id="08e54-119">방법: 복합 컨트롤 제작</span><span class="sxs-lookup"><span data-stu-id="08e54-119">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)  
  
-   [<span data-ttu-id="08e54-120">연습: Visual Basic에서 합성 컨트롤 제작</span><span class="sxs-lookup"><span data-stu-id="08e54-120">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)  
  
-   [<span data-ttu-id="08e54-121">연습: 시각적 개체를 사용 하 여 복합 컨트롤 제작C#</span><span class="sxs-lookup"><span data-stu-id="08e54-121">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
  
-   [<span data-ttu-id="08e54-122">연습: Visual Basic을 사용한 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="08e54-122">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
  
-   [<span data-ttu-id="08e54-123">연습: Visual Studio 디자인 타임 기능을 활용 하는 Windows Forms 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="08e54-123">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)  
  
-   <span data-ttu-id="08e54-124">[방법: 디자인 타임 기능을 활용 하는 Windows Forms 컨트롤 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="08e54-124">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08e54-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="08e54-125">See also</span></span>

- [<span data-ttu-id="08e54-126">방법: Windows Forms 컨트롤에서 특성 적용</span><span class="sxs-lookup"><span data-stu-id="08e54-126">How to: Apply Attributes in Windows Forms Controls</span></span>](how-to-apply-attributes-in-windows-forms-controls.md)
- [<span data-ttu-id="08e54-127">.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="08e54-127">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="08e54-128">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="08e54-128">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
