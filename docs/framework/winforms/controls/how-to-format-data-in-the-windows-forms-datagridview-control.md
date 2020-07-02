---
title: DataGridView 컨트롤의 데이터 서식 지정
description: Windows Forms DataGridView 컨트롤의 Datagridviewband.defaultcellstyle 속성 및 컨트롤의 특정 열을 사용 하 여 셀 값의 형식을 지정 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in DataGridView control
- data grids [Windows Forms], enabling wordwrap
- currency values [Windows Forms], formatting in data grids
- data grids [Windows Forms], currency values
- data grids [Windows Forms], formatting data
- data grids [Windows Forms], text alignment
- data grids [Windows Forms], date values
- cells [Windows Forms], text alignment
ms.assetid: 8c33543c-9c08-4636-a65a-fdf714a529b7
ms.openlocfilehash: d6105c1d1120876f854332e7a10106cc1caf6276
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622811"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 지정
다음 절차에서는 컨트롤 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> 의 속성 <xref:System.Windows.Forms.DataGridView> 및 컨트롤의 특정 열을 사용 하 여 셀 값의 기본적인 서식 지정을 보여 줍니다. 고급 데이터 서식에 대 한 자세한 내용은 [방법: DataGridView 컨트롤 Windows Forms에서 데이터 형식 사용자 지정](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)을 참조 하세요.  
  
### <a name="to-format-currency-and-date-values"></a>통화 및 날짜 값의 서식을 지정 하려면  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle>의 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 속성을 설정합니다. 다음 코드 예에서는 열의 속성을 사용 하 여 특정 열의 형식을 설정 합니다 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> . `UnitPrice`열의 값은 현재 문화권별 통화 형식으로 나타나며 음수 값은 괄호로 묶여 있습니다. 열의 값이 `ShipDate` 현재 문화권별 짧은 날짜 형식으로 표시 됩니다. 값에 대 한 자세한 내용은 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> [형식 서식 지정](../../../standard/base-types/formatting-types.md)을 참조 하세요.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a>Null 데이터베이스 값의 표시를 사용자 지정 하려면  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle>의 <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> 속성을 설정합니다. 다음 코드 예제에서는 속성을 사용 하 여 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> 와 같은 값을 포함 하는 모든 셀에 "no entry"를 표시 합니다 <xref:System.DBNull.Value?displayProperty=nameWithType> .  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a>텍스트 기반 셀에서 wordwrap를 사용 하도록 설정 하려면  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>의 속성을 <xref:System.Windows.Forms.DataGridViewCellStyle> 열거형 값 중 하나로 설정 합니다 <xref:System.Windows.Forms.DataGridViewTriState> . 다음 코드 예제에서는 속성을 사용 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> 하 여 전체 컨트롤에 대 한 줄 바꿈 모드를 설정 합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a>DataGridView 셀의 텍스트 맞춤을 지정 하려면  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>의 속성을 <xref:System.Windows.Forms.DataGridViewCellStyle> 열거형 값 중 하나로 설정 합니다 <xref:System.Windows.Forms.DataGridViewContentAlignment> . 다음 코드 예에서는 열의 속성을 사용 하 여 특정 열에 대 한 맞춤을 설정 합니다 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> .  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a>예제  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이러한 예제에는 다음이 필요합니다.  
  
- 이라는 열, 이라는 열 및 이라는 열이 <xref:System.Windows.Forms.DataGridView> 포함 된 이라는 컨트롤입니다 `dataGridView1` `UnitPrice` `ShipDate` `CustomerName` .  
  
- <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 확장성을 최대화 하려면 <xref:System.Windows.Forms.DataGridViewCellStyle> 각 요소에 대 한 스타일 속성을 별도로 설정 하는 대신 동일한 스타일을 사용 하는 여러 행, 열 또는 셀에서 개체를 공유 해야 합니다. 자세한 내용은 [Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법](best-practices-for-scaling-the-windows-forms-datagridview-control.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Windows Forms DataGridView 컨트롤에서 기본 형식 및 스타일 지정](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 셀 스타일](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤에서 데이터 형식 지정](data-formatting-in-the-windows-forms-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
- [형식 서식 지정](../../../standard/base-types/formatting-types.md)
