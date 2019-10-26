---
title: L2DBForm.xaml 소스 코드
ms.date: 10/22/2019
ms.topic: sample
ms.openlocfilehash: 290b00e136f0c49e1b27d4fa1bca7321eebe936e
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921229"
---
# <a name="l2dbformxaml-source-code"></a><span data-ttu-id="74a59-102">L2DBForm.xaml 소스 코드</span><span class="sxs-lookup"><span data-stu-id="74a59-102">L2DBForm.xaml source code</span></span>

<span data-ttu-id="74a59-103">이 페이지에는 [LINQ to XML 예제를 사용 하는 WPF 데이터 바인딩의](linq-to-xml-data-binding-sample.md)XAML 소스 파일에 대 한 설명이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-103">This page contains and describes the XAML source file for the [WPF data binding using LINQ to XML example](linq-to-xml-data-binding-sample.md).</span></span>

## <a name="overall-ui-structure"></a><span data-ttu-id="74a59-104">전체적인 UI 구조</span><span class="sxs-lookup"><span data-stu-id="74a59-104">Overall UI structure</span></span>

<span data-ttu-id="74a59-105">WPF 프로젝트에 일반적으로 사용 되는 것 처럼이 파일에는 `LinqToXmlDataBinding` 네임 스페이스의 `L2XDBFrom` 파생 클래스와 연결 된 <xref:System.Windows.Window> XML 요소인 하나의 부모 요소가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-105">As is typical for a WPF project, this file contains one parent element, a <xref:System.Windows.Window> XML element that's associated with the derived class `L2XDBFrom` in the `LinqToXmlDataBinding` namespace.</span></span>

