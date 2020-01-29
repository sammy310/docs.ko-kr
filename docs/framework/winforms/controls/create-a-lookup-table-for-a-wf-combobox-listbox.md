---
title: ComboBox, ListBox 또는 CheckedListBox 컨트롤에 대 한 조회 테이블 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CheckedListBox control [Windows Forms], creating lookup tables
- lookup tables
- list boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], lookup tables
- ComboBox control [Windows Forms], lookup table
- lookup tables [Windows Forms], creating for controls
- combo boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], creating lookup tables
ms.assetid: 4ce35f12-1f4e-4317-92d1-af8686a8cfaa
ms.openlocfilehash: 4bbbc66a56c7ce269c2dabd593db88f96907d755
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737374"
---
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="dfb6b-102">방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 조회 테이블 만들기</span><span class="sxs-lookup"><span data-stu-id="dfb6b-102">How to: Create a Lookup Table for a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="dfb6b-103">경우에 따라 Windows Form에서는 친숙한 형식으로 데이터를 표시하지만 프로그램에서는 더 의미 있는 형식으로 데이터를 저장하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-103">Sometimes it is useful to display data in a user-friendly format on a Windows Form, but store the data in a format that is more meaningful to your program.</span></span> <span data-ttu-id="dfb6b-104">예를 들어 음식 주문 양식의 목록 상자에는 메뉴 항목이 이름별로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-104">For example, an order form for food might display the menu items by name in a list box.</span></span> <span data-ttu-id="dfb6b-105">그러나 주문을 기록하는 데이터 테이블에는 음식을 나타내는 고유 ID 번호가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-105">However, the data table recording the order would contain the unique ID numbers representing the food.</span></span> <span data-ttu-id="dfb6b-106">다음 표에서는 음식에 대한 주문 양식 데이터를 저장 및 표시하는 방법의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-106">The following tables show an example of how to store and display order-form data for food.</span></span>  
  
### <a name="orderdetailstable"></a><span data-ttu-id="dfb6b-107">OrderDetailsTable</span><span class="sxs-lookup"><span data-stu-id="dfb6b-107">OrderDetailsTable</span></span>  
  
|<span data-ttu-id="dfb6b-108">OrderID</span><span class="sxs-lookup"><span data-stu-id="dfb6b-108">OrderID</span></span>|<span data-ttu-id="dfb6b-109">ItemID</span><span class="sxs-lookup"><span data-stu-id="dfb6b-109">ItemID</span></span>|<span data-ttu-id="dfb6b-110">Quantity</span><span class="sxs-lookup"><span data-stu-id="dfb6b-110">Quantity</span></span>|  
|-------------|------------|--------------|  
|<span data-ttu-id="dfb6b-111">4085</span><span class="sxs-lookup"><span data-stu-id="dfb6b-111">4085</span></span>|<span data-ttu-id="dfb6b-112">12</span><span class="sxs-lookup"><span data-stu-id="dfb6b-112">12</span></span>|<span data-ttu-id="dfb6b-113">1</span><span class="sxs-lookup"><span data-stu-id="dfb6b-113">1</span></span>|  
|<span data-ttu-id="dfb6b-114">4086</span><span class="sxs-lookup"><span data-stu-id="dfb6b-114">4086</span></span>|<span data-ttu-id="dfb6b-115">13</span><span class="sxs-lookup"><span data-stu-id="dfb6b-115">13</span></span>|<span data-ttu-id="dfb6b-116">3</span><span class="sxs-lookup"><span data-stu-id="dfb6b-116">3</span></span>|  
  
### <a name="itemtable"></a><span data-ttu-id="dfb6b-117">ItemTable</span><span class="sxs-lookup"><span data-stu-id="dfb6b-117">ItemTable</span></span>  
  
