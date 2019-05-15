---
title: '방법: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
ms.assetid: b5d4b47d-9a28-4d88-9dba-0a3c90fba71d
ms.openlocfilehash: c488d0221080454a82e4c80f89964df0ee62f068
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591646"
---
# <a name="how-to-create-an-unbound-windows-forms-datagridview-control"></a><span data-ttu-id="5114a-102">방법: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="5114a-102">How to: Create an Unbound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="5114a-103">다음 코드 예제에서는 데이터 소스에 바인딩하지 않고 프로그래밍 방식으로 <xref:System.Windows.Forms.DataGridView> 컨트롤을 채우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5114a-103">The following code example demonstrates how to populate a <xref:System.Windows.Forms.DataGridView> control programmatically without binding it to a data source.</span></span> <span data-ttu-id="5114a-104">적은 양의 데이터를 테이블 형식으로 표시하려는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="5114a-104">This is useful when you have a small amount of data that you want to display in a table format.</span></span>  
  
 <span data-ttu-id="5114a-105">에 대 한 전체 설명은이 코드 예제를 참조 하세요. [연습: 만들기는 바인딩되지 않은 Windows Forms DataGridView 컨트롤](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5114a-105">For a complete explanation of this code example, see [Walkthrough: Creating an Unbound Windows Forms DataGridView Control](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5114a-106">예제</span><span class="sxs-lookup"><span data-stu-id="5114a-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5114a-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="5114a-107">Compiling the Code</span></span>  
 <span data-ttu-id="5114a-108">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5114a-108">This example requires:</span></span>  
  
- <span data-ttu-id="5114a-109">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="5114a-109">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5114a-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="5114a-110">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="5114a-111">연습: 만들기는 바인딩되지 않은 Windows Forms DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5114a-111">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [<span data-ttu-id="5114a-112">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="5114a-112">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="5114a-113">Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드</span><span class="sxs-lookup"><span data-stu-id="5114a-113">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
