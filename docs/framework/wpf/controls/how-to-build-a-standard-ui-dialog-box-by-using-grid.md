---
title: '방법: Grid를 사용하여 표준 UI 대화 상자 빌드'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: 57edaa173b85bc06c6859b08d3edec281e1b8942
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372862"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a>방법: Grid를 사용하여 표준 UI 대화 상자 빌드
이 예제에는 표준을 만드는 방법을 보여 줍니다 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 를 사용 하 여 대화 상자는 <xref:System.Windows.Controls.Grid> 요소입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 같은 대화 상자가 합니다 **실행** 대화 상자는 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 운영 체제입니다.  
  
 만듭니다는 <xref:System.Windows.Controls.Grid> 사용 하는 <xref:System.Windows.Controls.ColumnDefinition> 및 <xref:System.Windows.Controls.RowDefinition> 다섯 개의 열 / 행 4 개를 정의 하는 클래스입니다.  
  
 이 예제에서 다음 추가 하 고 배치를 <xref:System.Windows.Controls.Image>, `RunIcon.png`, 대화 상자에 있는 이미지를 나타내는입니다. 첫 번째 열과 행에는 이미지가 <xref:System.Windows.Controls.Grid> (왼쪽 위 모서리).  
  
 이 예제에서는 추가 하는 다음으로 <xref:System.Windows.Controls.TextBlock> 첫 번째 행의 나머지 열을 포함 하는 첫 번째 열에 요소입니다. 다른 추가 <xref:System.Windows.Controls.TextBlock> 요소를 나타내는 첫 번째 열에서 두 번째 행에는 **오픈** 입력란입니다. <xref:System.Windows.Controls.TextBlock> 데이터 항목 영역을 나타내는 다음과 같습니다.  
  
 마지막으로,이 예제에서는 추가 세 <xref:System.Windows.Controls.Button> 마지막 행을 나타내는 요소를 **확인**를 **취소**, 및 **찾아보기** 이벤트입니다.  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [패널 개요](panels-overview.md)
- [방법 항목](grid-how-to-topics.md)
