---
title: DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
ms.openlocfilehash: 3e66b2306c11c54db14eb05cc6860257635cc653
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460361"
---
# <a name="datepicker"></a>DatePicker
<xref:System.Windows.Controls.DatePicker> 컨트롤을 사용 하면 사용자가 텍스트 필드에 입력 하거나 드롭다운 <xref:System.Windows.Controls.Calendar> 컨트롤을 사용 하 여 날짜를 선택할 수 있습니다.  
  
 다음 그림에서는 <xref:System.Windows.Controls.DatePicker>을 보여 줍니다.  
  
 ![DatePicker 컨트롤](./media/ndp-datepicker.png "NDP_DatePicker")  
DatePicker 컨트롤  
  
 대부분의 <xref:System.Windows.Controls.DatePicker> 컨트롤 속성은 기본 제공 <xref:System.Windows.Controls.Calendar>를 관리 하 고 <xref:System.Windows.Controls.Calendar>의 해당 속성과 동일 하 게 작동 합니다. 특히 <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>및 <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> 속성은 해당 <xref:System.Windows.Controls.Calendar> 대응 함수와 동일 하 게 작동 합니다. 자세한 내용은 <xref:System.Windows.Controls.Calendar>을 참조하십시오.  
  
 사용자는 <xref:System.Windows.Controls.DatePicker.Text%2A> 속성을 설정 하는 텍스트 필드에 직접 날짜를 입력할 수 있습니다. <xref:System.Windows.Controls.DatePicker> 입력 한 문자열을 유효한 날짜로 변환할 수 없는 경우 <xref:System.Windows.Controls.DatePicker.DateValidationError> 이벤트가 발생 합니다. 기본적으로이로 인해 예외가 발생 하지만 <xref:System.Windows.Controls.DatePicker.DateValidationError>에 대 한 이벤트 처리기에서 <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> 속성을 `false` 하 여 예외가 발생 하지 않도록 설정할 수 있습니다.  
  
## <a name="see-also"></a>참조

- [컨트롤](index.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
