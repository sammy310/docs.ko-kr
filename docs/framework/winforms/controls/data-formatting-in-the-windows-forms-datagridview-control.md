---
title: Windows Forms DataGridView 컨트롤에서 데이터 형식 지정
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in grids
- data grids [Windows Forms], formatting data
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
ms.openlocfilehash: b5c055bdd12a4bede6e77233726c697de424a055
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011448"
---
# <a name="data-formatting-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤에서 데이터 형식 지정
<xref:System.Windows.Forms.DataGridView> 컨트롤에 셀 값 사이의 부모 열을 표시 하는 데이터 형식 자동 변환을 제공 합니다. 예를 들어, 텍스트 상자 열 날짜, 시간, 숫자 및 열거형 값의 문자열 표현을 표시 하 고 사용자가 입력 한 문자열 값 데이터 저장소에 필요한 형식으로 변환 합니다.  
  
## <a name="formatting-with-the-datagridviewcellstyle-class"></a>DataGridViewCellStyle 클래스를 사용 하 여 서식 지정  
 합니다 <xref:System.Windows.Forms.DataGridView> 컨트롤의 셀 값을 통해 기본 데이터 형식을 제공 합니다 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스입니다. 사용할 수는 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 속성에 설명 된 형식 지정자를 사용 하 여 현재 기본 문화권의 날짜, 시간, 숫자 및 열거형 값의 형식 [형식](../../../standard/base-types/formatting-types.md)합니다. 이러한 값을 사용 하 여 특정 문화권에 대 한 형식을 지정할 수도 있습니다는 <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A> 속성입니다. 지정된 된 형식의 데이터를 표시 하 고 지정 된 형식의 사용자가 입력 한 데이터를 구문 분석에 사용 됩니다.  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스는 자동 줄 바꿈, 텍스트 맞춤 및 null 데이터베이스 값의 사용자 지정 표시에 대 한 추가 서식 속성을 제공 합니다. 자세한 내용은 [방법: 형식 데이터에는 Windows Forms DataGridView 컨트롤](how-to-format-data-in-the-windows-forms-datagridview-control.md)합니다.  
  
## <a name="formatting-with-the-cellformatting-event"></a>CellFormatting 이벤트를 사용 하 여 서식 지정  
 기본 서식 요구를 충족 하지 않습니다, 경우에 사용자 지정 데이터에 대 한 처리기에서 서식 지정을 제공할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> 이벤트입니다. 합니다 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> 처리기에 전달에 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> 처음에 셀 값을 포함 하는 속성입니다. 일반적으로이 값 표시 형식에 자동으로 변환 됩니다. 설정 값으로 직접 변환 하려면를 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> 속성은 표시 형식의 값입니다.  
  
> [!NOTE]
>  셀에 대 한 적용 되는 형식 문자열의 변경 내용을 재정의 합니다 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> 속성 값을 설정 하지 않으면 합니다 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> 속성을 `true`입니다.  
  
 합니다 <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트는 설정 하려는 경우에 유용도 <xref:System.Windows.Forms.DataGridViewCellStyle> 개별 셀에 대 한 속성 값을 기준으로 합니다. 자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)합니다.  
  
 사용자가 지정한 값의 기본 구문 분석에 맞지 않는 요구 하는 경우를 처리할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.CellParsing> 의 이벤트는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용자 지정 구문 분석을 제공 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Windows Forms DataGridView 컨트롤에서 데이터 표시](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 셀 스타일](cell-styles-in-the-windows-forms-datagridview-control.md)
- [방법: 형식 데이터에는 Windows Forms DataGridView 컨트롤](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
