---
title: '방법: Windows Forms DataGridView 컨트롤에서-Just-in-time 데이터 로드를 사용 하 여 가상 모드 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], just-in-time data loading
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- just-in-time data loading
- DataGridView control [Windows Forms], large data sets
- virtual mode [Windows Forms], just-in-time data loading
ms.assetid: 33825f92-7a22-40ee-86d9-9a2ed1ead7b7
ms.openlocfilehash: 0aeba7c39bb19de0300e166936e3f8b8f70f83b0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702804"
---
# <a name="how-to-implement-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="a8254-102">방법: Windows Forms DataGridView 컨트롤에서-Just-in-time 데이터 로드를 사용 하 여 가상 모드 구현</span><span class="sxs-lookup"><span data-stu-id="a8254-102">How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="a8254-103">다음 코드 예제에서는 필요한 경우에만 서버에서 데이터를 로드하는 데이터 캐시와 함께 <xref:System.Windows.Forms.DataGridView> 컨트롤의 가상 모드를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a8254-103">The following code example shows how to use virtual mode in the <xref:System.Windows.Forms.DataGridView> control with a data cache that loads data from a server only when it is needed.</span></span> <span data-ttu-id="a8254-104">이 예제에서 자세히 설명 되어 [Windows Forms DataGridView 컨트롤에서 Just-In-Time 데이터 로드 사용 하 여 가상 모드 구현](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a8254-104">This example is described in detail in [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8254-105">예제</span><span class="sxs-lookup"><span data-stu-id="a8254-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a8254-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="a8254-106">Compiling the Code</span></span>  
 <span data-ttu-id="a8254-107">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a8254-107">This example requires:</span></span>  
  
-   <span data-ttu-id="a8254-108">System, System.Data, System.Xml 및 System.Windows.Forms assemblies 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="a8254-108">References to the System, System.Data, System.Xml, and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="a8254-109">Northwind SQL Server 샘플 데이터베이스가 설치된 서버에 대한 액세스 권한</span><span class="sxs-lookup"><span data-stu-id="a8254-109">Access to a server with the Northwind SQL Server sample database installed.</span></span>  
  
 <span data-ttu-id="a8254-110">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a8254-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="a8254-111">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8254-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a8254-112">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="a8254-112">.NET Framework Security</span></span>  
 <span data-ttu-id="a8254-113">암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 애플리케이션 보안 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8254-113">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="a8254-114">데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="a8254-114">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="a8254-115">자세한 내용은 [연결 정보 보호](../../data/adonet/protecting-connection-information.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8254-115">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8254-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="a8254-116">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- [<span data-ttu-id="a8254-117">Windows Forms DataGridView 컨트롤에서 Just-In-Time 데이터 로드를 사용하여 가상 모드 구현</span><span class="sxs-lookup"><span data-stu-id="a8254-117">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [<span data-ttu-id="a8254-118">Windows Forms DataGridView 컨트롤의 성능 조정</span><span class="sxs-lookup"><span data-stu-id="a8254-118">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="a8254-119">Windows Forms DataGridView 컨트롤의 가상 모드</span><span class="sxs-lookup"><span data-stu-id="a8254-119">Virtual Mode in the Windows Forms DataGridView Control</span></span>](virtual-mode-in-the-windows-forms-datagridview-control.md)
