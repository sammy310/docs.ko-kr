---
title: '방법: 열거형 바인딩'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: 93f33e497fd7acb81c55f86bf38737d4e7d79bf2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454445"
---
# <a name="how-to-bind-to-an-enumeration"></a>방법: 열거형 바인딩
이 예제에서는 열거형의 GetValues 메서드에 바인딩하여 열거형에 바인딩하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예제에서 <xref:System.Windows.Controls.ListBox>는 데이터 바인딩을 통해 <xref:System.Windows.HorizontalAlignment> 열거 값의 목록을 표시 합니다. <xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.Button>는 <xref:System.Windows.Controls.ListBox>에서 값을 선택 하 여 <xref:System.Windows.Controls.Button>의 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성 값을 변경할 수 있도록 바인딩됩니다.  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a>참조

- [메서드 바인딩](how-to-bind-to-a-method.md)
- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [방법 항목](data-binding-how-to-topics.md)
