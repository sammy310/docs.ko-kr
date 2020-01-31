---
title: DataGrid 컨트롤에서 열 삭제 또는 숨기기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], deleting columns
- DataGrid control [Windows Forms], deleting columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
- columns [Windows Forms], deleting in data grids
- DataGrid control [Windows Forms], hiding columns
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
ms.openlocfilehash: c730be934e9b978bdaf09bc7e668b4318077fba5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743302"
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="9a359-102">방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기</span><span class="sxs-lookup"><span data-stu-id="9a359-102">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="9a359-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a359-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="9a359-104">자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a359-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="9a359-105"><xref:System.Windows.Forms.GridColumnStylesCollection> 및 <xref:System.Windows.Forms.DataGridColumnStyle> 개체 (<xref:System.Windows.Forms.DataGridTableStyle> 클래스의 멤버)의 속성과 메서드를 사용 하 여 Windows Forms <xref:System.Windows.Forms.DataGrid> 컨트롤의 열을 프로그래밍 방식으로 삭제 하거나 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a359-105">You can programmatically delete or hide columns in the Windows Forms <xref:System.Windows.Forms.DataGrid> control by using the properties and methods of the <xref:System.Windows.Forms.GridColumnStylesCollection> and <xref:System.Windows.Forms.DataGridColumnStyle> objects (which are members of the <xref:System.Windows.Forms.DataGridTableStyle> class).</span></span>  
  
 <span data-ttu-id="9a359-106">삭제 된 열 이나 숨겨진 열이 표가 바인딩된 데이터 소스에 여전히 존재 하 고 프로그래밍 방식으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a359-106">The deleted or hidden columns still exist in the data source the grid is bound to, and can still be accessed programmatically.</span></span> <span data-ttu-id="9a359-107">이러한 기능은 datagrid에 더 이상 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a359-107">They are just no longer visible in the datagrid.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9a359-108">응용 프로그램이 데이터의 특정 열에 액세스 하지 않고 datagrid에 표시 하지 않으려는 경우 처음에 데이터 소스에 포함 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a359-108">If your application does not access certain columns of data, and you do not want them displayed in the datagrid, then it is probably not necessary to include them in the data source in the first place.</span></span>  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a><span data-ttu-id="9a359-109">프로그래밍 방식으로 DataGrid에서 열을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="9a359-109">To delete a column from the DataGrid programmatically</span></span>  
  
1. <span data-ttu-id="9a359-110">폼의 선언 영역에서 <xref:System.Windows.Forms.DataGridTableStyle> 클래스의 새 인스턴스를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a359-110">In the declarations area of your form, declare a new instance of the <xref:System.Windows.Forms.DataGridTableStyle> class.</span></span>  
  
2. <span data-ttu-id="9a359-111"><xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> 속성을 스타일을 적용 하려는 데이터 원본의 테이블로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a359-111">Set the <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> property to the table in your data source that you want to apply the style to.</span></span> <span data-ttu-id="9a359-112">다음 예에서는가 이미 설정 된 것으로 가정 하는 <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a359-112">The following example uses the <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> property, which it assumes is already set.</span></span>  
  
3. <span data-ttu-id="9a359-113">새 <xref:System.Windows.Forms.DataGridTableStyle> 개체를 datagrid의 테이블 스타일 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a359-113">Add the new <xref:System.Windows.Forms.DataGridTableStyle> object to the datagrid's table styles collection.</span></span>  
  
4. <span data-ttu-id="9a359-114"><xref:System.Windows.Forms.DataGrid>의 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 컬렉션에 대 한 <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> 메서드를 호출 하 여 삭제할 열의 열 인덱스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a359-114">Call the <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DataGrid>'s <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> collection, specifying the column index of the column to delete.</span></span>  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub DeleteColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Delete the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles.RemoveAt(0)  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void deleteColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Delete the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles.RemoveAt(0);  
    }  
    ```  
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a><span data-ttu-id="9a359-115">프로그래밍 방식으로 DataGrid에서 열을 숨기려면</span><span class="sxs-lookup"><span data-stu-id="9a359-115">To hide a column in the DataGrid programmatically</span></span>  
  
1. <span data-ttu-id="9a359-116">폼의 선언 영역에서 <xref:System.Windows.Forms.DataGridTableStyle> 클래스의 새 인스턴스를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a359-116">In the declarations area of your form, declare a new instance of the <xref:System.Windows.Forms.DataGridTableStyle> class.</span></span>  
  
2. <span data-ttu-id="9a359-117"><xref:System.Windows.Forms.DataGridTableStyle>의 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 속성을 스타일을 적용 하려는 데이터 원본의 테이블로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a359-117">Set the <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> property of the <xref:System.Windows.Forms.DataGridTableStyle> to the table in your data source that you want to apply the style to.</span></span> <span data-ttu-id="9a359-118">다음 코드 예제에서는가 이미 설정 된 것으로 가정 하는 <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a359-118">The following code example uses the <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> property, which it assumes is already set.</span></span>  
  
3. <span data-ttu-id="9a359-119">새 <xref:System.Windows.Forms.DataGridTableStyle> 개체를 datagrid의 테이블 스타일 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a359-119">Add the new <xref:System.Windows.Forms.DataGridTableStyle> object to the datagrid's table styles collection.</span></span>  
  
4. <span data-ttu-id="9a359-120">`Width` 속성을 0으로 설정 하 여 열을 숨기고 숨길 열의 열 인덱스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a359-120">Hide the column by setting its `Width` property to 0, specifying the column index of the column to hide.</span></span>  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub HideColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Hide the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles(0).Width = 0  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void hideColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Hide the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles[0].Width = 0;  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9a359-121">참조</span><span class="sxs-lookup"><span data-stu-id="9a359-121">See also</span></span>

- [<span data-ttu-id="9a359-122">방법: 런타임에 Windows Forms DataGrid 컨트롤에 표시되는 데이터 변경</span><span class="sxs-lookup"><span data-stu-id="9a359-122">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](change-displayed-data-at-run-time-wf-datagrid-control.md)
- [<span data-ttu-id="9a359-123">방법: Windows Forms DataGrid 컨트롤에 테이블 및 열 추가</span><span class="sxs-lookup"><span data-stu-id="9a359-123">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