|<span data-ttu-id="dfb6b-118">ID</span><span class="sxs-lookup"><span data-stu-id="dfb6b-118">ID</span></span>|<span data-ttu-id="dfb6b-119">이름</span><span class="sxs-lookup"><span data-stu-id="dfb6b-119">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="dfb6b-120">12</span><span class="sxs-lookup"><span data-stu-id="dfb6b-120">12</span></span>|<span data-ttu-id="dfb6b-121">Potato</span><span class="sxs-lookup"><span data-stu-id="dfb6b-121">Potato</span></span>|  
|<span data-ttu-id="dfb6b-122">13</span><span class="sxs-lookup"><span data-stu-id="dfb6b-122">13</span></span>|<span data-ttu-id="dfb6b-123">Chicken</span><span class="sxs-lookup"><span data-stu-id="dfb6b-123">Chicken</span></span>|  
  
 <span data-ttu-id="dfb6b-124">이 시나리오에서 **OrderDetailsTable**테이블 하나는 표시 하 고 저장 하는 것과 관련 된 실제 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-124">In this scenario, one table, **OrderDetailsTable**, stores the actual information you are concerned with displaying and saving.</span></span> <span data-ttu-id="dfb6b-125">하지만 공간을 절약하기 위해 매우 복잡한 방식으로 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-125">But to save space, it does so in a fairly cryptic fashion.</span></span> <span data-ttu-id="dfb6b-126">다른 테이블 ( **ItemTable**)에는 주문 이름과 해당 하는 ID 번호에 대 한 모양 관련 정보만 포함 되며 실제 음식 주문에 대해서는 아무것도 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-126">The other table, **ItemTable**, contains only appearance-related information about which ID number is equivalent to which food name, and nothing about the actual food orders.</span></span>  
  
 <span data-ttu-id="dfb6b-127">**ItemTable** 는 세 가지 속성을 통해 <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>또는 <xref:System.Windows.Forms.CheckedListBox> 제어에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-127">The **ItemTable** is connected to the <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control through three properties.</span></span> <span data-ttu-id="dfb6b-128">`DataSource` 속성은이 테이블의 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-128">The `DataSource` property contains the name of this table.</span></span> <span data-ttu-id="dfb6b-129">`DisplayMember` 속성에는 컨트롤에 표시할 해당 테이블의 데이터 열 (음식 이름)이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-129">The `DisplayMember` property contains the data column of that table that you want to display in the control (the food name).</span></span> <span data-ttu-id="dfb6b-130">`ValueMember` 속성은 저장 된 정보 (ID 번호)가 포함 된 해당 테이블의 데이터 열을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-130">The `ValueMember` property contains the data column of that table with the stored information (the ID number).</span></span>  
  
 <span data-ttu-id="dfb6b-131">**OrderDetailsTable** 는 <xref:System.Windows.Forms.Control.DataBindings%2A> 속성을 통해 액세스 되는 바인딩 컬렉션에 의해 컨트롤에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-131">The **OrderDetailsTable** is connected to the control by its bindings collection, accessed through the <xref:System.Windows.Forms.Control.DataBindings%2A> property.</span></span> <span data-ttu-id="dfb6b-132">컬렉션에 바인딩 개체를 추가 하는 경우 데이터 원본의 특정 데이터 멤버 (ID 번호 열)에 컨트롤 속성을 연결 합니다 ( **OrderDetailsTable**).</span><span class="sxs-lookup"><span data-stu-id="dfb6b-132">When you add a binding object to the collection, you connect a control property to a specific data member (the column of ID numbers) in a data source (the **OrderDetailsTable**).</span></span> <span data-ttu-id="dfb6b-133">컨트롤에서 항목을 선택하면 양식 입력이 이 테이블에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-133">When a selection is made in the control, this table is where the form input is saved.</span></span>  
  
### <a name="to-create-a-lookup-table"></a><span data-ttu-id="dfb6b-134">조회 테이블을 만들려면</span><span class="sxs-lookup"><span data-stu-id="dfb6b-134">To create a lookup table</span></span>  
  
1. <span data-ttu-id="dfb6b-135">양식에 <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox> 또는 <xref:System.Windows.Forms.CheckedListBox> 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-135">Add a <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control to the form.</span></span>  
  
2. <span data-ttu-id="dfb6b-136">데이터 소스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-136">Connect to your data source.</span></span>  
  
