---
title: '방법: 속성 변경 알림 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- notifications of change [WPF]
- data binding [WPF], property change notifications
- change notifications [WPF]
- properties [WPF], change notifications
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
ms.openlocfilehash: 4f9ff49a443577e119b0c1079abbe23bd7ede4c4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459750"
---
# <a name="how-to-implement-property-change-notification"></a>방법: 속성 변경 알림 구현
바인딩 대상 속성에서 바인딩 소스의 동적 변경 내용을 자동으로 반영 하도록 <xref:System.Windows.Data.BindingMode.OneWay> 또는 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩을 지원 하려면 (예를 들어 사용자가 양식을 편집할 때 미리 보기 창이 자동으로 업데이트 되도록 하려면) 클래스는 다음을 포함 해야 합니다. 적절 한 속성 변경 알림을 제공 합니다. 이 예제에서는 <xref:System.ComponentModel.INotifyPropertyChanged>를 구현 하는 클래스를 만드는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 <xref:System.ComponentModel.INotifyPropertyChanged>를 구현 하려면 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 이벤트를 선언 하 고 `OnPropertyChanged` 메서드를 만들어야 합니다. 그런 다음 변경 알림이 필요한 각 속성이 업데이트될 때마다 `OnPropertyChanged`를 호출합니다.  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 `Person` 클래스를 사용 하 여 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩을 지 원하는 방법에 대 한 예제를 보려면 [TextBox 텍스트가 소스를 업데이트 하는 시점 제어](how-to-control-when-the-textbox-text-updates-the-source.md)를 참조 하세요.  
  
## <a name="see-also"></a>참조

- [바인딩 소스 개요](binding-sources-overview.md)
- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [방법 항목](data-binding-how-to-topics.md)
