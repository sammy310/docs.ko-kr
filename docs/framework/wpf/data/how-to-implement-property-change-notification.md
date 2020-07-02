---
title: '방법: 속성 변경 알림 구현'
description: Windows Presentation Foundation (WPF)에서 속성 값이 변경 될 때 자동으로 바인딩 소스에 알리도록 속성을 설정 합니다.
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
ms.openlocfilehash: 6c298930b7b1f812e94ea6add8f53c67d3453530
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620783"
---
# <a name="how-to-implement-property-change-notification"></a>방법: 속성 변경 알림 구현
바인딩 <xref:System.Windows.Data.BindingMode.OneWay> <xref:System.Windows.Data.BindingMode.TwoWay> 대상 속성에서 바인딩 소스의 동적 변경 내용을 자동으로 반영 하도록 지원 하거나 바인딩하려면 (예: 사용자가 폼을 편집할 때 미리 보기 창이 자동으로 업데이트 되도록) 클래스에서 적절 한 속성 변경 알림을 제공 해야 합니다. 이 예제에서는를 구현 하는 클래스를 만드는 방법을 보여 줍니다 <xref:System.ComponentModel.INotifyPropertyChanged> .  
  
## <a name="example"></a>예제  
 을 구현 하려면 <xref:System.ComponentModel.INotifyPropertyChanged> 이벤트를 선언 하 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 고 메서드를 만들어야 `OnPropertyChanged` 합니다. 그런 다음 변경 알림이 필요한 각 속성이 업데이트될 때마다 `OnPropertyChanged`를 호출합니다.  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 클래스를 사용 하 여 바인딩을 지 원하는 방법에 대 한 예제를 보려면 `Person` <xref:System.Windows.Data.BindingMode.TwoWay> [TextBox 텍스트가 소스를 업데이트 하는 시점 제어](how-to-control-when-the-textbox-text-updates-the-source.md)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [바인딩 소스 개요](binding-sources-overview.md)
- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [방법 도움말 항목](data-binding-how-to-topics.md)
