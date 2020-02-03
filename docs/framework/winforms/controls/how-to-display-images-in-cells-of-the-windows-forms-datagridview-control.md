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
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤의 셀에 이미지 표시
그림 또는 그래픽은 데이터 행에 표시할 수 있는 값 중 하나입니다. 이러한 그래픽은 종종 직원의 사진이 나 회사 로고 형태로 사용 됩니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤 내에 데이터를 표시 하는 경우 그림을 통합 하는 것이 간단 합니다. <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Drawing.Image> 클래스에서 지 원하는 모든 이미지 형식과 일부 데이터베이스에서 사용 되는 OLE 그림 형식을 기본적으로 처리 합니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤의 데이터 소스에 이미지 열이 있는 경우 <xref:System.Windows.Forms.DataGridView> 컨트롤에 의해 자동으로 표시 됩니다.  
  
 다음 코드 예제에서는 포함 된 리소스에서 아이콘을 추출 하 고 이미지 열의 모든 셀에 표시 하기 위해 비트맵으로 변환 하는 방법을 보여 줍니다. 텍스트 셀 값을 해당 이미지로 바꾸는 다른 예제 [는 방법: DataGridView 컨트롤 Windows Forms에서 데이터 형식 사용자 지정](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)을 참조 하세요.  
  
## <a name="example"></a>예제  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- <xref:System.Windows.Forms.DataGridView>이라는 `dataGridView1` 컨트롤  
  
- `tree.ico`이라는 포함 된 아이콘 리소스입니다.  
  
- <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> 및 <xref:System.Drawing?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.DataGridView>
- [Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
