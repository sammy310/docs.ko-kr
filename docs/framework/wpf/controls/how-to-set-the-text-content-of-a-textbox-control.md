---
title: '방법: TextBox 컨트롤의 텍스트 내용 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: da91e27b804d649f5b8010bc9d7c074425be26f6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212195"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a>방법: TextBox 컨트롤의 텍스트 내용 설정
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.TextBox.Text%2A> 초기 텍스트 콘텐츠를 설정 하는 속성을 <xref:System.Windows.Controls.TextBox> 제어 합니다.  
  
 **참고** 있지만 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 버전의 예제를 사용할 수는 `<TextBox.Text>` 태그의 각 단추의 텍스트를 둘러싸는 <xref:System.Windows.Controls.TextBox> 콘텐츠 필요는 없습니다 때문에 <xref:System.Windows.Controls.TextBox> 적용 됩니다는 <xref:System.Windows.Markup.ContentPropertyAttribute> 특성을 <xref:System.Windows.Controls.TextBox.Text%2A> 속성입니다. 자세한 내용은 [XAML 개요 (WPF)](../advanced/xaml-overview-wpf.md)합니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]  
  
## <a name="example"></a>예제  
 [!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
 [!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]  
  
## <a name="see-also"></a>참고자료

- [TextBox 개요](textbox-overview.md)
- [RichTextBox 개요](richtextbox-overview.md)
