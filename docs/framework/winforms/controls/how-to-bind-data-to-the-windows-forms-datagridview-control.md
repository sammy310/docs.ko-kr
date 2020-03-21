---
title: 데이터를 데이터그리드뷰 제어에 바인딩
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: 643dcd37cd1bb3f8b5938fedff66c67cd68278ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182271"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="75d37-102">방법: Windows 양식 DataGridView 컨트롤에 데이터를 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="75d37-102">How to: Bind data to the Windows Forms DataGridView control</span></span>

<span data-ttu-id="75d37-103">컨트롤은 <xref:System.Windows.Forms.DataGridView> 표준 Windows Forms 데이터 바인딩 모델을 지원하므로 다양한 데이터 원본에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d37-103">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it can bind to a variety of data sources.</span></span> <span data-ttu-id="75d37-104">일반적으로 데이터 원본과의 <xref:System.Windows.Forms.BindingSource> 상호 작용을 관리하는 에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="75d37-104">Usually, you bind to a <xref:System.Windows.Forms.BindingSource> that manages the interaction with the data source.</span></span> <span data-ttu-id="75d37-105">모든 <xref:System.Windows.Forms.BindingSource> Windows Forms 데이터 원본이 될 수 있으므로 데이터의 위치를 선택하거나 수정할 때 유연성이 뛰어나습니다.</span><span class="sxs-lookup"><span data-stu-id="75d37-105">The <xref:System.Windows.Forms.BindingSource> can be any Windows Forms data source, which gives you great flexibility when choosing or modifying your data's location.</span></span> <span data-ttu-id="75d37-106">컨트롤이 지원하는 데이터 <xref:System.Windows.Forms.DataGridView> 원본에 대한 자세한 내용은 [DataGridView 컨트롤 개요를](datagridview-control-overview-windows-forms.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="75d37-106">For more information about data sources the <xref:System.Windows.Forms.DataGridView> control supports, see the [DataGridView control overview](datagridview-control-overview-windows-forms.md).</span></span>  

<span data-ttu-id="75d37-107">Visual Studio는 DataGridView 컨트롤에 대한 데이터 바인딩을 광범위하게 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="75d37-107">Visual Studio has extensive support for data binding to the DataGridView control.</span></span> <span data-ttu-id="75d37-108">자세한 내용은 디자이너를 [사용하여 Windows Forms DataGridView 컨트롤에 데이터를 바인딩하는 방법을](bind-data-to-the-datagrid-using-the-designer.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="75d37-108">For more information, see [How to: Bind data to the Windows Forms DataGridView control using the Designer](bind-data-to-the-datagrid-using-the-designer.md).</span></span>  

<span data-ttu-id="75d37-109">DataGridView 컨트롤을 데이터에 연결하려면 다음을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="75d37-109">To connect a DataGridView control to data:</span></span>

1. <span data-ttu-id="75d37-110">데이터 검색 세부 정보를 처리하는 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="75d37-110">Implement a method to handle the details of retrieving the data.</span></span> <span data-ttu-id="75d37-111">다음 코드 예제에서는 `GetData` <xref:System.Data.SqlClient.SqlDataAdapter>을 초기화하고 이를 사용하여 을 채우는 <xref:System.Data.DataTable>메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="75d37-111">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter>, and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="75d37-112">그런 다음 <xref:System.Data.DataTable> <xref:System.Windows.Forms.BindingSource>에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="75d37-112">It then binds the <xref:System.Data.DataTable> to the <xref:System.Windows.Forms.BindingSource>.</span></span>

2. <span data-ttu-id="75d37-113">폼의 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기에서 <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.BindingSource>컨트롤을 에 바인딩하고 `GetData` 메서드를 호출하여 데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="75d37-113">In the form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource>, and call the `GetData` method to retrieve the data.</span></span>  

## <a name="example"></a><span data-ttu-id="75d37-114">예제</span><span class="sxs-lookup"><span data-stu-id="75d37-114">Example</span></span>

<span data-ttu-id="75d37-115">이 전체 코드 예제에서는 데이터베이스에서 데이터를 검색하여 DataGridView 컨트롤을 Windows 형식으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="75d37-115">This complete code example retrieves data from a database to populate a DataGridView control in a Windows form.</span></span> <span data-ttu-id="75d37-116">양식에는 데이터를 다시 로드하고 데이터베이스에 변경 내용을 제출하는 단추도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d37-116">The form also has buttons to reload data and submit changes to the database.</span></span>  

<span data-ttu-id="75d37-117">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="75d37-117">This example requires:</span></span>

- <span data-ttu-id="75d37-118">노스윈드 SQL Server 샘플 데이터베이스에 대한 액세스.</span><span class="sxs-lookup"><span data-stu-id="75d37-118">Access to a Northwind SQL Server sample database.</span></span> <span data-ttu-id="75d37-119">Northwind 샘플 데이터베이스 설치에 대한 자세한 내용은 [ADO.NET 코드 샘플에 대한 샘플 데이터베이스 받기를](../../data/adonet/sql/linq/downloading-sample-databases.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="75d37-119">For more information about installing the Northwind sample database, see [Get the sample databases for ADO.NET code samples](../../data/adonet/sql/linq/downloading-sample-databases.md).</span></span>

- <span data-ttu-id="75d37-120">시스템, System.Windows.Forms, System.Data 및 System.Xml 어셈블리에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="75d37-120">References to the System, System.Windows.Forms, System.Data, and System.Xml assemblies.</span></span>  

<span data-ttu-id="75d37-121">이 예제를 빌드하고 실행하려면 새 Windows Forms 프로젝트의 *Form1* 코드 파일에 코드를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="75d37-121">To build and run this example, paste the code into the *Form1* code file in a new Windows Forms project.</span></span> <span data-ttu-id="75d37-122">C# 또는 Visual Basic 명령줄에서 빌드에 대한 자세한 내용은 [csc.exe를 가진 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) 또는 [명령줄에서 빌드를](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="75d37-122">For information about building from the C# or Visual Basic command line, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
<span data-ttu-id="75d37-123">예제의 `connectionString` 변수를 Northwind SQL Server 샘플 데이터베이스 연결에 대한 값으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="75d37-123">Populate the `connectionString` variable in the example with the values for your Northwind SQL Server sample database connection.</span></span> <span data-ttu-id="75d37-124">통합 보안이라고도 하는 Windows 인증은 연결 문자열에 암호를 저장하는 것보다 데이터베이스에 연결하는 보다 안전한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="75d37-124">Windows Authentication, also called integrated security, is a more secure way to connect to the database than storing a password in the connection string.</span></span> <span data-ttu-id="75d37-125">연결 보안에 대한 자세한 내용은 [연결 정보 보호를](../../data/adonet/protecting-connection-information.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="75d37-125">For more information about connection security, see [Protect connection information](../../data/adonet/protecting-connection-information.md).</span></span>  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="75d37-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75d37-126">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="75d37-127">Windows 양식 데이터그리드뷰 컨트롤에 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="75d37-127">Display data in the Windows Forms DataGridView control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="75d37-128">연결 정보 보호</span><span class="sxs-lookup"><span data-stu-id="75d37-128">Protect connection information</span></span>](../../data/adonet/protecting-connection-information.md)
