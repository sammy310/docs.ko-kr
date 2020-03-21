---
title: 데이터 그리드 컨트롤에서 런타임에 표시된 데이터 변경
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DataGrid control [Windows Forms], dynamically changing at run time
- DataGrid control [Windows Forms], data binding
- cells [Windows Forms], changing DataGrid cell values
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
ms.openlocfilehash: 6b788c10784082a0c74ee09f8cd85d540c670b84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142383"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="3d6c2-102">방법: 런타임에 Windows Forms DataGrid 컨트롤에 표시되는 데이터 변경</span><span class="sxs-lookup"><span data-stu-id="3d6c2-102">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="3d6c2-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6c2-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="3d6c2-104">자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d6c2-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="3d6c2-105">디자인 타임 기능을 사용하여 <xref:System.Windows.Forms.DataGrid> Windows Forms를 만든 후에는 런타임에 그리드 <xref:System.Data.DataSet> 개체의 요소를 동적으로 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6c2-105">After you have created a Windows Forms <xref:System.Windows.Forms.DataGrid> using the design-time features, you may also wish to dynamically change elements of the <xref:System.Data.DataSet> object of the grid at run time.</span></span> <span data-ttu-id="3d6c2-106">여기에는 테이블의 개별 값에 대한 변경 또는 <xref:System.Windows.Forms.DataGrid> 컨트롤에 바인딩된 데이터 원본 변경이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6c2-106">This can include changes to either individual values of the table or changing which data source is bound to the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="3d6c2-107">개별 값에 대한 변경 <xref:System.Data.DataSet> 은 컨트롤이 아닌 개체를 <xref:System.Windows.Forms.DataGrid> 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d6c2-107">Changes to individual values are done through the <xref:System.Data.DataSet> object, not the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
### <a name="to-change-data-programmatically"></a><span data-ttu-id="3d6c2-108">프로그래밍 방식으로 데이터를 변경하려면</span><span class="sxs-lookup"><span data-stu-id="3d6c2-108">To change data programmatically</span></span>  
  
1. <span data-ttu-id="3d6c2-109"><xref:System.Data.DataSet> 개체에서 원하는 테이블을 지정하고 테이블에서 원하는 행과 필드를 지정하고 셀을 새 값과 동일하게 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6c2-109">Specify the desired table from the <xref:System.Data.DataSet> object and the desired row and field from the table and set the cell equal to the new value.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3d6c2-110">테이블의 첫 번째 <xref:System.Data.DataSet> 테이블 또는 첫 번째 행을 지정하려면 0을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6c2-110">To specify the first table of the <xref:System.Data.DataSet> or the first row of the table, use 0.</span></span>  
  
     <span data-ttu-id="3d6c2-111">다음 예제에서는 를 클릭하여 `Button1`데이터 집합의 첫 번째 테이블의 첫 번째 행의 두 번째 항목을 변경하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6c2-111">The following example shows how to change the second entry of the first row of the first table of a dataset by clicking `Button1`.</span></span> <span data-ttu-id="3d6c2-112"><xref:System.Data.DataSet> ()`ds`및 테이블 (및)`0` `1`이전에 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6c2-112">The <xref:System.Data.DataSet> (`ds`) and Tables (`0` and `1`) were previously created.</span></span>  
  
    ```vb  
    Protected Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       ds.tables(0).rows(0)(1) = "NewEntry"  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       ds.Tables[0].Rows[0][1]="NewEntry";  
    }  
    ```  
  
    ```cpp  
    private:
       void button1_Click(System::Object^ sender, System::EventArgs^ e)  
       {  
          dataSet1->Tables[0]->Rows[0][1] = "NewEntry";  
       }  
    ```  
  
     <span data-ttu-id="3d6c2-113">(비주얼 C #, 비주얼 C++) 양식의 생성자에서 다음 코드를 배치하여 이벤트 처리기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6c2-113">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="3d6c2-114">런타임에 메서드를 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 사용하여 컨트롤을 <xref:System.Windows.Forms.DataGrid> 다른 데이터 원본에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6c2-114">At run time you can use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to bind the <xref:System.Windows.Forms.DataGrid> control to a different data source.</span></span> <span data-ttu-id="3d6c2-115">예를 들어, 여러 ADO.NET 데이터 컨트롤이 있을 수 있습니다., 각각 다른 데이터베이스에 연결.</span><span class="sxs-lookup"><span data-stu-id="3d6c2-115">For example, you may have several ADO.NET data controls, each connected to a different database.</span></span>  
  
### <a name="to-change-the-datasource-programmatically"></a><span data-ttu-id="3d6c2-116">데이터 원본을 프로그래밍 방식으로 변경하려면</span><span class="sxs-lookup"><span data-stu-id="3d6c2-116">To change the DataSource programmatically</span></span>  
  
1. <span data-ttu-id="3d6c2-117">바인딩할 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 데이터 원본 및 테이블의 이름으로 메서드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6c2-117">Set the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to the name of the data source and table you want to bind to.</span></span>  
  
     <span data-ttu-id="3d6c2-118">다음 예제에서는 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 사용하여 날짜 원본을 Pubs 데이터베이스의 Authors 테이블에 연결된 ADO.NET 데이터 컨트롤(adoPubsAuthors)으로 변경하는 방법을 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6c2-118">The following example shows how to change the date source using the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to an ADO.NET data control (adoPubsAuthors) that is connected to the Authors table in the Pubs database.</span></span>  
  
    ```vb  
    Private Sub ResetSource()  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors")  
    End Sub  
    ```  
  
    ```csharp  
    private void ResetSource()  
    {  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors");  
    }  
    ```  
  
    ```cpp  
    private:  
       void ResetSource()  
       {  
          dataGrid1->SetDataBinding(adoPubsAuthors, "Authors");  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3d6c2-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d6c2-119">See also</span></span>

- [<span data-ttu-id="3d6c2-120">ADO.NET 데이터 집합</span><span class="sxs-lookup"><span data-stu-id="3d6c2-120">ADO.NET DataSets</span></span>](../../data/adonet/ado-net-datasets.md)
- [<span data-ttu-id="3d6c2-121">방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기</span><span class="sxs-lookup"><span data-stu-id="3d6c2-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="3d6c2-122">방법: Windows Forms DataGrid 컨트롤에 테이블과 열 추가</span><span class="sxs-lookup"><span data-stu-id="3d6c2-122">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="3d6c2-123">방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="3d6c2-123">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
