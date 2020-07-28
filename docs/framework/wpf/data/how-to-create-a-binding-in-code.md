---
title: '방법: 코드에서 바인딩 만들기'
description: SetBinding 메서드를 직접 호출 하 여 Windows Presentation Foundation 응용 프로그램의 코드에서 바인딩을 만드는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: aa2a29f4c1262d8ac54641b856c297b284b23a38
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165806"
---
# <a name="how-to-create-a-binding-in-code"></a>방법: 코드에서 바인딩 만들기
이 예제에서는 코드에서을 만들고 설정 하는 방법을 보여 줍니다 <xref:System.Windows.Data.Binding> .  
  
## <a name="example"></a>예제  
 <xref:System.Windows.FrameworkElement>클래스와 클래스는 <xref:System.Windows.FrameworkContentElement> 모두 메서드를 노출 합니다 `SetBinding` . 이러한 클래스 중 하나를 상속 하는 요소를 바인딩하는 경우 메서드를 직접 호출할 수 있습니다 <xref:System.Windows.FrameworkElement.SetBinding%2A> .  
  
 다음 예제에서는 라는 속성을 포함 하는 라는 클래스를 만듭니다 `MyData` `MyDataProperty` .  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 다음 예제에서는 바인딩 개체를 만들어 바인딩의 원본을 설정 하는 방법을 보여 줍니다.  이 예제에서는를 사용 하 여 <xref:System.Windows.FrameworkElement.SetBinding%2A> <xref:System.Windows.Controls.TextBlock.Text%2A> 컨트롤인의 속성을 `myText` <xref:System.Windows.Controls.TextBlock> 에 바인딩합니다 `MyDataProperty` .  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 전체 코드 샘플은 [코드 전용 바인딩 샘플](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90))을 참조 하세요.  
  
 를 호출 하는 대신 <xref:System.Windows.FrameworkElement.SetBinding%2A> <xref:System.Windows.Data.BindingOperations.SetBinding%2A> 클래스의 정적 메서드를 사용할 수 있습니다 <xref:System.Windows.Data.BindingOperations> . 다음 예제에서는 대신를 호출 하 여 <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> `myText` 에 바인딩합니다 `myDataProperty` .  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a>참조

- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [방법 항목](data-binding-how-to-topics.md)
