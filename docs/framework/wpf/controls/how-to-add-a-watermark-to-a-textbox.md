---
title: '방법: TextBox에 워터마크 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
ms.openlocfilehash: 5a2b48c6f580def98a47913c4909d0c57aca0974
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359422"
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a>방법: TextBox에 워터마크 추가
다음 예제에서는의 유용성을 <xref:System.Windows.Controls.TextBox> 내부의 설명 배경 이미지를 표시 하 여는 <xref:System.Windows.Controls.TextBox> 이미지 제거 되는 시점까지 사용자가 텍스트를 입력 합니다. 또한 사용자가 입력을 제거 하는 경우 배경 이미지가 다시 복원 됩니다. 아래 그림을 참조 하세요.  
  
 ![배경 이미지가 있는 TextBox](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")  
  
> [!NOTE]
>  배경 이미지 조작 대신 다음 단순히이 예에서 사용 되는 이유는 <xref:System.Windows.Controls.TextBox.Text%2A> 속성의 <xref:System.Windows.Controls.TextBox>는 배경 이미지를 데이터 바인딩에 방해 하지 것입니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a>참고자료
- [TextBox 개요](textbox-overview.md)
- [RichTextBox 개요](richtextbox-overview.md)
