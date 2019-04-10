---
title: '방법: 바인딩 방향 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 4334ed178e7f2ed90928db6b434eb8c9fee77bf7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206436"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>방법: 바인딩 방향 지정
이 예제에서는 바인딩으로 바인딩 대상(대상) 속성만 업데이트되는지, 바인딩 소스(소스) 속성만 업데이트되는지 아니면 대상 속성과 소스 속성이 모두 업데이트되는지 여부를 지정하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 사용 된 <xref:System.Windows.Data.Binding.Mode%2A> 바인딩 방향을 지정 하는 속성입니다. 다음 열거 목록에서는 바인딩 업데이트에 사용할 수 있는 옵션을 보여 줍니다.  
  
-   <xref:System.Windows.Data.BindingMode.TwoWay> 대상 속성 또는 소스 속성이 변경 될 때마다 대상 속성이 나 속성을 업데이트 합니다.  
  
-   <xref:System.Windows.Data.BindingMode.OneWay> source 속성을 변경 하는 경우에 대상 속성을 업데이트 합니다.  
  
-   <xref:System.Windows.Data.BindingMode.OneTime> 응용 프로그램을 시작 하는 경우에 되거나 대상 속성을 업데이트 합니다 <xref:System.Windows.FrameworkElement.DataContext%2A> 가 변경 합니다.  
  
-   <xref:System.Windows.Data.BindingMode.OneWayToSource> 대상 속성이 변경 되 면 소스 속성을 업데이트 합니다.  
  
-   <xref:System.Windows.Data.BindingMode.Default> 그러면 기본 <xref:System.Windows.Data.Binding.Mode%2A> 사용할 대상 속성의 값입니다.  
  
 자세한 내용은 <xref:System.Windows.Data.BindingMode> 열거형을 참조하세요.  
  
 다음 예제에서는 <xref:System.Windows.Data.Binding.Mode%2A> 속성을 설정하는 방법을 보여 줍니다.  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 소스 변경 내용을 검색 하려면 (적용할 <xref:System.Windows.Data.BindingMode.OneWay> 하 고 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩), 소스와 같은 적절 한 속성 변경 알림 메커니즘을 구현 해야 합니다 <xref:System.ComponentModel.INotifyPropertyChanged>. 참조 [속성 변경 알림 구현](how-to-implement-property-change-notification.md) 의 예는 <xref:System.ComponentModel.INotifyPropertyChanged> 구현 합니다.  
  
 에 대 한 <xref:System.Windows.Data.BindingMode.TwoWay> 또는 <xref:System.Windows.Data.BindingMode.OneWayToSource> 바인딩을 설정 하 여 소스 업데이트의 타이밍을 제어할 수는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성입니다. 자세한 내용은 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>를 참조하세요.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Data.Binding>
- [데이터 바인딩 개요](data-binding-overview.md)
- [방법 항목](data-binding-how-to-topics.md)
