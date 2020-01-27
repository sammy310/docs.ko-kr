---
title: DataGridView 컨트롤의 데이터 유효성 검사
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
ms.assetid: d10aef35-701e-4a3c-a684-2a2ed1aeaca6
ms.openlocfilehash: 5fd881829f87fa1dec135d936f22996f196b0594
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728313"
---
# <a name="how-to-validate-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8ab3f-102">방법: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="8ab3f-102">How to: Validate Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8ab3f-103">다음 코드 예제에서는 사용자가 <xref:System.Windows.Forms.DataGridView> 컨트롤에 입력한 데이터의 유효성을 검사하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8ab3f-103">The following code example demonstrates how to validate data entered by a user into a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="8ab3f-104">이 예제에서 <xref:System.Windows.Forms.DataGridView>는 Northwind 샘플 데이터베이스, `Customers` 테이블의 행으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="8ab3f-104">In this example, the <xref:System.Windows.Forms.DataGridView> is populated with rows from the `Customers` table of the Northwind sample database.</span></span> <span data-ttu-id="8ab3f-105">사용자가 `CompanyName` 열에서 셀을 편집하면 셀이 비어 있지 않은지 검사함으로써 해당 값의 유효성이 테스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ab3f-105">When the user edits a cell in the `CompanyName` column, its value is tested for validity by checking that it is not empty.</span></span> <span data-ttu-id="8ab3f-106"><xref:System.Windows.Forms.DataGridView.CellValidating> 이벤트의 이벤트 처리기가 값이 빈 문자열인 것으로 확인하면 <xref:System.Windows.Forms.DataGridView>는 비어 있지 않은 문자열이 입력될 때까지 사용자가 셀을 종료하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ab3f-106">If the event handler for the <xref:System.Windows.Forms.DataGridView.CellValidating> event finds that the value is an empty string, the <xref:System.Windows.Forms.DataGridView> prevents the user from exiting the cell until a non-empty string is entered.</span></span>  
  
 <span data-ttu-id="8ab3f-107">이 코드 예제에 대한 자세한 설명은 [연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ab3f-107">For a complete explanation of this code example, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ab3f-108">예</span><span class="sxs-lookup"><span data-stu-id="8ab3f-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8ab3f-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="8ab3f-109">Compiling the Code</span></span>  
 <span data-ttu-id="8ab3f-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8ab3f-110">This example requires:</span></span>  
  
- <span data-ttu-id="8ab3f-111">System, System.Data, System.Windows.Forms 및 System.XML 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="8ab3f-111">References to the System, System.Data, System.Windows.Forms and System.XML assemblies.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="8ab3f-112">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="8ab3f-112">.NET Framework Security</span></span>  
 <span data-ttu-id="8ab3f-113">암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 애플리케이션 보안 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab3f-113">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="8ab3f-114">데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="8ab3f-114">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="8ab3f-115">자세한 내용은 [연결 정보 보호](../../data/adonet/protecting-connection-information.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ab3f-115">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ab3f-116">참조</span><span class="sxs-lookup"><span data-stu-id="8ab3f-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="8ab3f-117">연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="8ab3f-117">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="8ab3f-118">Windows Forms DataGridView 컨트롤의 데이터 입력</span><span class="sxs-lookup"><span data-stu-id="8ab3f-118">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="8ab3f-119">연습: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리</span><span class="sxs-lookup"><span data-stu-id="8ab3f-119">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="8ab3f-120">연결 정보 보호</span><span class="sxs-lookup"><span data-stu-id="8ab3f-120">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
