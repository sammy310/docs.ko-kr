---
title: '방법: TextBox 컨트롤의 텍스트 내용 설정'
description: 텍스트 속성을 사용 하 여 Windows Presentation Foundation TextBox 컨트롤의 초기 텍스트 콘텐츠를 설정 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: 41efb69e297b3c6fdb1203c358dcc72d7a9f806f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168041"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a>방법: TextBox 컨트롤의 텍스트 내용 설정

이 예제에서는 속성을 사용 하 여 <xref:System.Windows.Controls.TextBox.Text%2A> 컨트롤의 초기 텍스트 콘텐츠를 설정 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.TextBox> .

> [!NOTE]
> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]이 예제의 버전에서는 `<TextBox.Text>` 각 단추의 콘텐츠 텍스트 주위에 있는 태그를 사용할 수 있지만에서는 <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBox> 속성에 특성을 적용 하기 때문에 필요 하지 않습니다 <xref:System.Windows.Markup.ContentPropertyAttribute> <xref:System.Windows.Controls.TextBox.Text%2A> . 자세한 내용은 [XAML 개요 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)를 참조 하세요.

## <a name="example"></a>예제

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a>예제

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a>참고 항목

- [TextBox 개요](textbox-overview.md)
- [RichTextBox 개요](richtextbox-overview.md)
