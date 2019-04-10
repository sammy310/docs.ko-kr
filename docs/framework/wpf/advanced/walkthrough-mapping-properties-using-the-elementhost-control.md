---
title: '연습: ElementHost 컨트롤을 사용하여 속성 매핑'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: 360f19e558f97e1807b329ad18e429fa893bbf86
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59300920"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a><span data-ttu-id="a5edb-102">연습: ElementHost 컨트롤을 사용하여 속성 매핑</span><span class="sxs-lookup"><span data-stu-id="a5edb-102">Walkthrough: Mapping Properties Using the ElementHost Control</span></span>

<span data-ttu-id="a5edb-103">이 연습에서는 사용 하는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> 매핑할 속성을 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 속성을 해당 속성에 호스트 된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> property to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element.</span></span>

<span data-ttu-id="a5edb-104">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-104">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="a5edb-105">프로젝트 만들기.</span><span class="sxs-lookup"><span data-stu-id="a5edb-105">Creating the project.</span></span>

-   <span data-ttu-id="a5edb-106">새 속성 매핑 정의.</span><span class="sxs-lookup"><span data-stu-id="a5edb-106">Defining a new property mapping.</span></span>

-   <span data-ttu-id="a5edb-107">기본 속성 매핑 제거.</span><span class="sxs-lookup"><span data-stu-id="a5edb-107">Removing a default property mapping.</span></span>

-   <span data-ttu-id="a5edb-108">기본 속성 매핑 확장.</span><span class="sxs-lookup"><span data-stu-id="a5edb-108">Extending a default property mapping.</span></span>

