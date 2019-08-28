---
title: '방법: Windows Forms DataGrid 컨트롤에 테이블 및 열 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
ms.openlocfilehash: bfb0296566fecc2029df16d91c9c04d7daa4b4b5
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046163"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a><span data-ttu-id="97a17-102">방법: Windows Forms DataGrid 컨트롤에 테이블 및 열 추가</span><span class="sxs-lookup"><span data-stu-id="97a17-102">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>

> [!NOTE]
> <span data-ttu-id="97a17-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97a17-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="97a17-104">자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="97a17-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

<span data-ttu-id="97a17-105">**DataGridTableStyle** 개체를 만들고 <xref:System.Windows.Forms.DataGrid> 컨트롤의를 <xref:System.Windows.Forms.DataGrid> 통해 액세스 되는 **GridTableStylesCollection** 개체에 추가 하 여 테이블 및 열에 Windows Forms 컨트롤의 데이터를 표시할 수 있습니다. **System.windows.forms.datagrid.tablestyles** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="97a17-105">You can display data in the Windows Forms <xref:System.Windows.Forms.DataGrid> control in tables and columns by creating **DataGridTableStyle** objects and adding them to the **GridTableStylesCollection** object, which is accessed through the <xref:System.Windows.Forms.DataGrid> control's **TableStyles** property.</span></span> <span data-ttu-id="97a17-106">각 테이블 스타일은 **DataGridTableStyle** 개체의 **MappingName** 속성에 지정 된 모든 데이터 테이블의 내용을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="97a17-106">Each table style displays the contents of whatever data table is specified in the **DataGridTableStyle** object's **MappingName** property.</span></span> <span data-ttu-id="97a17-107">기본적으로 열 스타일이 지정 되지 않은 테이블 스타일은 해당 데이터 테이블 내의 모든 열을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="97a17-107">By default, a table style with no column styles specified will display all the columns within that data table.</span></span> <span data-ttu-id="97a17-108">각 **DataGridTableStyle** 의 **gridcolumnstyles** 속성을 통해 액세스 되는 **GridColumnStylesCollection** 개체에 **system.windows.forms.datagridcolumnstyle>** 개체를 추가 하 여 표시 되는 테이블의 열을 제한할 수 있습니다. 개체가.</span><span class="sxs-lookup"><span data-stu-id="97a17-108">You can restrict which columns from the table appear by adding **DataGridColumnStyle** objects to the **GridColumnStylesCollection** object, which is accessed through the **GridColumnStyles** property of each **DataGridTableStyle** object.</span></span>

### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a><span data-ttu-id="97a17-109">프로그래밍 방식으로 DataGrid에 테이블과 열을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="97a17-109">To add a table and column to a DataGrid programmatically</span></span>

1. <span data-ttu-id="97a17-110">테이블에 데이터를 표시 하려면 먼저 <xref:System.Windows.Forms.DataGrid> 컨트롤을 데이터 집합에 바인딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97a17-110">In order to display data in the table, you must first bind the <xref:System.Windows.Forms.DataGrid> control to a dataset.</span></span> <span data-ttu-id="97a17-111">자세한 내용은 [방법: Windows Forms DataGrid 컨트롤을 데이터 소스](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="97a17-111">For more information, see [How to: Bind the Windows Forms DataGrid Control to a Data Source](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>

    > [!CAUTION]
    > <span data-ttu-id="97a17-112">프로그래밍 방식으로 열 스타일을 지정 하는 경우에는 **system.windows.forms.datagridcolumnstyle>** 개체를 만든 다음이 개체를 **GridColumnStylesCollection** 개체에 추가 하 여 다음에 **DataGridTableStyle** 개체를 추가 합니다 **. GridTableStylesCollection** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="97a17-112">When programmatically specifying column styles, always create **DataGridColumnStyle** objects and add them to the **GridColumnStylesCollection** object before adding **DataGridTableStyle** objects to the **GridTableStylesCollection** object.</span></span> <span data-ttu-id="97a17-113">컬렉션에 빈 **DataGridTableStyle** 개체를 추가 하면 **system.windows.forms.datagridcolumnstyle>** 개체가 자동으로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97a17-113">When you add an empty **DataGridTableStyle** object to the collection, **DataGridColumnStyle** objects are automatically generated for you.</span></span> <span data-ttu-id="97a17-114">따라서 **MappingName** 값이 중복 되는 새 **System.windows.forms.datagridcolumnstyle>** 개체를 **GridColumnStylesCollection** 개체에 추가 하려고 하면 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97a17-114">Consequently, an exception will be thrown if you try to add new **DataGridColumnStyle** objects with duplicate **MappingName** values to the **GridColumnStylesCollection** object.</span></span>

2. <span data-ttu-id="97a17-115">새 테이블 스타일을 선언 하 고 매핑 이름을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="97a17-115">Declare a new table style and set its mapping name.</span></span>

    ```vb
    Dim ts1 As New DataGridTableStyle()
    ts1.MappingName = "Customers"
    ```

    ```csharp
    DataGridTableStyle ts1 = new DataGridTableStyle();
    ts1.MappingName = "Customers";
    ```

    ```cpp
    DataGridTableStyle* ts1 = new DataGridTableStyle();
    ts1->MappingName = S"Customers";
    ```

3. <span data-ttu-id="97a17-116">새 열 스타일을 선언 하 고 해당 매핑 이름 및 기타 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="97a17-116">Declare a new column style and set its mapping name and other properties.</span></span>

    ```vb
    Dim myDataCol As New DataGridBoolColumn()
    myDataCol.HeaderText = "My New Column"
    myDataCol.MappingName = "Current"
    ```

    ```csharp
    DataGridBoolColumn myDataCol = new DataGridBoolColumn();
    myDataCol.HeaderText = "My New Column";
    myDataCol.MappingName = "Current";
    ```

    ```cpp
    DataGridBoolColumn^ myDataCol = gcnew DataGridBoolColumn();
    myDataCol->HeaderText = "My New Column";
    myDataCol->MappingName = "Current";
    ```

4. <span data-ttu-id="97a17-117">**GridColumnStylesCollection** 개체의 **add** 메서드를 호출 하 여 테이블 스타일에 열을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="97a17-117">Call the **Add** method of the **GridColumnStylesCollection** object to add the column to the table style</span></span>

    ```vb
    ts1.GridColumnStyles.Add(myDataCol)
    ```

    ```csharp
    ts1.GridColumnStyles.Add(myDataCol);
    ```

    ```cpp
    ts1->GridColumnStyles->Add(myDataCol);
    ```

5. <span data-ttu-id="97a17-118">**GridTableStylesCollection** 개체의 **Add** 메서드를 호출 하 여 테이블 스타일을 데이터 표에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="97a17-118">Call the **Add** method of the **GridTableStylesCollection** object to add the table style to the data grid.</span></span>

    ```vb
    DataGrid1.TableStyles.Add(ts1)
    ```

    ```csharp
    dataGrid1.TableStyles.Add(ts1);
    ```

    ```cpp
    dataGrid1->TableStyles->Add(ts1);
    ```

## <a name="see-also"></a><span data-ttu-id="97a17-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="97a17-119">See also</span></span>

- [<span data-ttu-id="97a17-120">DataGrid 컨트롤</span><span class="sxs-lookup"><span data-stu-id="97a17-120">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="97a17-121">방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기</span><span class="sxs-lookup"><span data-stu-id="97a17-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
