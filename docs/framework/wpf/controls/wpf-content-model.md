---
title: 콘텐츠 모델
ms.date: 03/30/2017
helpviewer_keywords:
- UIElement class [WPF], displaying content
- content model [WPF], controls
- controls [WPF], displaying text
- content display [WPF], controls
- controls [WPF], formatting text
- displaying content [WPF]
- arbitrary content classes [WPF], content model
- ContentControl class [WPF], displaying content
ms.assetid: 214da5ef-547a-4cf8-9b07-4aa8a0e52cdd
ms.openlocfilehash: ec4e96c0883489135b77f09a3c19f144cb4d30bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187400"
---
# <a name="wpf-content-model"></a><span data-ttu-id="ae0f1-102">WPF 콘텐츠 모델</span><span class="sxs-lookup"><span data-stu-id="ae0f1-102">WPF Content Model</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="ae0f1-103">는 다양한 형식의 콘텐츠를 표시하는 것을 기본 용도로 하는 많은 컨트롤 형식 및 컨트롤과 유사한 형식을 제공하는 프레젠테이션 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-103">is a presentation platform that provides many controls and control-like types whose primary purpose is to display different types of content.</span></span> <span data-ttu-id="ae0f1-104">사용할 컨트롤이나 파생시킬 컨트롤을 결정하려면 특정 컨트롤이 가장 잘 표시할 수 있는 개체 유형을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-104">To determine which control to use or which control to derive from, you should understand the kinds of objects a particular control can best display.</span></span>  
  
 <span data-ttu-id="ae0f1-105">이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 형식 및 컨트롤과 비슷한 형식에 대한 콘텐츠 모델을 요약하여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-105">This topic summarizes the content model for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control and control-like types.</span></span> <span data-ttu-id="ae0f1-106">콘텐츠 모델은 컨트롤에 사용될 수 있는 컨트롤에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-106">The content model describes what content can be used in a control.</span></span> <span data-ttu-id="ae0f1-107">또한 이 항목에서는 각 컨트롤 모델에 대한 콘텐츠 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-107">This topic also lists the content properties for each content model.</span></span> <span data-ttu-id="ae0f1-108">콘텐츠 속성은 개체의 콘텐츠를 저장하는 데 사용되는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-108">A content property is a property that is used to store the content of the object.</span></span>  

<a name="classes_that_contain_arbitrary_content"></a>
## <a name="classes-that-contain-arbitrary-content"></a><span data-ttu-id="ae0f1-109">임의의 콘텐츠가 들어 있는 클래스</span><span class="sxs-lookup"><span data-stu-id="ae0f1-109">Classes That Contain Arbitrary Content</span></span>  
 <span data-ttu-id="ae0f1-110">일부 컨트롤에는 문자열, <xref:System.DateTime> 개체 또는 추가 항목에 대한 컨테이너인 <xref:System.Windows.UIElement> a와 같은 모든 형식의 개체가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-110">Some controls can contain an object of any type, such as a string, a <xref:System.DateTime> object, or a <xref:System.Windows.UIElement> that is a container for additional items.</span></span> <span data-ttu-id="ae0f1-111">예를 들어, <xref:System.Windows.Controls.Button> a는 이미지와 일부 텍스트를 포함할 수 있습니다. 또는 <xref:System.Windows.Controls.CheckBox> 의 값을 포함할 수 <xref:System.DateTime.Now%2A?displayProperty=nameWithType>있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-111">For example, a <xref:System.Windows.Controls.Button> can contain an image and some text; or a <xref:System.Windows.Controls.CheckBox> can contain the value of <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span></span>  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="ae0f1-112">에는 임의의 콘텐츠가 들어 있는 네 개의 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-112">has four classes that can contain arbitrary content.</span></span> <span data-ttu-id="ae0f1-113">다음 표에는 에서 상속되는 <xref:System.Windows.Controls.Control>클래스가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-113">The following table lists the classes, which inherit from <xref:System.Windows.Controls.Control>.</span></span>  
  
