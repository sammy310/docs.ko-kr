---
title: '연습: WindowsFormsHost 요소를 사용하여 속성 매핑'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
ms.openlocfilehash: 94d175ec58f35b7e807786c221437d05c605c0bc
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974220"
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a><span data-ttu-id="47dcf-102">연습: WindowsFormsHost 요소를 사용하여 속성 매핑</span><span class="sxs-lookup"><span data-stu-id="47dcf-102">Walkthrough: Mapping Properties Using the WindowsFormsHost Element</span></span>

<span data-ttu-id="47dcf-103">이 연습에서는 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> 속성을 사용 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성을 호스트 된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 해당 속성에 매핑하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> property to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

<span data-ttu-id="47dcf-104">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="47dcf-105">프로젝트 만들기.</span><span class="sxs-lookup"><span data-stu-id="47dcf-105">Creating the project.</span></span>

- <span data-ttu-id="47dcf-106">애플리케이션 레이아웃 정의.</span><span class="sxs-lookup"><span data-stu-id="47dcf-106">Defining the application layout.</span></span>

- <span data-ttu-id="47dcf-107">새 속성 매핑 정의.</span><span class="sxs-lookup"><span data-stu-id="47dcf-107">Defining a new property mapping.</span></span>

- <span data-ttu-id="47dcf-108">기본 속성 매핑 제거.</span><span class="sxs-lookup"><span data-stu-id="47dcf-108">Removing a default property mapping.</span></span>

- <span data-ttu-id="47dcf-109">기본 속성 매핑 바꾸기.</span><span class="sxs-lookup"><span data-stu-id="47dcf-109">Replacing a default property mapping.</span></span>

- <span data-ttu-id="47dcf-110">기본 속성 매핑 확장.</span><span class="sxs-lookup"><span data-stu-id="47dcf-110">Extending a default property mapping.</span></span>

<span data-ttu-id="47dcf-111">이 연습에서 설명 하는 작업의 전체 코드 목록은 [WindowsFormsHost 요소 샘플을 사용 하 여 속성 매핑](https://go.microsoft.com/fwlink/?LinkID=160019)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47dcf-111">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the WindowsFormsHost Element Sample](https://go.microsoft.com/fwlink/?LinkID=160019).</span></span>

<span data-ttu-id="47dcf-112">작업이 완료 되 면 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 해당 속성에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성을 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-112">When you are finished, you will be able to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="47dcf-113">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="47dcf-113">Prerequisites</span></span>

<span data-ttu-id="47dcf-114">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-114">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="47dcf-115">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="47dcf-115">Visual Studio 2017</span></span>

## <a name="create-and-set-up-the-project"></a><span data-ttu-id="47dcf-116">프로젝트를 만들고 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-116">Create and set up the project</span></span>

1. <span data-ttu-id="47dcf-117">`PropertyMappingWithWfhSample`이라는 **WPF 앱** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-117">Create a **WPF App** project named `PropertyMappingWithWfhSample`.</span></span>

2. <span data-ttu-id="47dcf-118">**솔루션 탐색기**에서 windows integration .Dll 이라는 windows양식 통합 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-118">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="47dcf-119">**솔루션 탐색기**에서 Drawing 및 system.xml 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-119">In **Solution Explorer**, add references to the System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="defining-the-application-layout"></a><span data-ttu-id="47dcf-120">애플리케이션 레이아웃 정의</span><span class="sxs-lookup"><span data-stu-id="47dcf-120">Defining the Application Layout</span></span>

<span data-ttu-id="47dcf-121">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]기반 응용 프로그램은 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소를 사용 하 여 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-121">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

### <a name="to-define-the-application-layout"></a><span data-ttu-id="47dcf-122">애플리케이션 레이아웃을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="47dcf-122">To define the application layout</span></span>

1. <span data-ttu-id="47dcf-123">WPF 디자이너에서 Window1을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-123">Open Window1.xaml in the WPF Designer.</span></span>

