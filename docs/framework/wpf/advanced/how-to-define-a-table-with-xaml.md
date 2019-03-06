---
title: '방법: XAML로 표 정의'
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
ms.openlocfilehash: 7398af6fddae56238e1af3ee4e726420c01ab7ea
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376925"
---
# <a name="how-to-define-a-table-with-xaml"></a>방법: XAML로 표 정의
다음 예제에서는 정의 하는 방법에 설명 된 <xref:System.Windows.Documents.Table> 를 사용 하 여 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]입니다.  예제 테이블에는 네 개의 열 (나타낸 <xref:System.Windows.Documents.TableColumn> 요소)과 여러 개의 행 (나타내는 <xref:System.Windows.Documents.TableRow> 요소) 데이터도 포함 된 제목, 머리글 및 바닥글 정보입니다.  행에 포함 되어야 합니다는 <xref:System.Windows.Documents.TableRowGroup> 요소입니다.  표의 각 행은 하나 이상의 셀 구성 (나타내는 <xref:System.Windows.Documents.TableCell> 요소).  테이블 셀의 내용에 포함 되어야 합니다는 <xref:System.Windows.Documents.Block> 요소, 여기서 <xref:System.Windows.Documents.Paragraph> 요소를 사용 합니다.  테이블에 하이퍼링크도 호스트 (나타내는 <xref:System.Windows.Documents.Hyperlink> 요소) 바닥글 행에 있습니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[TableSnippetsXAML#_TableXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 다음 그림에서는 이 예제에 정의된 테이블이 렌더링되는 방법을 보여 줍니다.  
  
 ![렌더링된 테이블.](./media/tableeg.png "TableEG")