|<span data-ttu-id="ae0f1-114">임의의 콘텐츠가 들어 있는 클래스</span><span class="sxs-lookup"><span data-stu-id="ae0f1-114">Class that contains arbitrary content</span></span>|<span data-ttu-id="ae0f1-115">콘텐츠</span><span class="sxs-lookup"><span data-stu-id="ae0f1-115">Content</span></span>|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="ae0f1-116">임의의 단일 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-116">A single arbitrary object.</span></span>|  
|<xref:System.Windows.Controls.HeaderedContentControl>|<span data-ttu-id="ae0f1-117">헤더 및 단일 항목이며 둘 모두 임의의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-117">A header and a single item, both of which are arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.ItemsControl>|<span data-ttu-id="ae0f1-118">임의 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-118">A collection of arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|<span data-ttu-id="ae0f1-119">헤더와 항목 컬렉션이며 모두 임의의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-119">A header and a collection of items, all of which are arbitrary objects.</span></span>|  
  
 <span data-ttu-id="ae0f1-120">이러한 클래스에서 상속하는 컨트롤은 동일한 형식의 콘텐츠를 포함하며 콘텐츠를 동일한 방식으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-120">Controls that inherit from these classes can contain the same type of content and treat the content in the same way.</span></span> <span data-ttu-id="ae0f1-121">다음 그림에서는 이미지와 일부 텍스트를 포함하는 각 콘텐츠 모델의 컨트롤 을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-121">The following illustration shows one control from each content model that contains an image and some text:</span></span>  
  
 ![각 콘텐츠 모델에서 하나씩 네 가지 컨트롤을 보여 주는 스크린샷입니다.](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a><span data-ttu-id="ae0f1-123">임의의 단일 개체가 들어 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ae0f1-123">Controls That Contain a Single Arbitrary Object</span></span>  
 <span data-ttu-id="ae0f1-124">클래스에는 <xref:System.Windows.Controls.ContentControl> 임의의 콘텐츠의 단일 조각이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-124">The <xref:System.Windows.Controls.ContentControl> class contains a single piece of arbitrary content.</span></span> <span data-ttu-id="ae0f1-125">해당 콘텐츠 속성은 <xref:System.Windows.Controls.ContentControl.Content%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-125">Its content property is <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="ae0f1-126">다음 컨트롤은 <xref:System.Windows.Controls.ContentControl> 해당 콘텐츠 모델에서 상속및 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-126">The following controls inherit from <xref:System.Windows.Controls.ContentControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Button>  
  
- <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
- <xref:System.Windows.Controls.CheckBox>  
  
- <xref:System.Windows.Controls.ComboBoxItem>  
  
- <xref:System.Windows.Controls.ContentControl>  
  
- <xref:System.Windows.Controls.Frame>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GroupItem>  
  
- <xref:System.Windows.Controls.Label>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Navigation.NavigationWindow>  
  
- <xref:System.Windows.Controls.RadioButton>  
  
- <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
- <xref:System.Windows.Controls.ScrollViewer>  
  
- <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
- <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
- <xref:System.Windows.Controls.ToolTip>  
  
- <xref:System.Windows.Controls.UserControl>  
  
- <xref:System.Windows.Window>  
  
 <span data-ttu-id="ae0f1-127">다음 그림에서는 문자열, <xref:System.Windows.Controls.ContentControl.Content%2A> <xref:System.DateTime> 개체, <xref:System.Windows.Shapes.Rectangle>A 및 <xref:System.Windows.Controls.Panel> a를 포함하는 문자열로 설정된 <xref:System.Windows.Shapes.Ellipse> 네 <xref:System.Windows.Controls.TextBlock>개의 단추를 보여 주며 다음과 같은 단추를 보여 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-127">The following illustration shows four buttons whose <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a string, a <xref:System.DateTime> object, a <xref:System.Windows.Shapes.Rectangle>, and a <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>:</span></span>  
  
 ![콘텐츠 유형이 다른 네 개의 단추를 보여 주는 스크린샷입니다.](./media/wpf-content-model/control-content-model-buttons.png)  
  
 <span data-ttu-id="ae0f1-129"><xref:System.Windows.Controls.ContentControl.Content%2A> 속성을 설정하는 방법에 대한 예는 <xref:System.Windows.Controls.ContentControl>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-129">For an example of how to set the <xref:System.Windows.Controls.ContentControl.Content%2A> property, see <xref:System.Windows.Controls.ContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a><span data-ttu-id="ae0f1-130">헤더와 임의의 단일 개체가 들어 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ae0f1-130">Controls That Contain a Header and a Single Arbitrary Object</span></span>  
 <span data-ttu-id="ae0f1-131">클래스에서 <xref:System.Windows.Controls.HeaderedContentControl> 상속 <xref:System.Windows.Controls.ContentControl> 하 고 헤더와 콘텐츠를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-131">The <xref:System.Windows.Controls.HeaderedContentControl> class inherits from <xref:System.Windows.Controls.ContentControl> and displays content with a header.</span></span> <span data-ttu-id="ae0f1-132">에서 에서 콘텐츠 속성을 <xref:System.Windows.Controls.ContentControl.Content%2A>상속 <xref:System.Windows.Controls.ContentControl> 하 고 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 형식의 <xref:System.Object>속성을 정의 합니다. 따라서 둘 다 임의의 개체일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-132">It inherits the content property, <xref:System.Windows.Controls.ContentControl.Content%2A>, from <xref:System.Windows.Controls.ContentControl> and defines the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> property that is of type <xref:System.Object>; therefore, both can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="ae0f1-133">다음 컨트롤은 <xref:System.Windows.Controls.HeaderedContentControl> 해당 콘텐츠 모델에서 상속및 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-133">The following controls inherit from <xref:System.Windows.Controls.HeaderedContentControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Expander>  
  
- <xref:System.Windows.Controls.GroupBox>  
  
- <xref:System.Windows.Controls.TabItem>  
  
 <span data-ttu-id="ae0f1-134">다음 그림에서는 <xref:System.Windows.Controls.TabItem> 두 개체를 보여 주십습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-134">The following illustration shows two <xref:System.Windows.Controls.TabItem> objects.</span></span> <span data-ttu-id="ae0f1-135">첫 <xref:System.Windows.Controls.TabItem> 번째 <xref:System.Windows.UIElement> 개체에는 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 와 <xref:System.Windows.Controls.ContentControl.Content%2A>가.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-135">The first <xref:System.Windows.Controls.TabItem> has <xref:System.Windows.UIElement> objects as the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="ae0f1-136">과 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 를 포함하는 <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Shapes.Ellipse> 로 <xref:System.Windows.Controls.TextBlock>설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-136">The <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="ae0f1-137">과 <xref:System.Windows.Controls.ContentControl.Content%2A> 를 포함하는 <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.TextBlock> 로 <xref:System.Windows.Controls.Label>설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-137">The <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains a <xref:System.Windows.Controls.TextBlock> and a <xref:System.Windows.Controls.Label>.</span></span> <span data-ttu-id="ae0f1-138">두 <xref:System.Windows.Controls.TabItem> 번째 문자열은 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 에 <xref:System.Windows.Controls.TextBlock> 문자열과 <xref:System.Windows.Controls.ContentControl.Content%2A>에 있는 문자열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-138">The second <xref:System.Windows.Controls.TabItem> has a string in the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and a <xref:System.Windows.Controls.TextBlock> in the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span>  
  
 ![헤더 속성에서 다른 형식을 사용하는 TabControl입니다.](./media/wpf-content-model/control-content-model-tab.png)  
  
 <span data-ttu-id="ae0f1-140">개체를 만드는 <xref:System.Windows.Controls.TabItem> 방법의 예는 <xref:System.Windows.Controls.HeaderedContentControl>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-140">For an example of how to create <xref:System.Windows.Controls.TabItem> objects, see <xref:System.Windows.Controls.HeaderedContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a><span data-ttu-id="ae0f1-141">임의 개체의 컬렉션을 포함하는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ae0f1-141">Controls That Contain a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="ae0f1-142">클래스는 <xref:System.Windows.Controls.ItemsControl> <xref:System.Windows.Controls.Control> 문자열, 개체 또는 기타 요소와 같은 여러 항목을 상속하고 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-142">The <xref:System.Windows.Controls.ItemsControl> class inherits from <xref:System.Windows.Controls.Control> and can contain multiple items, such as strings, objects, or other elements.</span></span> <span data-ttu-id="ae0f1-143">해당 콘텐츠 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성은 및 <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-143">Its content properties are <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span></span> <span data-ttu-id="ae0f1-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>은 일반적으로 데이터 <xref:System.Windows.Controls.ItemsControl> 컬렉션으로 채우는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> is typically used to populate the <xref:System.Windows.Controls.ItemsControl> with a data collection.</span></span> <span data-ttu-id="ae0f1-145">컬렉션을 사용하여 <xref:System.Windows.Controls.ItemsControl>을 채우기 위해 사용하지 않으려면 <xref:System.Windows.Controls.ItemsControl.Items%2A> 속성을 사용하여 항목을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-145">If you do not want to use a collection to populate the <xref:System.Windows.Controls.ItemsControl>, you can add items by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="ae0f1-146">다음 컨트롤은 <xref:System.Windows.Controls.ItemsControl> 해당 콘텐츠 모델에서 상속및 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-146">The following controls inherit from <xref:System.Windows.Controls.ItemsControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Menu>  
  
- <xref:System.Windows.Controls.Primitives.MenuBase>  
  
- <xref:System.Windows.Controls.ContextMenu>  
  
- <xref:System.Windows.Controls.ComboBox>  
  
- <xref:System.Windows.Controls.ItemsControl>  
  
- <xref:System.Windows.Controls.ListBox>  
  
- <xref:System.Windows.Controls.ListView>  
  
- <xref:System.Windows.Controls.TabControl>  
  
- <xref:System.Windows.Controls.TreeView>  
  
- <xref:System.Windows.Controls.Primitives.Selector>  
  
- <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 <span data-ttu-id="ae0f1-147">다음 그림에서는 <xref:System.Windows.Controls.ListBox> 이러한 유형의 항목이 포함된 a를 보여 주며 다음과 같은 유형의 항목을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-147">The following illustration shows a <xref:System.Windows.Controls.ListBox> that contains these types of items:</span></span>  
  
- <span data-ttu-id="ae0f1-148">문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-148">A string.</span></span>  
  
- <span data-ttu-id="ae0f1-149"><xref:System.DateTime> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-149">A <xref:System.DateTime> object.</span></span>  
  
- <span data-ttu-id="ae0f1-150"><xref:System.Windows.UIElement>입니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-150">A <xref:System.Windows.UIElement>.</span></span>  
  
- <span data-ttu-id="ae0f1-151"><xref:System.Windows.Shapes.Ellipse> A와 <xref:System.Windows.Controls.TextBlock>를 포함하는 . <xref:System.Windows.Controls.Panel></span><span class="sxs-lookup"><span data-stu-id="ae0f1-151">A <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 ![네 가지 유형의 콘텐츠가 있는 ListBox를 보여 주는 스크린샷입니다.](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a><span data-ttu-id="ae0f1-153">헤더와 임의 개체의 컬렉션을 포함하는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ae0f1-153">Controls That Contain a Header and a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="ae0f1-154">클래스는 <xref:System.Windows.Controls.HeaderedItemsControl> 문자열, <xref:System.Windows.Controls.ItemsControl> 개체 또는 기타 요소 및 헤더와 같은 여러 항목을 상속하고 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-154">The <xref:System.Windows.Controls.HeaderedItemsControl> class inherits from <xref:System.Windows.Controls.ItemsControl> and can contain multiple items, such as strings, objects, or other elements, and a header.</span></span> <span data-ttu-id="ae0f1-155"><xref:System.Windows.Controls.ItemsControl> 콘텐츠 속성을 상속 하 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>고 <xref:System.Windows.Controls.ItemsControl.Items%2A>및 임의의 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 개체일 수 있는 속성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-155">It inherits the <xref:System.Windows.Controls.ItemsControl> content properties, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, and <xref:System.Windows.Controls.ItemsControl.Items%2A>, and it defines the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property that can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="ae0f1-156">다음 컨트롤은 <xref:System.Windows.Controls.HeaderedItemsControl> 해당 콘텐츠 모델에서 상속및 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-156">The following controls inherit from <xref:System.Windows.Controls.HeaderedItemsControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.MenuItem>  
  
- <xref:System.Windows.Controls.ToolBar>  
  
- <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a><span data-ttu-id="ae0f1-157">UIElement 개체 컬렉션을 포함하는 클래스</span><span class="sxs-lookup"><span data-stu-id="ae0f1-157">Classes That Contain a Collection of UIElement Objects</span></span>  
 <span data-ttu-id="ae0f1-158">클래스는 <xref:System.Windows.Controls.Panel> 자식 <xref:System.Windows.UIElement> 개체의 위치와 정렬을 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-158">The <xref:System.Windows.Controls.Panel> class positions and arranges child <xref:System.Windows.UIElement> objects.</span></span> <span data-ttu-id="ae0f1-159">해당 콘텐츠 속성은 <xref:System.Windows.Controls.Panel.Children%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-159">Its content property is <xref:System.Windows.Controls.Panel.Children%2A>.</span></span>  
  
 <span data-ttu-id="ae0f1-160">다음 클래스는 <xref:System.Windows.Controls.Panel> 클래스에서 상속되며 해당 콘텐츠 모델을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-160">The following classes inherit from the <xref:System.Windows.Controls.Panel> class and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Canvas>  
  
- <xref:System.Windows.Controls.DockPanel>  
  
- <xref:System.Windows.Controls.Grid>  
  
- <xref:System.Windows.Controls.Primitives.TabPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
- <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
- <xref:System.Windows.Controls.StackPanel>  
  
- <xref:System.Windows.Controls.VirtualizingPanel>  
  
- <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
- <xref:System.Windows.Controls.WrapPanel>  
  
 <span data-ttu-id="ae0f1-161">자세한 내용은 [패널 개요](panels-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-161">For more information, see [Panels Overview](panels-overview.md).</span></span>  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a><span data-ttu-id="ae0f1-162">UIElement의 모양에 영향을 주는 클래스</span><span class="sxs-lookup"><span data-stu-id="ae0f1-162">Classes That Affect the Appearance of a UIElement</span></span>  
 <span data-ttu-id="ae0f1-163">이 <xref:System.Windows.Controls.Decorator> 클래스는 단일 자식 <xref:System.Windows.UIElement>에 또는 그 주변에 시각 효과를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-163">The <xref:System.Windows.Controls.Decorator> class applies visual effects onto or around a single child <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="ae0f1-164">해당 콘텐츠 속성은 <xref:System.Windows.Controls.Decorator.Child%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-164">Its content property is <xref:System.Windows.Controls.Decorator.Child%2A>.</span></span> <span data-ttu-id="ae0f1-165">다음 클래스는 <xref:System.Windows.Controls.Decorator> 해당 콘텐츠 모델을 상속하고 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-165">The following classes inherit from <xref:System.Windows.Controls.Decorator> and use its content model:</span></span>  
  
- <xref:System.Windows.Documents.AdornerDecorator>  
  
- <xref:System.Windows.Controls.Border>  
  
- <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
- <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
- <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
- <xref:System.Windows.Controls.InkPresenter>  
  
- <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
- <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
- <xref:System.Windows.Controls.Viewbox>  
  
 <span data-ttu-id="ae0f1-166">다음 그림은 주변에 <xref:System.Windows.Controls.TextBox> (장식된) a를 <xref:System.Windows.Controls.Border> 보여 주어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-166">The following illustration shows a <xref:System.Windows.Controls.TextBox> that has (is decorated with) a <xref:System.Windows.Controls.Border> around it.</span></span>  
  
 <span data-ttu-id="ae0f1-167">![검은색 테두리가 있는 TextBox](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span><span class="sxs-lookup"><span data-stu-id="ae0f1-167">![TextBox with black border](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span></span>  
<span data-ttu-id="ae0f1-168">테두리가 있는 TextBlock</span><span class="sxs-lookup"><span data-stu-id="ae0f1-168">TextBlock that has a Border</span></span>  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a><span data-ttu-id="ae0f1-169">UIElement에 대한 시각적 피드백을 제공하는 클래스</span><span class="sxs-lookup"><span data-stu-id="ae0f1-169">Classes That Provide Visual Feedback About a UIElement</span></span>  
 <span data-ttu-id="ae0f1-170">클래스는 <xref:System.Windows.Documents.Adorner> 사용자에게 시각적 신호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-170">The <xref:System.Windows.Documents.Adorner> class provides visual cues to a user.</span></span> <span data-ttu-id="ae0f1-171">예를 들어 를 <xref:System.Windows.Documents.Adorner> 사용하여 요소에 기능 핸들을 추가하거나 컨트롤에 대한 상태 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-171">For example, use an <xref:System.Windows.Documents.Adorner> to add functional handles to elements or provide state information about a control.</span></span> <span data-ttu-id="ae0f1-172">클래스는 <xref:System.Windows.Documents.Adorner> 사용자 고유의 표시기를 만들 수 있도록 프레임 워크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-172">The <xref:System.Windows.Documents.Adorner> class provides a framework so that you can create your own adorners.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="ae0f1-173">는 구현된 표시기를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-173">does not provide any implemented adorners.</span></span> <span data-ttu-id="ae0f1-174">자세한 내용은 [표시기 개요](adorners-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-174">For more information, see [Adorners Overview](adorners-overview.md).</span></span>  
  
<a name="classes_that_enable_users_to_enter_text"></a>
## <a name="classes-that-enable-users-to-enter-text"></a><span data-ttu-id="ae0f1-175">사용자가 텍스트를 입력할 수 있는 클래스</span><span class="sxs-lookup"><span data-stu-id="ae0f1-175">Classes That Enable Users to Enter Text</span></span>  
 <span data-ttu-id="ae0f1-176">WPF는 사용자가 텍스트를 입력할 수 있는 세 개의 기본 컨트롤을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-176">WPF provides three primary controls that enable users to enter text.</span></span> <span data-ttu-id="ae0f1-177">각 컨트롤에는 텍스트가 다르게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-177">Each control displays the text differently.</span></span> <span data-ttu-id="ae0f1-178">다음 표에서는 이 세 가지 텍스트 관련 컨트롤과 텍스트를 표시할 때의 기능 및 컨트롤 텍스트를 포함하는 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-178">The following table lists these three text-related controls, their capabilities when they display text, and their properties that contain the control's text.</span></span>  
  
|<span data-ttu-id="ae0f1-179">제어</span><span class="sxs-lookup"><span data-stu-id="ae0f1-179">Control</span></span>|<span data-ttu-id="ae0f1-180">텍스트 표시</span><span class="sxs-lookup"><span data-stu-id="ae0f1-180">Text is displayed as</span></span>|<span data-ttu-id="ae0f1-181">콘텐츠 속성</span><span class="sxs-lookup"><span data-stu-id="ae0f1-181">Content property</span></span>|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="ae0f1-182">일반 텍스트</span><span class="sxs-lookup"><span data-stu-id="ae0f1-182">Plain text</span></span>|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="ae0f1-183">서식 있는 텍스트</span><span class="sxs-lookup"><span data-stu-id="ae0f1-183">Formatted text</span></span>|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|<span data-ttu-id="ae0f1-184">숨겨진 텍스트(문자가 마스킹됨)</span><span class="sxs-lookup"><span data-stu-id="ae0f1-184">Hidden text (characters are masked)</span></span>|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>
## <a name="classes-that-display-your-text"></a><span data-ttu-id="ae0f1-185">텍스트를 표시하는 클래스</span><span class="sxs-lookup"><span data-stu-id="ae0f1-185">Classes That Display Your Text</span></span>  
 <span data-ttu-id="ae0f1-186">여러 클래스를 사용하여 일반 텍스트나 서식이 지정된 텍스트를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-186">Several classes can be used to display plain or formatted text.</span></span> <span data-ttu-id="ae0f1-187">소량의 <xref:System.Windows.Controls.TextBlock> 텍스트를 표시하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-187">You can use <xref:System.Windows.Controls.TextBlock> to display small amounts of text.</span></span> <span data-ttu-id="ae0f1-188">많은 양의 텍스트를 표시하려면 에서 <xref:System.Windows.Controls.FlowDocumentReader> <xref:System.Windows.Controls.FlowDocumentPageViewer>또는 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 컨트롤을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-188">If you want to display large amounts of text, use the <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, or <xref:System.Windows.Controls.FlowDocumentScrollViewer> controls.</span></span>  
  
 <span data-ttu-id="ae0f1-189">의 <xref:System.Windows.Controls.TextBlock> 두 가지 <xref:System.Windows.Controls.TextBlock.Text%2A> 콘텐츠 <xref:System.Windows.Controls.TextBlock.Inlines%2A>속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-189">The <xref:System.Windows.Controls.TextBlock> has two content properties: <xref:System.Windows.Controls.TextBlock.Text%2A> and <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span></span> <span data-ttu-id="ae0f1-190">일관된 서식을 사용하는 텍스트를 표시하려는 <xref:System.Windows.Controls.TextBlock.Text%2A> 경우 속성이 가장 적합한 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-190">When you want to display text that uses consistent formatting, the <xref:System.Windows.Controls.TextBlock.Text%2A> property is often your best choice.</span></span> <span data-ttu-id="ae0f1-191">텍스트 전체에서 다른 서식을 사용하려는 <xref:System.Windows.Controls.TextBlock.Inlines%2A> 경우 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-191">If you plan to use different formatting throughout the text, use the <xref:System.Windows.Controls.TextBlock.Inlines%2A> property.</span></span> <span data-ttu-id="ae0f1-192">속성은 <xref:System.Windows.Controls.TextBlock.Inlines%2A> 텍스트의 <xref:System.Windows.Documents.Inline> 서식을 지정하는 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-192">The <xref:System.Windows.Controls.TextBlock.Inlines%2A> property is a collection of <xref:System.Windows.Documents.Inline> objects, which specify how to format text.</span></span>  
  
 <span data-ttu-id="ae0f1-193">다음 표에는 에 <xref:System.Windows.Controls.FlowDocumentReader> <xref:System.Windows.Controls.FlowDocumentPageViewer>대한 및 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 클래스에 대한 콘텐츠 속성이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-193">The following table lists the content property for <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, and <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span></span>  
  
|<span data-ttu-id="ae0f1-194">제어</span><span class="sxs-lookup"><span data-stu-id="ae0f1-194">Control</span></span>|<span data-ttu-id="ae0f1-195">콘텐츠 속성</span><span class="sxs-lookup"><span data-stu-id="ae0f1-195">Content property</span></span>|<span data-ttu-id="ae0f1-196">콘텐츠 속성 형식</span><span class="sxs-lookup"><span data-stu-id="ae0f1-196">Content property type</span></span>|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|<span data-ttu-id="ae0f1-197">문서</span><span class="sxs-lookup"><span data-stu-id="ae0f1-197">Document</span></span>|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|<span data-ttu-id="ae0f1-198">문서</span><span class="sxs-lookup"><span data-stu-id="ae0f1-198">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|<span data-ttu-id="ae0f1-199">문서</span><span class="sxs-lookup"><span data-stu-id="ae0f1-199">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
  
 <span data-ttu-id="ae0f1-200">인터페이스를 <xref:System.Windows.Documents.FlowDocument> 구현합니다. <xref:System.Windows.Documents.IDocumentPaginatorSource> 따라서 세 클래스 모두 <xref:System.Windows.Documents.FlowDocument> 콘텐츠로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-200">The <xref:System.Windows.Documents.FlowDocument> implements the <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; therefore, all three classes can take a <xref:System.Windows.Documents.FlowDocument> as content.</span></span>  
  
<a name="classes_that_format_text"></a>
## <a name="classes-that-format-your-text"></a><span data-ttu-id="ae0f1-201">텍스트 서식을 지정하는 클래스</span><span class="sxs-lookup"><span data-stu-id="ae0f1-201">Classes That Format Your Text</span></span>  
 <span data-ttu-id="ae0f1-202"><xref:System.Windows.Documents.TextElement>및 관련 클래스를 사용하면 텍스트의 서식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-202"><xref:System.Windows.Documents.TextElement> and its related classes allow you to format text.</span></span> <span data-ttu-id="ae0f1-203"><xref:System.Windows.Documents.TextElement>는 개체에 <xref:System.Windows.Controls.TextBlock> 텍스트와 <xref:System.Windows.Documents.FlowDocument> 개체의 서식을 포함하고 서식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-203"><xref:System.Windows.Documents.TextElement> objects contain and format text in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="ae0f1-204">개체의 <xref:System.Windows.Documents.TextElement> 두 가지 <xref:System.Windows.Documents.Block> 기본 <xref:System.Windows.Documents.Inline> 유형은 요소와 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-204">The two primary types of <xref:System.Windows.Documents.TextElement> objects are <xref:System.Windows.Documents.Block> elements and <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="ae0f1-205">요소는 <xref:System.Windows.Documents.Block> 단락 이나 목록 등 텍스트의 블록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-205">A <xref:System.Windows.Documents.Block> element represents a block of text, such as a paragraph or list.</span></span> <span data-ttu-id="ae0f1-206">요소는 <xref:System.Windows.Documents.Inline> 블록의 텍스트 일부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-206">An <xref:System.Windows.Documents.Inline> element represents a portion of text in a block.</span></span> <span data-ttu-id="ae0f1-207">많은 <xref:System.Windows.Documents.Inline> 클래스에서 적용되는 텍스트에 대한 서식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-207">Many <xref:System.Windows.Documents.Inline> classes specify formatting for the text to which they are applied.</span></span> <span data-ttu-id="ae0f1-208">각각에는 <xref:System.Windows.Documents.TextElement> 고유한 콘텐츠 모델이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-208">Each <xref:System.Windows.Documents.TextElement> has its own content model.</span></span> <span data-ttu-id="ae0f1-209">자세한 내용은 [TextElement 콘텐츠 모델 개요](../advanced/textelement-content-model-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae0f1-209">For more information, see the [TextElement Content Model Overview](../advanced/textelement-content-model-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae0f1-210">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae0f1-210">See also</span></span>

- [<span data-ttu-id="ae0f1-211">고급</span><span class="sxs-lookup"><span data-stu-id="ae0f1-211">Advanced</span></span>](../advanced/index.md)
