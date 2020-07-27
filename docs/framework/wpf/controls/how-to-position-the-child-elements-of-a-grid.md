---
title: '방법: Grid의 자식 요소 위치 지정'
description: Windows Presentation Foundation 표에 정의 된 get 및 set 메서드를 사용 하 여 자식 요소를 배치 하는 방법을 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 926d223097dd21dd0292c9523903b4be8aba8ba9
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167391"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a>방법: Grid의 자식 요소 위치 지정
이 예제에서는에 정의 된 get 및 set 메서드를 사용 하 여 자식 요소를 배치 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.Grid> .  
  
## <a name="example"></a>예제  
 다음 예에서는 <xref:System.Windows.Controls.Grid> `grid1` 3 개의 열과 3 개의 행이 있는 부모 요소 ()를 정의 합니다. 자식 <xref:System.Windows.Shapes.Rectangle> 요소 ( `rect1` )가의 <xref:System.Windows.Controls.Grid> 열 위치 0, 행 위치 0에 추가 됩니다. <xref:System.Windows.Controls.Button>요소는 내에서 요소의 위치를 변경 하기 위해 호출할 수 있는 메서드를 나타냅니다 <xref:System.Windows.Shapes.Rectangle> <xref:System.Windows.Controls.Grid> . 사용자가 단추를 클릭 하면 관련 메서드가 활성화 됩니다.  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 다음 코드 예제에서는 단추 이벤트가 발생 하는 메서드를 처리 합니다 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> . 이 예제에서는 <xref:System.Windows.Controls.TextBlock> 관련 get 메서드를 사용 하 여 새 속성 값을 문자열로 출력 하는 요소에 이러한 메서드 호출을 씁니다.  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 완성 된 결과는 다음과 같습니다.

 ![스크린 샷에서는 두 개의 열이 있는 WPF 사용자 인터페이스를 보여 줍니다. 오른쪽에는 3 x 3 눈금이 있고 왼쪽에는 표의 열과 행 사이에서 색이 지정 된 사각형을 이동 하는 단추가 있습니다.](././media/grid-methods-sample.png)
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.Grid>
- [Panel 개요](panels-overview.md)
