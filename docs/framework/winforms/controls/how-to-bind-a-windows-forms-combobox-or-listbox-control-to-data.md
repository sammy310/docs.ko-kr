---
title: '방법: 데이터에 Windows Forms ComboBox 또는 ListBox 컨트롤 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], binding to controls
- list boxes [Windows Forms], data binding
- ComboBox control [Windows Forms], data binding
- data binding [Windows Forms], combo boxes
- ListBox control [Windows Forms], data binding
- combo boxes [Windows Forms], data binding
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- data-bound controls [Windows Forms], Windows Forms
ms.assetid: dfd7f081-8bea-4a41-86a3-86a1934828ef
ms.openlocfilehash: f361526c44f8fbb9ab282fe15ae109b67e8f01dd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922750"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="6d5a2-102">방법: 데이터에 Windows Forms ComboBox 또는 ListBox 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="6d5a2-102">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="6d5a2-103"><xref:System.Windows.Forms.ComboBox> 및<xref:System.Windows.Forms.ListBox> 를 데이터에 바인딩하여 데이터베이스의 데이터 검색, 새 데이터 입력, 기존 데이터 편집 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5a2-103">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="6d5a2-104">ComboBox 또는 ListBox 컨트롤을 바인딩하려면</span><span class="sxs-lookup"><span data-stu-id="6d5a2-104">To bind a ComboBox or ListBox control</span></span>  
  
1. <span data-ttu-id="6d5a2-105">`DataSource` 속성을 데이터 원본 개체로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5a2-105">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="6d5a2-106">가능한 데이터 원본에는 <xref:System.Windows.Forms.BindingSource> 데이터에 바인딩된 데이터, 데이터 테이블, 데이터 뷰, 데이터 집합, 데이터 뷰 관리자, 배열 또는 인터페이스를 <xref:System.Collections.IList> 구현 하는 클래스가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d5a2-106">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="6d5a2-107">자세한 내용은 [Windows Forms에서 지 원하는 데이터 원본](../data-sources-supported-by-windows-forms.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d5a2-107">For more information, see [Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="6d5a2-108">테이블에 바인딩하는 경우 `DisplayMember` 속성을 데이터 원본의 열 이름으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5a2-108">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="6d5a2-109">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="6d5a2-109">\- or -</span></span>  
  
     <span data-ttu-id="6d5a2-110">에 <xref:System.Collections.IList>바인딩하는 경우 표시 멤버를 목록에 있는 형식의 public 속성으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5a2-110">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
    ```vb  
    Private Sub BindComboBox()  
      ComboBox1.DataSource = DataSet1.Tables("Suppliers")  
      ComboBox1.DisplayMember = "ProductName"  
    End Sub  
    ```  
  
    ```csharp  
    private void BindComboBox()  
    {  
      comboBox1.DataSource = dataSet1.Tables["Suppliers"];  
      comboBox1.DisplayMember = "ProductName";  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="6d5a2-111"><xref:System.ComponentModel.IBindingList> 인터페이스를 구현 하지 않는 데이터 소스 (예: <xref:System.Collections.ArrayList>)에 바인딩되는 경우 데이터 소스가 업데이트 될 때 바인딩된 컨트롤의 데이터가 업데이트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5a2-111">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="6d5a2-112">예를 들어에 바인딩된 <xref:System.Collections.ArrayList> 콤보 상자가 있고 데이터를에 추가 <xref:System.Collections.ArrayList>하는 경우 이러한 새 항목은 콤보 상자에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5a2-112">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="6d5a2-113">그러나 컨트롤이 바인딩되는 <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> <xref:System.Windows.Forms.BindingContext> 클래스의 인스턴스에서 및 <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> 메서드를 호출 하 여 콤보 상자를 강제로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5a2-113">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d5a2-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="6d5a2-114">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="6d5a2-115">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="6d5a2-115">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="6d5a2-116">데이터 바인딩 및 Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6d5a2-116">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="6d5a2-117">옵션 목록 표시에 사용된 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6d5a2-117">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
