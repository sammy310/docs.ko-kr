---
title: DataGridView 컨트롤의 셀에 이미지 표시
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
ms.openlocfilehash: e0e125c816877875b80e0f20887d9beee443577a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740279"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="56add-102">방법: Windows Forms DataGridView 컨트롤의 셀에 이미지 표시</span><span class="sxs-lookup"><span data-stu-id="56add-102">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="56add-103">그림 또는 그래픽은 데이터 행에 표시할 수 있는 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="56add-103">A picture or graphic is one of the values that you can display in a row of data.</span></span> <span data-ttu-id="56add-104">이러한 그래픽은 종종 직원의 사진이 나 회사 로고 형태로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56add-104">Frequently, these graphics take the form of an employee's photograph or a company logo.</span></span>  
  
 <span data-ttu-id="56add-105"><xref:System.Windows.Forms.DataGridView> 컨트롤 내에 데이터를 표시 하는 경우 그림을 통합 하는 것이 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="56add-105">Incorporating pictures is simple when you display data within the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="56add-106"><xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Drawing.Image> 클래스에서 지 원하는 모든 이미지 형식과 일부 데이터베이스에서 사용 되는 OLE 그림 형식을 기본적으로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="56add-106">The <xref:System.Windows.Forms.DataGridView> control natively handles any image format supported by the <xref:System.Drawing.Image> class, as well as the OLE picture format used by some databases.</span></span>  
  
 <span data-ttu-id="56add-107"><xref:System.Windows.Forms.DataGridView> 컨트롤의 데이터 소스에 이미지 열이 있는 경우 <xref:System.Windows.Forms.DataGridView> 컨트롤에 의해 자동으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56add-107">If the <xref:System.Windows.Forms.DataGridView> control's data source has a column of images, they will be displayed automatically by the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="56add-108">다음 코드 예제에서는 포함 된 리소스에서 아이콘을 추출 하 고 이미지 열의 모든 셀에 표시 하기 위해 비트맵으로 변환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="56add-108">The following code example demonstrates how to extract an icon from an embedded resource and convert it to a bitmap for display in every cell of an image column.</span></span> <span data-ttu-id="56add-109">텍스트 셀 값을 해당 이미지로 바꾸는 다른 예제 [는 방법: DataGridView 컨트롤 Windows Forms에서 데이터 형식 사용자 지정](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="56add-109">For another example that replaces textual cell values with corresponding images, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="56add-110">예제</span><span class="sxs-lookup"><span data-stu-id="56add-110">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="56add-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="56add-111">Compiling the Code</span></span>  
 <span data-ttu-id="56add-112">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="56add-112">This example requires:</span></span>  
  
- <span data-ttu-id="56add-113"><xref:System.Windows.Forms.DataGridView>이라는 `dataGridView1` 컨트롤</span><span class="sxs-lookup"><span data-stu-id="56add-113">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="56add-114">`tree.ico`이라는 포함 된 아이콘 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="56add-114">An embedded icon resource named `tree.ico`.</span></span>  
  
- <span data-ttu-id="56add-115"><xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> 및 <xref:System.Drawing?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="56add-115">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56add-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56add-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="56add-117">Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능</span><span class="sxs-lookup"><span data-stu-id="56add-117">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="56add-118">방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="56add-118">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
