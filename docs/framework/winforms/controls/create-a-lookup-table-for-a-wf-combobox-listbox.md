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
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 조회 테이블 만들기
경우에 따라 Windows Form에서는 친숙한 형식으로 데이터를 표시하지만 프로그램에서는 더 의미 있는 형식으로 데이터를 저장하는 데 유용합니다. 예를 들어 음식 주문 양식의 목록 상자에는 메뉴 항목이 이름별로 표시될 수 있습니다. 그러나 주문을 기록하는 데이터 테이블에는 음식을 나타내는 고유 ID 번호가 포함됩니다. 다음 표에서는 음식에 대한 주문 양식 데이터를 저장 및 표시하는 방법의 예를 보여 줍니다.  
  
### <a name="orderdetailstable"></a>OrderDetailsTable  
  
|OrderID|ItemID|Quantity|  
|-------------|------------|--------------|  
|4085|12|1|  
|4086|13|3|  
  
### <a name="itemtable"></a>ItemTable  
  
|ID|이름|  
|--------|----------|  
|12|Potato|  
|13|Chicken|  
  
 이 시나리오에서 **OrderDetailsTable**테이블 하나는 표시 하 고 저장 하는 것과 관련 된 실제 정보를 저장 합니다. 하지만 공간을 절약하기 위해 매우 복잡한 방식으로 작업이 수행됩니다. 다른 테이블 ( **ItemTable**)에는 주문 이름과 해당 하는 ID 번호에 대 한 모양 관련 정보만 포함 되며 실제 음식 주문에 대해서는 아무것도 포함 되지 않습니다.  
  
 **ItemTable** 는 세 가지 속성을 통해 <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>또는 <xref:System.Windows.Forms.CheckedListBox> 제어에 연결 됩니다. `DataSource` 속성은이 테이블의 이름을 포함 합니다. `DisplayMember` 속성에는 컨트롤에 표시할 해당 테이블의 데이터 열 (음식 이름)이 포함 되어 있습니다. `ValueMember` 속성은 저장 된 정보 (ID 번호)가 포함 된 해당 테이블의 데이터 열을 포함 합니다.  
  
 **OrderDetailsTable** 는 <xref:System.Windows.Forms.Control.DataBindings%2A> 속성을 통해 액세스 되는 바인딩 컬렉션에 의해 컨트롤에 연결 됩니다. 컬렉션에 바인딩 개체를 추가 하는 경우 데이터 원본의 특정 데이터 멤버 (ID 번호 열)에 컨트롤 속성을 연결 합니다 ( **OrderDetailsTable**). 컨트롤에서 항목을 선택하면 양식 입력이 이 테이블에 저장됩니다.  
  
### <a name="to-create-a-lookup-table"></a>조회 테이블을 만들려면  
  
1. 양식에 <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox> 또는 <xref:System.Windows.Forms.CheckedListBox> 컨트롤을 추가합니다.  
  
2. 데이터 소스에 연결합니다.  
  
3. 두 테이블 간에 데이터 관계를 설정합니다. [DataRelation 개체 소개를](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120))참조 하세요.  
  
4. 다음 속성을 설정합니다. 코드 또는 디자이너에서 설정할 수 있습니다.  
  
    |속성|설정|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|어떤 ID 번호가 어떤 항목에 해당하는지에 대한 정보를 포함하는 테이블입니다. 이전 시나리오에서는 `ItemTable`입니다.|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|컨트롤에 표시하려는 데이터 소스 테이블의 열입니다. 이전 시나리오에서이는 `"Name"` (코드에서 설정 하기 위해 따옴표 사용)입니다.|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|저장된 정보를 포함하는 데이터 소스 테이블의 열입니다. 이전 시나리오에서이는 `"ID"` (코드에서 설정 하기 위해 따옴표 사용)입니다.|  
  
5. 프로시저에서 <xref:System.Windows.Forms.ControlBindingsCollection> 클래스의 <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> 메서드를 호출하여 양식 입력을 기록하는 테이블에 컨트롤의 <xref:System.Windows.Forms.ListControl.SelectedValue%2A> 속성을 바인딩합니다. 또한 **속성** 창에서 컨트롤의 <xref:System.Windows.Forms.Control.DataBindings%2A> 속성에 액세스 하 여 코드 대신 디자이너에서이 작업을 수행할 수 있습니다. 이전 시나리오에서는이 `OrderDetailsTable`되 고 열은 `"ItemID"`됩니다.  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a>참조

- [데이터 바인딩 및 Windows Forms](../data-binding-and-windows-forms.md)
- [ListBox 컨트롤 개요](listbox-control-overview-windows-forms.md)
- [ComboBox 컨트롤 개요](combobox-control-overview-windows-forms.md)
- [CheckedListBox 컨트롤 개요](checkedlistbox-control-overview-windows-forms.md)
- [옵션 목록 표시에 사용된 Windows Forms 컨트롤](windows-forms-controls-used-to-list-options.md)