<span data-ttu-id="74a59-106">클라이언트 영역은 연한 파란색 배경이 제공 되는 <xref:System.Windows.Controls.StackPanel>에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-106">The client area is contained within a <xref:System.Windows.Controls.StackPanel> that's given a light blue background.</span></span> <span data-ttu-id="74a59-107">이 패널에는 <xref:System.Windows.Controls.DockPanel> 표시줄로 구분된 <xref:System.Windows.Controls.Separator> UI 섹션이 4개 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-107">This panel contains four <xref:System.Windows.Controls.DockPanel> UI sections separated by <xref:System.Windows.Controls.Separator> bars.</span></span> <span data-ttu-id="74a59-108">이러한 섹션의 용도는 [여기](linq-to-xml-data-binding-sample.md#overview)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-108">The purpose of these sections is described [here](linq-to-xml-data-binding-sample.md#overview).</span></span>

<span data-ttu-id="74a59-109">각 섹션에는 해당 섹션을 식별하는 레이블이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-109">Each section contains a label that identifies it.</span></span> <span data-ttu-id="74a59-110">처음 두 섹션에서 이 레이블은 <xref:System.Windows.FrameworkElement.LayoutTransform%2A>을 사용하여 90도 회전됩니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-110">In the first two sections, this label is rotated 90 degrees through the use of a <xref:System.Windows.FrameworkElement.LayoutTransform%2A>.</span></span> <span data-ttu-id="74a59-111">섹션의 나머지 부분에는 해당 섹션의 목적에 적합 한 텍스트 블록, 텍스트 상자, 단추 등의 UI 요소가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-111">The rest of the section contains UI elements appropriate to the purpose of that section, for example, text blocks, text boxes, and buttons.</span></span> <span data-ttu-id="74a59-112">때때로 자식 <xref:System.Windows.Controls.StackPanel> 이 이러한 자식 컨트롤을 정렬하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-112">Sometimes a child <xref:System.Windows.Controls.StackPanel> is used to align these child controls.</span></span>

## <a name="window-resource-section"></a><span data-ttu-id="74a59-113">창 리소스 섹션</span><span class="sxs-lookup"><span data-stu-id="74a59-113">Window resource section</span></span>

<span data-ttu-id="74a59-114">9번째 줄의 여는 `<Window.Resources>` 태그는 창 리소스 섹션의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-114">The opening `<Window.Resources>` tag on line 9 indicates the start of the window resource section.</span></span> <span data-ttu-id="74a59-115">창 리소스 섹션은 35번째 줄의 닫는 태그에서 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-115">It ends with the closing tag on line 35.</span></span>

<span data-ttu-id="74a59-116">11-25번째 줄에 있는 `<ObjectDataProvider>` 태그는 <xref:System.Windows.Data.ObjectDataProvider>를 소스로 사용하는 `LoadedBooks`라는 <xref:System.Xml.Linq.XElement> 를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-116">The `<ObjectDataProvider>` tag, which spans lines 11 through 25, declares a <xref:System.Windows.Data.ObjectDataProvider>, named `LoadedBooks`, that uses an <xref:System.Xml.Linq.XElement> as the source.</span></span> <span data-ttu-id="74a59-117"><xref:System.Xml.Linq.XElement>는 포함된 XML 문서(`CDATA` 요소)의 구문을 분석하여 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-117">The <xref:System.Xml.Linq.XElement> is initialized by parsing an embedded XML document (a `CDATA` element).</span></span> <span data-ttu-id="74a59-118">포함 된 XML 문서를 선언 하는 경우와 구문 분석 되는 경우에도 공백이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-118">Notice that white space is preserved when declaring the embedded XML document and also when it's parsed.</span></span> <span data-ttu-id="74a59-119">공백은 원시 XML을 표시하는 데 사용되는 <xref:System.Windows.Controls.TextBlock> 컨트롤에 유지되기 때문에 특별한 XML 서식 지정 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-119">White space is preserved because the <xref:System.Windows.Controls.TextBlock> control, which is used to display the raw XML, has no special XML formatting capabilities.</span></span>

<span data-ttu-id="74a59-120">마지막으로 <xref:System.Windows.DataTemplate> 이라는 `BookTemplate` 이 28-34번째 줄에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-120">Lastly, a <xref:System.Windows.DataTemplate> named `BookTemplate` is defined on lines 28 through 34.</span></span> <span data-ttu-id="74a59-121">이 템플릿은 **Book List** UI 섹션에 항목을 표시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-121">This template is used to display the entries in the **Book List** UI section.</span></span> <span data-ttu-id="74a59-122">이 템플릿에서는 데이터 바인딩과 LINQ to XML 동적 속성을 사용하여 다음 할당을 통해 책 ID와 책 이름을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-122">It uses data binding and LINQ to XML dynamic properties to retrieve the book ID and book name through the following assignments:</span></span>

```xaml
Text="{Binding Path=Attribute[id].Value}"Text="{Binding Path=Value}"
```

## <a name="data-binding-code"></a><span data-ttu-id="74a59-123">데이터 바인딩 코드</span><span class="sxs-lookup"><span data-stu-id="74a59-123">Data binding code</span></span>

<span data-ttu-id="74a59-124"><xref:System.Windows.DataTemplate> 요소 외에도 데이터 바인딩이 이 파일의 여러 위치에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-124">In addition to the <xref:System.Windows.DataTemplate> element, data binding is used in a number of other places in this file.</span></span>

<span data-ttu-id="74a59-125">38번째 줄의 여는 `<StackPanel>` 태그에서 이 패널의 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성은 `LoadedBooks` 데이터 공급자로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-125">In the opening `<StackPanel>` tag on line 38, the <xref:System.Windows.FrameworkElement.DataContext%2A> property of this panel is set to the `LoadedBooks` data provider.</span></span>

```xaml
DataContext="{Binding Source={StaticResource LoadedBooks}}
```

<span data-ttu-id="74a59-126">데이터 컨텍스트를 설정하면(46번째 줄) `tbRawXml`이라는 <xref:System.Windows.Controls.TextBlock>이 이 데이터 공급자의 `Xml` 속성에 바인딩하여 원시 XML을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-126">Setting the data context makes it possible (on line 46) for the <xref:System.Windows.Controls.TextBlock> named `tbRawXml` to display the raw XML by binding to this data provider's `Xml` property:</span></span>

```xaml
Text="{Binding Path=Xml}"
```

<span data-ttu-id="74a59-127">58-62번째 줄의 <xref:System.Windows.Controls.ListBox> Book List **UI 섹션에 있는** 는 표시 항목에 대한 템플릿을 창 리소스 섹션에 정의된 `BookTemplate` 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-127">The <xref:System.Windows.Controls.ListBox> in the **Book List** UI section, on lines 58 through 62, sets the template for its display items to the `BookTemplate` defined in the window resource section:</span></span>

```xaml
ItemTemplate ="{StaticResource BookTemplate}"
```

<span data-ttu-id="74a59-128">그런 다음 59-62번째 줄에서 책의 실제 값이 이 목록 상자에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-128">Then, on lines 59 through 62, the actual values of the books are bound to this list box:</span></span>

```xaml
<ListBox.ItemsSource>
    <Binding Path="Elements[{http://www.mybooks.com}book]"/>
</ListBox.ItemsSource>
```

<span data-ttu-id="74a59-129">세 번째 UI 섹션인 **Edit Selected Book**은 먼저 부모 <xref:System.Windows.FrameworkElement.DataContext%2A> 의 <xref:System.Windows.Controls.StackPanel> 를 **Book List** UI 섹션(82번째 줄)에서 현재 선택된 항목에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-129">The third UI section, **Edit Selected Book**, first binds the <xref:System.Windows.FrameworkElement.DataContext%2A> of the parent <xref:System.Windows.Controls.StackPanel> to the currently selected item in from the **Book List** UI section (line 82):</span></span>

```xaml
DataContext="{Binding ElementName=lbBooks, Path=SelectedItem}"
```

<span data-ttu-id="74a59-130">그런 다음, 양방향 데이터 바인딩을 사용하여 책 요소의 현재 값이 이 패널의 두 텍스트 상자에 표시되고 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-130">It then uses two-way data binding, so that the current values of the book elements are displayed to, and updated from, the two text boxes in this panel.</span></span> <span data-ttu-id="74a59-131">동적 속성에 대한 데이터 바인딩은 `BookTemplate` 데이터 템플릿에서 사용되는 데이터 바인딩과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-131">Data binding to dynamic properties is similar to the data binding used in the `BookTemplate` data template:</span></span>

```xaml
Text="{Binding Path=Attribute[id].Value}"...Text="{Binding Path=Value}"
```

<span data-ttu-id="74a59-132">최신 UI 섹션인 **Add New Book**에서는 XAML 코드에 데이터 바인딩을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-132">The last UI section, **Add New Book**, doesn't use data binding in its XAML code.</span></span> <span data-ttu-id="74a59-133">대신, 데이터 바인딩은 *L2DBForm.xaml.cs* 파일의 이벤트 처리 코드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-133">Instead, data binding is in its event handling code in the file *L2DBForm.xaml.cs*.</span></span>

## <a name="example"></a><span data-ttu-id="74a59-134">예제</span><span class="sxs-lookup"><span data-stu-id="74a59-134">Example</span></span>

### <a name="description"></a><span data-ttu-id="74a59-135">설명</span><span class="sxs-lookup"><span data-stu-id="74a59-135">Description</span></span>

> [!NOTE]
> <span data-ttu-id="74a59-136">줄 번호를 추적하기 쉽도록 아래의 코드를 Visual Studio의 C# 소스 코드 편집기와 같은 코드 편집기에 복사하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="74a59-136">We recommend that you copy the following code below into a code editor, such as the C# source code editor in Visual Studio, so that line numbers will be easier to track.</span></span>

### <a name="code"></a><span data-ttu-id="74a59-137">코드</span><span class="sxs-lookup"><span data-stu-id="74a59-137">Code</span></span>

```xml
<Window x:Class="LinqToXmlDataBinding.L2XDBForm"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:system="clr-namespace:System;assembly=mscorlib"
    xmlns:xlinq="clr-namespace:System.Xml.Linq;assembly=System.Xml.Linq"
    xmlns:local="clr-namespace:LinqToXmlDataBinding"
    Title="WPF Data Binding using LINQ-to-XML" Height="665" Width="500" ResizeMode="NoResize">

    <Window.Resources>
        <!-- Books provider and inline data -->
        <ObjectDataProvider x:Key="LoadedBooks" ObjectType="{x:Type xlinq:XElement}" MethodName="Parse">
            <ObjectDataProvider.MethodParameters>
                <system:String xml:space="preserve">
<![CDATA[
<books xmlns="http://www.mybooks.com">
  <book id="0">book zero</book>
  <book id="1">book one</book>
  <book id="2">book two</book>
  <book id="3">book three</book>
</books>
]]>
                </system:String>
                <xlinq:LoadOptions>PreserveWhitespace</xlinq:LoadOptions>
            </ObjectDataProvider.MethodParameters>
        </ObjectDataProvider>

        <!-- Template for use in Books List listbox. -->
        <DataTemplate x:Key="BookTemplate">
            <StackPanel Orientation="Horizontal">
                <TextBlock Margin="3" Text="{Binding Path=Attribute[id].Value}"/>
                <TextBlock Margin="3" Text="-"/>
                <TextBlock Margin="3" Text="{Binding Path=Value}"/>
            </StackPanel>
        </DataTemplate>
    </Window.Resources>

    <!-- Main visual content container -->
    <StackPanel Background="lightblue" DataContext="{Binding Source={StaticResource LoadedBooks}}">
        <!-- Raw XML display section -->
        <DockPanel Margin="5">
            <Label  Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" FontWeight="Bold">XML
            <Label.LayoutTransform>
                <RotateTransform Angle="90"/>
            </Label.LayoutTransform>
            </Label>
            <TextBlock Name="tbRawXml" Height="200" Background="LightGray" Text="{Binding Path=Xml}" TextTrimming="CharacterEllipsis" />
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- List box to display all books section -->
        <DockPanel Margin="5">
            <Label  Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" FontWeight="Bold">Book List
                <Label.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </Label.LayoutTransform>
            </Label>
            <ListBox Name="lbBooks" Height="200" Width="415" ItemTemplate ="{StaticResource BookTemplate}">
                <ListBox.ItemsSource>
                    <Binding Path="Elements[{http://www.mybooks.com}book]"/>
                </ListBox.ItemsSource>
            </ListBox>
            <Button Margin="5" DockPanel.Dock="Right" Height="30" Width ="130" Content="Remove Selected Book" Click="OnRemoveBook">
            <Button.LayoutTransform>
                <RotateTransform Angle="90"/>
            </Button.LayoutTransform>
            </Button>
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- Edit current selection section -->
        <DockPanel Margin="5">
            <TextBlock Margin="5" Height="30" Width="65" DockPanel.Dock="Right" Background="LightGray" TextWrapping="Wrap" TextAlignment="Center">
                    Changes are live!
                <TextBlock.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </TextBlock.LayoutTransform>
            </TextBlock>
            <StackPanel>
                <Label Width="450" Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Left" FontWeight="Bold">Edit Selected Book</Label>
                <StackPanel Margin="1" DataContext="{Binding ElementName=lbBooks, Path=SelectedItem}">
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">ID:</Label>
                        <TextBox Name="editAttributeTextBox" Width="410" Text="{Binding Path=Attribute[id].Value}">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Edit the selected book ID and see it changed.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">Value:</Label>
                        <TextBox Name="editValueTextBox" Width="410" Text="{Binding Path=Value}" Height="25">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Edit the selected book Value and see it changed.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                </StackPanel>
            </StackPanel>
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- Add new book section -->
        <DockPanel Margin="5">
            <Button Margin="5" Height="30" DockPanel.Dock="Right" Click ="OnAddBook">Add Book
                <Button.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </Button.LayoutTransform>
            </Button>
            <StackPanel>
                <Label Width="450" Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Left" FontWeight="Bold">Add New Book</Label>
                <StackPanel Margin="1">
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">ID:</Label>
                        <TextBox Name="tbAddID" Width="410">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Enter a book ID and Value pair, then click Add Book.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">Value:</Label>
                        <TextBox Name="tbAddValue" Width="410" Height="25">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="UltraBold" TextAlignment="Center">
                                    <Label>Enter a book ID and Value pair, then click Add Book.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                </StackPanel>
            </StackPanel>
        </DockPanel>
    </StackPanel>
</Window>
```

### <a name="comments"></a><span data-ttu-id="74a59-138">주석</span><span class="sxs-lookup"><span data-stu-id="74a59-138">Comments</span></span>

<span data-ttu-id="74a59-139">WPF UI 요소와 연결된 이벤트 처리기의 C# 소스 코드는 [L2DBForm.xaml.cs 소스 코드](l2dbform-xaml-cs-source-code.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74a59-139">For the C# source code for the event handlers associated with the WPF UI elements, see [L2DBForm.xaml.cs source code](l2dbform-xaml-cs-source-code.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="74a59-140">참조</span><span class="sxs-lookup"><span data-stu-id="74a59-140">See also</span></span>

- [<span data-ttu-id="74a59-141">연습: LinqToXmlDataBinding 예제</span><span class="sxs-lookup"><span data-stu-id="74a59-141">Walkthrough: LinqToXmlDataBinding example</span></span>](linq-to-xml-data-binding-sample.md)
- [<span data-ttu-id="74a59-142">L2DBForm.xaml.cs 소스 코드</span><span class="sxs-lookup"><span data-stu-id="74a59-142">L2DBForm.xaml.cs source code</span></span>](l2dbform-xaml-cs-source-code.md)
