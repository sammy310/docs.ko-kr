---
title: '방법: TextBox에서 텍스트가 변경되는 시점 감지'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 1adadb0f071815930d34f40ddf244ffc8c19131b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000976"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a>방법: TextBox에서 텍스트가 변경되는 시점 감지
이 예제에 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 메서드를 실행 하는 이벤트 때마다의 텍스트를 <xref:System.Windows.Controls.TextBox> 컨트롤이 변경 된 합니다.  
  
 코드 숨김 클래스에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 포함 하는 합니다 <xref:System.Windows.Controls.TextBox> 변경에 대 한 모니터링 하려는 컨트롤 삽입 될 때마다 호출할 메서드를를 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 이벤트가 발생 합니다.  이 메서드는에서 예상한 일치 하는 서명이 있어야 합니다.는 <xref:System.Windows.Controls.TextChangedEventHandler> 위임 합니다.  
  
 이벤트 처리기가 호출 될 때마다 내용의 <xref:System.Windows.Controls.TextBox> 사용자 또는 프로그래밍 방식으로 제어 됩니다 변경 합니다.  
  
 **참고:** 이 이벤트를 발생 하는 경우는 <xref:System.Windows.Controls.TextBox> 제어를 만들고 텍스트를 사용 하 여 처음에 채웁니다.  
  
## <a name="example"></a>예제  
 에 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 정의 하는 프로그램 <xref:System.Windows.Controls.TextBox> 컨트롤을 지정를 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 이벤트 처리기 메서드 이름이 일치 하는 값을 사용 하 여 특성.  
  
 [!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]  
  
## <a name="example"></a>예제  
 코드 숨김 클래스에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 포함 하는 합니다 <xref:System.Windows.Controls.TextBox> 변경에 대 한 모니터링 하려는 컨트롤 삽입 될 때마다 호출할 메서드를를 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 이벤트가 발생 합니다.  이 메서드는에서 예상한 일치 하는 서명이 있어야 합니다.는 <xref:System.Windows.Controls.TextChangedEventHandler> 위임 합니다.  
  
 [!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
 [!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]  
  
 이벤트 처리기가 호출 될 때마다 내용의 <xref:System.Windows.Controls.TextBox> 사용자 또는 프로그래밍 방식으로 제어 됩니다 변경 합니다.  
  
 **참고:** 이 이벤트를 발생 하는 경우는 <xref:System.Windows.Controls.TextBox> 제어를 만들고 텍스트를 사용 하 여 처음에 채웁니다.  
  
 설명  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Controls.TextChangedEventArgs>
- [TextBox 개요](textbox-overview.md)
- [RichTextBox 개요](richtextbox-overview.md)
