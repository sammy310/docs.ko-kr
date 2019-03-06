---
title: '방법: 시각적 요소의 그리기 콘텐츠 열거'
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 6414026090766544585c8e5e940ef9f0c62566d2
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360016"
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a>방법: 시각적 요소의 그리기 콘텐츠 열거
합니다 <xref:System.Windows.Media.Drawing> 의 콘텐츠를 열거 하는 것에 대 한 개체 모델을 제공 하는 개체는 <xref:System.Windows.Media.Visual>합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> 검색 하는 메서드를 <xref:System.Windows.Media.DrawingGroup> 값을 <xref:System.Windows.Media.Visual> 열거 합니다.  
  
> [!NOTE]
>  검색 하려는 시각적 개체의 내용을 열거 하는 경우 <xref:System.Windows.Media.Drawing> 개체 및 없습니다 기본 표시는 렌더링 데이터의 벡터 그래픽 명령 목록으로 합니다. 자세한 내용은 [WPF 그래픽 렌더링 개요](wpf-graphics-rendering-overview.md)를 참조하세요.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.VisualTreeHelper>
- [Drawing 개체 개요](drawing-objects-overview.md)
- [WPF 그래픽 렌더링 개요](wpf-graphics-rendering-overview.md)