<span data-ttu-id="a5edb-109">이 연습에 설명 된 작업의 전체 코드 목록은 참조 하세요 [ElementHost 컨트롤 샘플을 사용 하 여 속성 매핑](https://go.microsoft.com/fwlink/?LinkID=160018)합니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-109">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the ElementHost Control Sample](https://go.microsoft.com/fwlink/?LinkID=160018).</span></span>

<span data-ttu-id="a5edb-110">에 매핑할 수 있게 됩니다 완료 했으면 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 속성을 해당 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 호스팅된 요소 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-110">When you are finished, you will be able to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties on a hosted element.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a5edb-111">전제 조건</span><span class="sxs-lookup"><span data-stu-id="a5edb-111">Prerequisites</span></span>

<span data-ttu-id="a5edb-112">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-112">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="a5edb-113">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="a5edb-113">Visual Studio 2017</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="a5edb-114">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="a5edb-114">Creating the Project</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="a5edb-115">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="a5edb-115">To create the project</span></span>

1. <span data-ttu-id="a5edb-116">만들기는 **Windows Forms 앱** 라는 프로젝트 `PropertyMappingWithElementHost`합니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-116">Create a **Windows Forms App** project named `PropertyMappingWithElementHost`.</span></span>

2. <span data-ttu-id="a5edb-117">**솔루션 탐색기**, 다음에 대 한 참조를 추가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-117">In **Solution Explorer**, add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies.</span></span>

    -   <span data-ttu-id="a5edb-118">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="a5edb-118">PresentationCore</span></span>

    -   <span data-ttu-id="a5edb-119">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="a5edb-119">PresentationFramework</span></span>

    -   <span data-ttu-id="a5edb-120">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="a5edb-120">WindowsBase</span></span>

    -   <span data-ttu-id="a5edb-121">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="a5edb-121">WindowsFormsIntegration</span></span>

3. <span data-ttu-id="a5edb-122">맨 위에 다음 코드를 복사 합니다 `Form1` 코드 파일.</span><span class="sxs-lookup"><span data-stu-id="a5edb-122">Copy the following code into the top of the `Form1` code file.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#10](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4. <span data-ttu-id="a5edb-123">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-123">Open `Form1` in the Windows Forms Designer.</span></span> <span data-ttu-id="a5edb-124">에 대 한 이벤트 처리기를 추가 하려면 폼을 두 번 클릭 합니다 <xref:System.Windows.Forms.Form.Load> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-124">Double-click the form to add an event handler for the <xref:System.Windows.Forms.Form.Load> event.</span></span>

5. <span data-ttu-id="a5edb-125">Windows Forms 디자이너로 돌아가서 폼에 대 한 이벤트 처리기를 추가 <xref:System.Windows.Forms.Control.Resize> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-125">Return to the Windows Forms Designer and add an event handler for the form's <xref:System.Windows.Forms.Control.Resize> event.</span></span> <span data-ttu-id="a5edb-126">자세한 내용은 [방법: 디자이너를 사용 하 여 이벤트 처리기를 만들](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-126">For more information, see [How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

6. <span data-ttu-id="a5edb-127">선언를 <xref:System.Windows.Forms.Integration.ElementHost> 필드에 `Form1` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-127">Declare an <xref:System.Windows.Forms.Integration.ElementHost> field in the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#16](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a><span data-ttu-id="a5edb-128">새 속성 매핑 정의</span><span class="sxs-lookup"><span data-stu-id="a5edb-128">Defining New Property Mappings</span></span>

<span data-ttu-id="a5edb-129"><xref:System.Windows.Forms.Integration.ElementHost> 컨트롤 몇 가지 기본 속성 매핑의 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-129">The <xref:System.Windows.Forms.Integration.ElementHost> control provides several default property mappings.</span></span> <span data-ttu-id="a5edb-130">호출 하 여 새 속성 매핑을 추가 합니다 <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> 메서드를 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-130">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-define-new-property-mappings"></a><span data-ttu-id="a5edb-131">새 속성 매핑을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="a5edb-131">To define new property mappings</span></span>

1. <span data-ttu-id="a5edb-132">다음 코드에 대 한 정의를 복사 합니다 `Form1` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-132">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     <span data-ttu-id="a5edb-133">합니다 `AddMarginMapping` 에 대 한 새 매핑을 추가 하는 메서드는 <xref:System.Windows.Forms.Control.Margin%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-133">The `AddMarginMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span>

     <span data-ttu-id="a5edb-134">`OnMarginChange` 메서드 변환 하는 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="a5edb-134">The `OnMarginChange` method translates the <xref:System.Windows.Forms.Control.Margin%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> property.</span></span>

2. <span data-ttu-id="a5edb-135">다음 코드에 대 한 정의를 복사 합니다 `Form1` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-135">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     <span data-ttu-id="a5edb-136">합니다 `AddRegionMapping` 에 대 한 새 매핑을 추가 하는 메서드는 <xref:System.Windows.Forms.Control.Region%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-136">The `AddRegionMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="a5edb-137">`OnRegionChange` 메서드 변환 하는 <xref:System.Windows.Forms.Control.Region%2A> 속성을 합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="a5edb-137">The `OnRegionChange` method translates the <xref:System.Windows.Forms.Control.Region%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="a5edb-138">합니다 `Form1_Resize` 양식의 처리 <xref:System.Windows.Forms.Control.Resize> 이벤트 호스 티 드 요소에 맞게 클리핑 영역의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-138">The `Form1_Resize` method handles the form's <xref:System.Windows.Forms.Control.Resize> event and sizes the clipping region to fit the hosted element.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="a5edb-139">기본 속성 매핑 제거</span><span class="sxs-lookup"><span data-stu-id="a5edb-139">Removing a Default Property Mapping</span></span>

<span data-ttu-id="a5edb-140">호출 하 여 기본 속성 매핑을 제거 합니다 <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> 메서드를 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-140">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="a5edb-141">기본 속성 매핑을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="a5edb-141">To remove a default property mapping</span></span>

-   <span data-ttu-id="a5edb-142">다음 코드에 대 한 정의를 복사 합니다 `Form1` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-142">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     <span data-ttu-id="a5edb-143">합니다 `RemoveCursorMapping` 에 대 한 기본 매핑을 삭제 하는 메서드를 <xref:System.Windows.Forms.Control.Cursor%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-143">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.Forms.Control.Cursor%2A> property.</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="a5edb-144">기본 속성 매핑 확장</span><span class="sxs-lookup"><span data-stu-id="a5edb-144">Extending a Default Property Mapping</span></span>

<span data-ttu-id="a5edb-145">기본 속성 매핑을 사용하고 고유 매핑으로 확장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-145">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="a5edb-146">기본 속성 매핑을 확장하려면</span><span class="sxs-lookup"><span data-stu-id="a5edb-146">To extend a default property mapping</span></span>

-   <span data-ttu-id="a5edb-147">다음 코드에 대 한 정의를 복사 합니다 `Form1` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-147">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     <span data-ttu-id="a5edb-148">합니다 `ExtendBackColorMapping` 메서드를 기존 사용자 지정 속성 변환기를 추가 <xref:System.Windows.Forms.Control.BackColor%2A> 속성 매핑.</span><span class="sxs-lookup"><span data-stu-id="a5edb-148">The `ExtendBackColorMapping` method adds a custom property translator to the existing <xref:System.Windows.Forms.Control.BackColor%2A> property mapping.</span></span>

     <span data-ttu-id="a5edb-149">합니다 `OnBackColorChange` 메서드를 호스팅된 컨트롤의 이미지를 할당 <xref:System.Windows.Controls.Control.Background%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-149">The `OnBackColorChange` method assigns a specific image to the hosted control's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="a5edb-150">`OnBackColorChange` 기본 속성 매핑을 적용 된 후 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-150">The `OnBackColorChange` method is called after the default property mapping is applied.</span></span>

## <a name="initialize-your-property-mappings"></a><span data-ttu-id="a5edb-151">속성 매핑을 초기화합니다</span><span class="sxs-lookup"><span data-stu-id="a5edb-151">Initialize your property mappings</span></span>

1. <span data-ttu-id="a5edb-152">다음 코드에 대 한 정의를 복사 합니다 `Form1` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-152">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     <span data-ttu-id="a5edb-153">`Form1_Load` 메서드 핸들을 <xref:System.Windows.Forms.Form.Load> 이벤트 하 고 다음과 같은 초기화를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-153">The `Form1_Load` method handles the <xref:System.Windows.Forms.Form.Load> event and performs the following initialization.</span></span>

    -   <span data-ttu-id="a5edb-154">만듭니다는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-154">Creates a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> element.</span></span>

    -   <span data-ttu-id="a5edb-155">연습에서 이전에 정의한 메서드를 호출하여 속성 매핑을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-155">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    -   <span data-ttu-id="a5edb-156">매핑된 속성에 초기 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-156">Assigns initial values to the mapped properties.</span></span>

2. <span data-ttu-id="a5edb-157">F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a5edb-157">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5edb-158">참고자료</span><span class="sxs-lookup"><span data-stu-id="a5edb-158">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="a5edb-159">Windows Forms 및 WPF 속성 매핑</span><span class="sxs-lookup"><span data-stu-id="a5edb-159">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="a5edb-160">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="a5edb-160">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="a5edb-161">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="a5edb-161">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)