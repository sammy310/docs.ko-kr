---
title: '방법: ControlTemplate에서 생성된 요소 찾기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ControlTemplates [WPF], finding elements
- finding ControlTemplate elements [WPF]
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
ms.openlocfilehash: 232ee7d2859059591c9beff753f45781598a8127
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460712"
---
# <a name="how-to-find-controltemplate-generated-elements"></a>방법: ControlTemplate에서 생성된 요소 찾기
이 예제에서는 <xref:System.Windows.Controls.ControlTemplate>에서 생성 된 요소를 찾는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Controls.Button> 클래스에 대 한 간단한 <xref:System.Windows.Controls.ControlTemplate>을 만드는 스타일을 보여 줍니다.  
  
 [!code-xaml[FindGeneratedItems#CT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 템플릿이 적용 된 후 템플릿 내에서 요소를 찾으려면 <xref:System.Windows.Controls.Control.Template%2A>의 <xref:System.Windows.FrameworkTemplate.FindName%2A> 메서드를 호출 하면 됩니다. 다음 예제에서는 컨트롤 템플릿 내 <xref:System.Windows.Controls.Grid>의 실제 너비 값을 보여 주는 메시지 상자를 만듭니다.  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## <a name="see-also"></a>참조

- [DataTemplate에서 생성된 요소 찾기](../data/how-to-find-datatemplate-generated-elements.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [WPF XAML 이름 범위](../advanced/wpf-xaml-namescopes.md)
- [WPF의 트리](../advanced/trees-in-wpf.md)
