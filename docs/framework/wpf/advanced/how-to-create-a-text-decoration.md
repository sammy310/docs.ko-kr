---
title: '방법: 텍스트 장식 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], baseline
- text [WPF], decorations
- fonts [WPF], underline
- fonts [WPF], overline
- strikethrough type [WPF]
- fonts [WPF], strikethrough
- overline type [WPF]
- underline type [WPF]
- typography [WPF], text decorations
- baseline type [WPF]
ms.assetid: cf3cb4e7-782a-4be7-b2d4-e0935e21e4e0
ms.openlocfilehash: cf3b3c3bcb75153a0be4f7ced03b38134b79a930
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185929"
---
# <a name="how-to-create-a-text-decoration"></a>방법: 텍스트 장식 만들기
<xref:System.Windows.TextDecoration> 개체가 시각적 장식 텍스트를 추가할 수 있습니다. 텍스트 장식의 네 가지가: 밑줄, 기준, 취소선 및 윗줄 합니다. 다음 예제에서는 텍스트를 기준으로 텍스트 장식의 위치를 보여 줍니다.  
  
 ![텍스트 장식 유형 다이어그램](./media/how-to-create-a-text-decoration/text-decoration-types.gif)  
  
 텍스트에 텍스트 장식을 추가하려면 <xref:System.Windows.TextDecoration> 개체를 만들고 해당 속성을 수정합니다. 속성을 <xref:System.Windows.TextDecoration.Location%2A> 사용하여 밑줄과 같은 텍스트 장식이 나타나는 위치를 지정합니다. 속성을 <xref:System.Windows.TextDecoration.Pen%2A> 사용하여 단색 채우기 또는 그라데이션 색상과 같은 텍스트 장식의 모양을 지정합니다. <xref:System.Windows.TextDecoration.Pen%2A> 속성에 대한 값을 지정하지 않으면 장식기본값이 텍스트와 동일한 색상으로 설정됩니다. 객체를 <xref:System.Windows.TextDecoration> 정의한 후에는 원하는 <xref:System.Windows.TextDecorations> 텍스트 개체의 컬렉션에 객체를 추가합니다.  
  
 다음 예제에서는 파선된 펜 선형 그라데이션 브러시와 스타일이 지정 된 텍스트 장식을 보여 줍니다.  
  
 ![선형 그라데이션 밑줄로 텍스트 장식](./media/how-to-create-a-text-decoration/text-decoration-gradient.png)  
  
 개체는 <xref:System.Windows.Documents.Hyperlink> 흐름 콘텐츠 내에서 하이퍼링크를 호스트할 수 있는 인라인 수준 흐름 콘텐츠 요소입니다. 기본적으로 <xref:System.Windows.Documents.Hyperlink> 사용을 <xref:System.Windows.TextDecoration> 밑줄을 표시 하는 개체입니다. <xref:System.Windows.TextDecoration> 많을 경우에 특히 개체를 인스턴스화할 때 성능이 저하 될 수 있습니다 <xref:System.Windows.Documents.Hyperlink> 개체입니다. <xref:System.Windows.Documents.Hyperlink> 요소를 광범위하게 사용하는 경우 <xref:System.Windows.ContentElement.MouseEnter> 이벤트와 같은 이벤트를 트리거할 때만 밑줄을 표시하는 것이 좋습니다.  
  
 다음 예제에서는 "내 MSN" 링크의 밑줄이 동적이며 <xref:System.Windows.ContentElement.MouseEnter> 이벤트가 트리거될 때만 나타납니다.  
  
 ![TextDecoration을 표시하는 하이퍼링크](./media/how-to-create-a-text-decoration/text-decorations-hyperlinks.png)  

 자세한 내용은 [하이퍼링크에 밑줄이 그어지는지 여부 지정](how-to-specify-whether-a-hyperlink-is-underlined.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서 밑줄 텍스트 장식은 기본 글꼴 값을 사용합니다.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 다음 코드 예제에서는 펜에 대한 단색 브러시로 밑줄 텍스트 장식이 만들어집니다.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 다음 코드 예제에서 밑줄 텍스트 장식은 파선된 펜에 대 한 선형 그라데이션 브러시를 사용 하 여 만들어집니다.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [하이퍼링크에 밑줄을 표시할지 여부 지정](how-to-specify-whether-a-hyperlink-is-underlined.md)
