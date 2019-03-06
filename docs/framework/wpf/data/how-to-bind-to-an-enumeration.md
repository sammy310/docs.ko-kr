---
title: '방법: 열거형 바인딩'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: df26d2bd08e4691837f739a4e71d3bb1a25bdd00
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377796"
---
# <a name="how-to-bind-to-an-enumeration"></a>방법: 열거형 바인딩
이 예제에서는 열거형의 GetValues 메서드에 바인딩하여 열거형에 바인딩하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Controls.ListBox> 목록이 표시 됩니다 <xref:System.Windows.HorizontalAlignment> 데이터 바인딩을 통해 열거형 값입니다. <xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.Button> 변경할 수 있는 이러한 바인딩된를 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성 값을 <xref:System.Windows.Controls.Button> 값을 선택 하 여는 <xref:System.Windows.Controls.ListBox>.  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a>참고자료
- [메서드 바인딩](how-to-bind-to-a-method.md)
- [데이터 바인딩 개요](data-binding-overview.md)
- [방법 항목](data-binding-how-to-topics.md)
