---
title: DataGridView 컨트롤에 데이터 바인딩
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: e2762bf363a469abf8c1e57b851d351c1cb41b62
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745081"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="0996a-102">방법: Windows Forms DataGridView 컨트롤에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="0996a-102">How to: Bind data to the Windows Forms DataGridView control</span></span>

<span data-ttu-id="0996a-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 표준 Windows Forms 데이터 바인딩 모델을 지원 하므로 다양 한 데이터 소스에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0996a-103">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it can bind to a variety of data sources.</span></span> <span data-ttu-id="0996a-104">일반적으로 데이터 소스와의 상호 작용을 관리 하는 <xref:System.Windows.Forms.BindingSource>에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="0996a-104">Usually, you bind to a <xref:System.Windows.Forms.BindingSource> that manages the interaction with the data source.</span></span> <span data-ttu-id="0996a-105"><xref:System.Windows.Forms.BindingSource>은 데이터의 위치를 선택 하거나 수정할 때 뛰어난 유연성을 제공 하는 Windows Forms 데이터 원본 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0996a-105">The <xref:System.Windows.Forms.BindingSource> can be any Windows Forms data source, which gives you great flexibility when choosing or modifying your data's location.</span></span> <span data-ttu-id="0996a-106"><xref:System.Windows.Forms.DataGridView> 컨트롤에서 지 원하는 데이터 소스에 대 한 자세한 내용은 [DataGridView 컨트롤 개요](datagridview-control-overview-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0996a-106">For more information about data sources the <xref:System.Windows.Forms.DataGridView> control supports, see the [DataGridView control overview](datagridview-control-overview-windows-forms.md).</span></span>  

<span data-ttu-id="0996a-107">Visual Studio에는 DataGridView 컨트롤에 대 한 데이터 바인딩이 광범위 하 게 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0996a-107">Visual Studio has extensive support for data binding to the DataGridView control.</span></span> <span data-ttu-id="0996a-108">자세한 내용은 [방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에 데이터 바인딩](bind-data-to-the-datagrid-using-the-designer.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0996a-108">For more information, see [How to: Bind data to the Windows Forms DataGridView control using the Designer](bind-data-to-the-datagrid-using-the-designer.md).</span></span>  

<span data-ttu-id="0996a-109">DataGridView 컨트롤을 데이터에 연결 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0996a-109">To connect a DataGridView control to data:</span></span>

1. <span data-ttu-id="0996a-110">데이터 검색에 대 한 세부 정보를 처리 하는 메서드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0996a-110">Implement a method to handle the details of retrieving the data.</span></span> <span data-ttu-id="0996a-111">다음 코드 예제에서는 <xref:System.Data.SqlClient.SqlDataAdapter>를 초기화 하 고이를 사용 하 여 <xref:System.Data.DataTable>를 채우는 `GetData` 메서드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0996a-111">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter>, and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="0996a-112">그런 다음 <xref:System.Data.DataTable> <xref:System.Windows.Forms.BindingSource>에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="0996a-112">It then binds the <xref:System.Data.DataTable> to the <xref:System.Windows.Forms.BindingSource>.</span></span> 

2. <span data-ttu-id="0996a-113">양식의 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 <xref:System.Windows.Forms.BindingSource>에 바인딩하고 `GetData` 메서드를 호출 하 여 데이터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="0996a-113">In the form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource>, and call the `GetData` method to retrieve the data.</span></span>  

## <a name="example"></a><span data-ttu-id="0996a-114">예</span><span class="sxs-lookup"><span data-stu-id="0996a-114">Example</span></span>

<span data-ttu-id="0996a-115">이 전체 코드 예제에서는 데이터베이스에서 데이터를 검색 하 여 Windows form에서 DataGridView 컨트롤을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="0996a-115">This complete code example retrieves data from a database to populate a DataGridView control in a Windows form.</span></span> <span data-ttu-id="0996a-116">또한 폼에는 데이터를 다시 로드 하 고 변경 내용을 데이터베이스에 전송 하는 단추도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0996a-116">The form also has buttons to reload data and submit changes to the database.</span></span>  

<span data-ttu-id="0996a-117">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0996a-117">This example requires:</span></span> 

- <span data-ttu-id="0996a-118">Northwind SQL Server 예제 데이터베이스에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="0996a-118">Access to a Northwind SQL Server sample database.</span></span> <span data-ttu-id="0996a-119">Northwind 샘플 데이터베이스를 설치 하는 방법에 대 한 자세한 내용은 [ADO.NET 코드 샘플에 대 한 샘플 데이터베이스 가져오기](../../data/adonet/sql/linq/downloading-sample-databases.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0996a-119">For more information about installing the Northwind sample database, see [Get the sample databases for ADO.NET code samples](../../data/adonet/sql/linq/downloading-sample-databases.md).</span></span> 

- <span data-ttu-id="0996a-120">시스템, System.web, System.xml 및 System.xml 어셈블리에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="0996a-120">References to the System, System.Windows.Forms, System.Data, and System.Xml assemblies.</span></span>  

<span data-ttu-id="0996a-121">이 예제를 빌드하고 실행 하려면 코드를 새 Windows Forms 프로젝트의 *Form1* 코드 파일에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="0996a-121">To build and run this example, paste the code into the *Form1* code file in a new Windows Forms project.</span></span> <span data-ttu-id="0996a-122">C# 또는 Visual Basic 명령줄에서 빌드하는 방법에 대 한 자세한 내용은 [Csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) 또는 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0996a-122">For information about building from the C# or Visual Basic command line, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
<span data-ttu-id="0996a-123">예제의 `connectionString` 변수를 Northwind SQL Server 샘플 데이터베이스 연결 값으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="0996a-123">Populate the `connectionString` variable in the example with the values for your Northwind SQL Server sample database connection.</span></span> <span data-ttu-id="0996a-124">통합 보안이 라고도 하는 Windows 인증을 통해 연결 문자열에 암호를 저장 하는 것 보다 데이터베이스에 연결 하는 것이 더 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="0996a-124">Windows Authentication, also called integrated security, is a more secure way to connect to the database than storing a password in the connection string.</span></span> <span data-ttu-id="0996a-125">연결 보안에 대 한 자세한 내용은 [연결 정보 보호](../../data/adonet/protecting-connection-information.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0996a-125">For more information about connection security, see [Protect connection information](../../data/adonet/protecting-connection-information.md).</span></span>  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0996a-126">참조</span><span class="sxs-lookup"><span data-stu-id="0996a-126">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="0996a-127">Windows Forms DataGridView 컨트롤의 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="0996a-127">Display data in the Windows Forms DataGridView control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="0996a-128">연결 정보 보호</span><span class="sxs-lookup"><span data-stu-id="0996a-128">Protect connection information</span></span>](../../data/adonet/protecting-connection-information.md)
