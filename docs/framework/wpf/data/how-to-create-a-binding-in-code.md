---
title: '방법: 코드에서 바인딩 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: 616487a16ebbe6e23fe067fb7ce72644aa3f919f
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458853"
---
# <a name="how-to-create-a-binding-in-code"></a>방법: 코드에서 바인딩 만들기
이 예제에서는 코드에서 <xref:System.Windows.Data.Binding>를 만들고 설정 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 <xref:System.Windows.FrameworkElement> 클래스와 <xref:System.Windows.FrameworkContentElement> 클래스는 모두 `SetBinding` 메서드를 노출 합니다. 이러한 클래스 중 하나를 상속 하는 요소를 바인딩하는 경우 <xref:System.Windows.FrameworkElement.SetBinding%2A> 메서드를 직접 호출할 수 있습니다.  
  
 다음 예제에서는 `MyDataProperty`라는 속성을 포함 하는 `MyData`이라는 클래스를 만듭니다.  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 다음 예제에서는 바인딩 개체를 만들어 바인딩의 원본을 설정 하는 방법을 보여 줍니다.  이 예제에서는 <xref:System.Windows.FrameworkElement.SetBinding%2A>를 사용 하 여 <xref:System.Windows.Controls.TextBlock> 컨트롤인 `myText`의 <xref:System.Windows.Controls.TextBlock.Text%2A> 속성을 `MyDataProperty`에 바인딩합니다.  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 전체 코드 샘플은 [코드 전용 바인딩 샘플](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90))을 참조 하세요.  
  
 <xref:System.Windows.FrameworkElement.SetBinding%2A>를 호출 하는 대신 <xref:System.Windows.Data.BindingOperations> 클래스의 <xref:System.Windows.Data.BindingOperations.SetBinding%2A> 정적 메서드를 사용할 수 있습니다. 다음 예에서는 <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> 대신 <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType>를 호출 하 여 `myText`를 `myDataProperty`에 바인딩합니다.  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a>참조

- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [방법 항목](data-binding-how-to-topics.md)