3. <span data-ttu-id="dfb6b-137">두 테이블 간에 데이터 관계를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-137">Establish a data relation between the two tables.</span></span> <span data-ttu-id="dfb6b-138">[DataRelation 개체 소개를](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120))참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-138">See [Introduction to DataRelation Objects](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120)).</span></span>  
  
4. <span data-ttu-id="dfb6b-139">다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-139">Set the following properties.</span></span> <span data-ttu-id="dfb6b-140">코드 또는 디자이너에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-140">They can be set in code or in the designer.</span></span>  
  
    |<span data-ttu-id="dfb6b-141">속성</span><span class="sxs-lookup"><span data-stu-id="dfb6b-141">Property</span></span>|<span data-ttu-id="dfb6b-142">설정</span><span class="sxs-lookup"><span data-stu-id="dfb6b-142">Setting</span></span>|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|<span data-ttu-id="dfb6b-143">어떤 ID 번호가 어떤 항목에 해당하는지에 대한 정보를 포함하는 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-143">The table that contains information about which ID number is equivalent to which item.</span></span> <span data-ttu-id="dfb6b-144">이전 시나리오에서는 `ItemTable`입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-144">In the previous scenario, this is `ItemTable`.</span></span>|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|<span data-ttu-id="dfb6b-145">컨트롤에 표시하려는 데이터 소스 테이블의 열입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-145">The column of the data source table that you want to display in the control.</span></span> <span data-ttu-id="dfb6b-146">이전 시나리오에서이는 `"Name"` (코드에서 설정 하기 위해 따옴표 사용)입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-146">In the previous scenario, this is `"Name"` (to set in code, use quotation marks).</span></span>|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|<span data-ttu-id="dfb6b-147">저장된 정보를 포함하는 데이터 소스 테이블의 열입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-147">The column of the data source table that contains the stored information.</span></span> <span data-ttu-id="dfb6b-148">이전 시나리오에서이는 `"ID"` (코드에서 설정 하기 위해 따옴표 사용)입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-148">In the previous scenario, this is `"ID"` (to set in code, use quotation marks).</span></span>|  
  
5. <span data-ttu-id="dfb6b-149">프로시저에서 <xref:System.Windows.Forms.ControlBindingsCollection> 클래스의 <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> 메서드를 호출하여 양식 입력을 기록하는 테이블에 컨트롤의 <xref:System.Windows.Forms.ListControl.SelectedValue%2A> 속성을 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-149">In a procedure, call the <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> method of the <xref:System.Windows.Forms.ControlBindingsCollection> class to bind the control's <xref:System.Windows.Forms.ListControl.SelectedValue%2A> property to the table recording the form input.</span></span> <span data-ttu-id="dfb6b-150">또한 **속성** 창에서 컨트롤의 <xref:System.Windows.Forms.Control.DataBindings%2A> 속성에 액세스 하 여 코드 대신 디자이너에서이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-150">You can also do this in the Designer instead of in code, by accessing the control's <xref:System.Windows.Forms.Control.DataBindings%2A> property in the **Properties** window.</span></span> <span data-ttu-id="dfb6b-151">이전 시나리오에서는이 `OrderDetailsTable`되 고 열은 `"ItemID"`됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb6b-151">In the previous scenario, this is `OrderDetailsTable`, and the column is `"ItemID"`.</span></span>  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="dfb6b-152">참조</span><span class="sxs-lookup"><span data-stu-id="dfb6b-152">See also</span></span>

- [<span data-ttu-id="dfb6b-153">데이터 바인딩 및 Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dfb6b-153">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="dfb6b-154">ListBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="dfb6b-154">ListBox Control Overview</span></span>](listbox-control-overview-windows-forms.md)
- [<span data-ttu-id="dfb6b-155">ComboBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="dfb6b-155">ComboBox Control Overview</span></span>](combobox-control-overview-windows-forms.md)
- [<span data-ttu-id="dfb6b-156">CheckedListBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="dfb6b-156">CheckedListBox Control Overview</span></span>](checkedlistbox-control-overview-windows-forms.md)
- [<span data-ttu-id="dfb6b-157">옵션 목록 표시에 사용된 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="dfb6b-157">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
