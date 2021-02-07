---
description: '자세한 정보: 방법: Windows Forms DataGridView 컨트롤에 DataView 개체 바인딩'
title: '방법: Windows Forms DataGridView 컨트롤에 DataView 개체 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b73d60a-6049-446a-85a7-3e5a68b183e2
ms.openlocfilehash: 59bc1a0f6b7b2b0d6da4fa6d88e06922d95c9f46
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723909"
---
# <a name="how-to-bind-a-dataview-object-to-a-windows-forms-datagridview-control"></a><span data-ttu-id="ea5c6-103">방법: Windows Forms DataGridView 컨트롤에 DataView 개체 바인딩</span><span class="sxs-lookup"><span data-stu-id="ea5c6-103">How to: Bind a DataView Object to a Windows Forms DataGridView Control</span></span>

<span data-ttu-id="ea5c6-104"><xref:System.Windows.Forms.DataGridView> 컨트롤에서는 데이터를 표 형식으로 표시하는 강력하고 유연한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ea5c6-104">The <xref:System.Windows.Forms.DataGridView> control provides a powerful and flexible way to display data in a tabular format.</span></span> <span data-ttu-id="ea5c6-105"><xref:System.Windows.Forms.DataGridView> 컨트롤은 표준 Windows Forms 데이터 바인딩 모델을 지원하므로 <xref:System.Data.DataView> 및 다양한 데이터 소스에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="ea5c6-105">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it will bind to <xref:System.Data.DataView> and a variety of other data sources.</span></span> <span data-ttu-id="ea5c6-106">그러나 대부분의 경우 데이터 소스와의 상호 작용에 대한 세부 사항을 관리하는 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="ea5c6-106">In most situations, however, you will bind to a <xref:System.Windows.Forms.BindingSource> component that will manage the details of interacting with the data source.</span></span>  
  
 <span data-ttu-id="ea5c6-107">컨트롤에 대 한 자세한 내용은 <xref:System.Windows.Forms.DataGridView> [DataGridView 컨트롤 개요](/dotnet/desktop/winforms/controls/datagridview-control-overview-windows-forms)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ea5c6-107">For more information about the <xref:System.Windows.Forms.DataGridView> control, see [DataGridView Control Overview](/dotnet/desktop/winforms/controls/datagridview-control-overview-windows-forms).</span></span>  
  
### <a name="to-connect-a-datagridview-control-to-a-dataview"></a><span data-ttu-id="ea5c6-108">DataGridView 컨트롤을 DataView에 연결하려면</span><span class="sxs-lookup"><span data-stu-id="ea5c6-108">To connect a DataGridView control to a DataView</span></span>  
  
1. <span data-ttu-id="ea5c6-109">데이터베이스에서 데이터를 검색하는 세부 과정을 처리하는 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ea5c6-109">Implement a method to handle the details of retrieving data from a database.</span></span> <span data-ttu-id="ea5c6-110">다음 코드 예제에서는 `GetData` 구성 요소를 초기화한 다음 이 구성 요소를 사용하여 <xref:System.Data.SqlClient.SqlDataAdapter>을 채우는 <xref:System.Data.DataSet> 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ea5c6-110">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter> component and uses it to fill a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="ea5c6-111">`connectionString` 변수를 사용자의 데이터베이스에 적합한 값으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea5c6-111">Be sure to set the `connectionString` variable to a value that is appropriate for your database.</span></span> <span data-ttu-id="ea5c6-112">AdventureWorks SQL Server 샘플 데이터베이스가 설치된 서버에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea5c6-112">You will need access to a server with the AdventureWorks SQL Server sample database installed.</span></span>  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1getdata)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1getdata)]  
  
2. <span data-ttu-id="ea5c6-113">폼의 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩한 다음 `GetData` 메서드를 호출하여 데이터베이스에서 데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ea5c6-113">In the <xref:System.Windows.Forms.Form.Load> event handler of your form, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource> component and call the `GetData` method to retrieve the data from the database.</span></span> <span data-ttu-id="ea5c6-114">는 <xref:System.Data.DataView> 연락처에 대 한 LINQ to DataSet 쿼리에서 생성 된 <xref:System.Data.DataTable> 다음 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea5c6-114">The <xref:System.Data.DataView> is created from a LINQ to DataSet query over the Contact <xref:System.Data.DataTable> and is then bound to the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1formload)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1formload)]  
  
## <a name="see-also"></a><span data-ttu-id="ea5c6-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea5c6-115">See also</span></span>

- [<span data-ttu-id="ea5c6-116">데이터 바인딩 및 LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="ea5c6-116">Data Binding and LINQ to DataSet</span></span>](data-binding-and-linq-to-dataset.md)
