---
title: DataGridView 컨트롤의 데이터 서식 지정
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in grids
- data grids [Windows Forms], formatting data
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
ms.openlocfilehash: a041bcc5e1b65afb3123f1f42e0f1b5a479b5764
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743988"
---
# <a name="data-formatting-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤에서 데이터 형식 지정
<xref:System.Windows.Forms.DataGridView> 컨트롤은 셀 값과 부모 열에 표시 되는 데이터 형식 간의 자동 변환을 제공 합니다. 텍스트 상자 열 (예: 날짜, 시간, 숫자 및 열거형 값의 문자열 표현을 표시 하 고 사용자가 입력 한 문자열 값을 데이터 저장소에 필요한 형식으로 변환)  
  
## <a name="formatting-with-the-datagridviewcellstyle-class"></a>DataGridViewCellStyle 클래스를 사용 하 여 서식 지정  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스를 통해 셀 값의 기본 데이터 서식을 제공 합니다. <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 속성을 사용 하 여 형식 [지정](../../../standard/base-types/formatting-types.md)형식에 설명 된 형식 지정자를 사용 하 여 현재 기본 문화권의 날짜, 시간, 숫자 및 열거형 값에 서식을 지정할 수 있습니다. <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A> 속성을 사용 하 여 특정 문화권에 대해 이러한 값의 형식을 지정할 수도 있습니다. 지정 된 형식은 데이터를 표시 하 고 사용자가 지정 된 형식으로 입력 한 데이터를 구문 분석 하는 데 사용 됩니다.  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스는 wordwrap, 텍스트 맞춤 및 null 데이터베이스 값의 사용자 지정 표시에 대 한 추가 서식 속성을 제공 합니다. 자세한 내용은 [방법: Windows Forms DataGridView 컨트롤의 데이터 형식 지정](how-to-format-data-in-the-windows-forms-datagridview-control.md)을 참조하세요.  
  
## <a name="formatting-with-the-cellformatting-event"></a>셀 서식 지정 이벤트로 서식 지정  
 기본 형식이 요구 사항에 맞지 않는 경우 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> 이벤트에 대 한 처리기에서 사용자 지정 데이터 형식을 제공할 수 있습니다. 처리기에 전달 된 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs>에는 처음에 셀 값을 포함 하는 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> 속성이 있습니다. 일반적으로이 값은 자동으로 표시 형식으로 변환 됩니다. 값을 직접 변환 하려면 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> 속성을 표시 형식 값으로 설정 합니다.  
  
> [!NOTE]
> 셀에 서식 문자열이 적용 되는 경우 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> 속성을 `true`로 설정 하지 않으면 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> 속성 값의 변경 내용이 재정의 됩니다.  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트는 값을 기준으로 개별 셀의 <xref:System.Windows.Forms.DataGridViewCellStyle> 속성을 설정 하려는 경우에도 유용 합니다. 자세한 내용은 [방법: DataGridView 컨트롤 Windows Forms에서 데이터 형식 사용자 지정](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)을 참조 하세요.  
  
 사용자 지정 값의 기본 구문 분석이 사용자의 요구에 맞지 않는 경우 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.CellParsing> 이벤트를 처리 하 여 사용자 지정 구문 분석을 제공할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Windows Forms DataGridView 컨트롤에서 데이터 표시](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 셀 스타일](cell-styles-in-the-windows-forms-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤의 데이터 형식 지정](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