2. <span data-ttu-id="47dcf-124">기존 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-124">Replace the existing code with the following code.</span></span>

     [!code-xaml[PropertyMappingWithWfhSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]

3. <span data-ttu-id="47dcf-125">코드 편집기에서 Window1.xaml.cs를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-125">Open Window1.xaml.cs in the Code Editor.</span></span>

4. <span data-ttu-id="47dcf-126">파일의 맨 위에서 다음 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-126">At the top of the file, import the following namespaces.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#20](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]

## <a name="defining-a-new-property-mapping"></a><span data-ttu-id="47dcf-127">새 속성 매핑 정의</span><span class="sxs-lookup"><span data-stu-id="47dcf-127">Defining a New Property Mapping</span></span>

<span data-ttu-id="47dcf-128"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 몇 가지 기본 속성 매핑을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-128">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element provides several default property mappings.</span></span> <span data-ttu-id="47dcf-129"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>에서 <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> 메서드를 호출 하 여 새 속성 매핑을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-129">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-define-a-new-property-mapping"></a><span data-ttu-id="47dcf-130">새 속성 매핑을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="47dcf-130">To define a new property mapping</span></span>

- <span data-ttu-id="47dcf-131">`Window1` 클래스에 대 한 정의에 다음 코드를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-131">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]

     <span data-ttu-id="47dcf-132">`AddClipMapping` 메서드는 <xref:System.Windows.UIElement.Clip%2A> 속성에 대 한 새 매핑을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-132">The `AddClipMapping` method adds a new mapping for the <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="47dcf-133">`OnClipChange` 메서드는 <xref:System.Windows.UIElement.Clip%2A> 속성을 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A> 속성으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-133">The `OnClipChange` method translates the <xref:System.Windows.UIElement.Clip%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="47dcf-134">`Window1_SizeChanged` 메서드는 창의 <xref:System.Windows.FrameworkElement.SizeChanged> 이벤트를 처리 하 고 클리핑 영역의 크기를 응용 프로그램 창에 맞게 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-134">The `Window1_SizeChanged` method handles the window's <xref:System.Windows.FrameworkElement.SizeChanged> event and sizes the clipping region to fit the application window.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="47dcf-135">기본 속성 매핑 제거</span><span class="sxs-lookup"><span data-stu-id="47dcf-135">Removing a Default Property Mapping</span></span>

<span data-ttu-id="47dcf-136"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>에서 <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> 메서드를 호출 하 여 기본 속성 매핑을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-136">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="47dcf-137">기본 속성 매핑을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="47dcf-137">To remove a default property mapping</span></span>

- <span data-ttu-id="47dcf-138">`Window1` 클래스에 대 한 정의에 다음 코드를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-138">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]

     <span data-ttu-id="47dcf-139">`RemoveCursorMapping` 메서드는 <xref:System.Windows.FrameworkElement.Cursor%2A> 속성의 기본 매핑을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-139">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.FrameworkElement.Cursor%2A> property.</span></span>

## <a name="replacing-a-default-property-mapping"></a><span data-ttu-id="47dcf-140">기본 속성 매핑 바꾸기</span><span class="sxs-lookup"><span data-stu-id="47dcf-140">Replacing a Default Property Mapping</span></span>

<span data-ttu-id="47dcf-141">기본 매핑을 제거 하 고 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>에서 <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> 메서드를 호출 하 여 기본 속성 매핑을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-141">Replace a default property mapping by removing the default mapping and calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-replace-a-default-property-mapping"></a><span data-ttu-id="47dcf-142">기본 속성 매핑을 바꾸려면</span><span class="sxs-lookup"><span data-stu-id="47dcf-142">To replace a default property mapping</span></span>

- <span data-ttu-id="47dcf-143">`Window1` 클래스에 대 한 정의에 다음 코드를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-143">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]

     <span data-ttu-id="47dcf-144">`ReplaceFlowDirectionMapping` 메서드는 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성의 기본 매핑을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-144">The `ReplaceFlowDirectionMapping` method replaces the default mapping for the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property.</span></span>

     <span data-ttu-id="47dcf-145">`OnFlowDirectionChange` 메서드는 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성을 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A> 속성으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-145">The `OnFlowDirectionChange` method translates the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A> property.</span></span>

     <span data-ttu-id="47dcf-146">`cb_CheckedChanged` 메서드는 <xref:System.Windows.Forms.CheckBox> 컨트롤의 <xref:System.Windows.Forms.CheckBox.CheckedChanged> 이벤트를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-146">The `cb_CheckedChanged` method handles the <xref:System.Windows.Forms.CheckBox.CheckedChanged> event on the <xref:System.Windows.Forms.CheckBox> control.</span></span> <span data-ttu-id="47dcf-147"><xref:System.Windows.Forms.CheckBox.CheckState%2A> 속성의 값을 기반으로 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-147">It assigns the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property based on the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="47dcf-148">기본 속성 매핑 확장</span><span class="sxs-lookup"><span data-stu-id="47dcf-148">Extending a Default Property Mapping</span></span>

<span data-ttu-id="47dcf-149">기본 속성 매핑을 사용하고 고유 매핑으로 확장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-149">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="47dcf-150">기본 속성 매핑을 확장하려면</span><span class="sxs-lookup"><span data-stu-id="47dcf-150">To extend a default property mapping</span></span>

- <span data-ttu-id="47dcf-151">`Window1` 클래스에 대 한 정의에 다음 코드를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-151">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]

     <span data-ttu-id="47dcf-152">`ExtendBackgroundMapping` 메서드는 기존 <xref:System.Windows.Controls.Control.Background%2A> 속성 매핑에 사용자 지정 속성 번역기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-152">The `ExtendBackgroundMapping` method adds a custom property translator to the existing <xref:System.Windows.Controls.Control.Background%2A> property mapping.</span></span>

     <span data-ttu-id="47dcf-153">`OnBackgroundChange` 메서드는 호스트 된 컨트롤의 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성에 특정 이미지를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-153">The `OnBackgroundChange` method assigns a specific image to the hosted control's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span> <span data-ttu-id="47dcf-154">`OnBackgroundChange` 메서드는 기본 속성 매핑이 적용 된 후에 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-154">The `OnBackgroundChange` method is called after the default property mapping is applied.</span></span>

## <a name="initializing-your-property-mappings"></a><span data-ttu-id="47dcf-155">속성 매핑 초기화</span><span class="sxs-lookup"><span data-stu-id="47dcf-155">Initializing Your Property Mappings</span></span>

<span data-ttu-id="47dcf-156"><xref:System.Windows.FrameworkElement.Loaded> 이벤트 처리기에서 앞에서 설명한 메서드를 호출 하 여 속성 매핑을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-156">Set up your property mappings by calling the previously described methods in the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>

### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="47dcf-157">속성 매핑을 초기화하려면</span><span class="sxs-lookup"><span data-stu-id="47dcf-157">To initialize your property mappings</span></span>

1. <span data-ttu-id="47dcf-158">`Window1` 클래스에 대 한 정의에 다음 코드를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-158">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]

     <span data-ttu-id="47dcf-159">`WindowLoaded` 메서드는 <xref:System.Windows.FrameworkElement.Loaded> 이벤트를 처리 하 고 다음 초기화를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-159">The `WindowLoaded` method handles the <xref:System.Windows.FrameworkElement.Loaded> event and performs the following initialization.</span></span>

    - <span data-ttu-id="47dcf-160">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox> 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-160">Creates a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox> control.</span></span>

    - <span data-ttu-id="47dcf-161">연습에서 이전에 정의한 메서드를 호출하여 속성 매핑을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-161">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    - <span data-ttu-id="47dcf-162">매핑된 속성에 초기 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-162">Assigns initial values to the mapped properties.</span></span>

2. <span data-ttu-id="47dcf-163">**F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-163">Press **F5** to build and run the application.</span></span> <span data-ttu-id="47dcf-164"><xref:System.Windows.FrameworkElement.FlowDirection%2A> 매핑의 효과를 확인 하려면이 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-164">Click the check box to see the effect of the <xref:System.Windows.FrameworkElement.FlowDirection%2A> mapping.</span></span> <span data-ttu-id="47dcf-165">확인란을 클릭하면 레이아웃이 왼쪽에서 오른쪽으로의 방향을 반대로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="47dcf-165">When you click the check box, the layout reverses its left-right orientation.</span></span>

## <a name="see-also"></a><span data-ttu-id="47dcf-166">참조</span><span class="sxs-lookup"><span data-stu-id="47dcf-166">See also</span></span>

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="47dcf-167">Windows Forms 및 WPF 속성 매핑</span><span class="sxs-lookup"><span data-stu-id="47dcf-167">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="47dcf-168">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="47dcf-168">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="47dcf-169">연습: WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="47dcf-169">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
