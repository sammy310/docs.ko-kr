---
title: '방법: 텍스트 입력 체계 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting Typography attributes [WPF]
- Typography attribute [WPF], setting
ms.assetid: 19a3b49b-60a2-4c11-a786-e26b4c965588
ms.openlocfilehash: eeed93f62802a942915511db060c0e6c029579e0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365786"
---
# <a name="how-to-alter-the-typography-of-text"></a>방법: 텍스트 입력 체계 변경
다음 예제에서는 설정 하는 방법을 보여 줍니다 합니다 <xref:System.Windows.Documents.TextElement.Typography%2A> 특성을 사용 하 여 <xref:System.Windows.Documents.Paragraph> 를 예제 요소로 합니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 다음 그림은 이 예제에서 렌더링하는 방법을 보여줍니다.  
  
 ![스크린 샷: 변경 된 텍스트](./media/textelement-typog.png "TextElement_Typog")  
  
 반면 다음 그림은 기본 입력 체계 속성이 있는 비슷한 예제가 렌더링되는 방식을 보여줍니다.  
  
 ![스크린 샷: 변경 된 텍스트](./media/textelement-typog-default.png "TextElement_Typog_Default")  
  
## <a name="example"></a>예제  
 다음 예제에서는 설정 하는 방법의 <xref:System.Windows.Controls.TextBox.Typography%2A> 속성 프로그래밍 방식으로 합니다.  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
## <a name="see-also"></a>참고자료
- [유동 문서 개요](flow-document-overview.md)
