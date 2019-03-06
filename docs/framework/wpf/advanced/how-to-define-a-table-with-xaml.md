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
# <a name="how-to-define-a-table-with-xaml"></a><span data-ttu-id="21c78-102">방법: XAML로 표 정의</span><span class="sxs-lookup"><span data-stu-id="21c78-102">How to: Define a Table with XAML</span></span>
<span data-ttu-id="21c78-103">다음 예제에서는 정의 하는 방법에 설명 된 <xref:System.Windows.Documents.Table> 를 사용 하 여 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]입니다.</span><span class="sxs-lookup"><span data-stu-id="21c78-103">The following example demonstrates how to define a <xref:System.Windows.Documents.Table> using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  <span data-ttu-id="21c78-104">예제 테이블에는 네 개의 열 (나타낸 <xref:System.Windows.Documents.TableColumn> 요소)과 여러 개의 행 (나타내는 <xref:System.Windows.Documents.TableRow> 요소) 데이터도 포함 된 제목, 머리글 및 바닥글 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="21c78-104">The example table has four columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and several rows (represented by <xref:System.Windows.Documents.TableRow> elements) containing data as well as title, header, and footer information.</span></span>  <span data-ttu-id="21c78-105">행에 포함 되어야 합니다는 <xref:System.Windows.Documents.TableRowGroup> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="21c78-105">Rows must be contained in a <xref:System.Windows.Documents.TableRowGroup> element.</span></span>  <span data-ttu-id="21c78-106">표의 각 행은 하나 이상의 셀 구성 (나타내는 <xref:System.Windows.Documents.TableCell> 요소).</span><span class="sxs-lookup"><span data-stu-id="21c78-106">Each row in the table is comprised of one or more cells (represented by <xref:System.Windows.Documents.TableCell> elements).</span></span>  <span data-ttu-id="21c78-107">테이블 셀의 내용에 포함 되어야 합니다는 <xref:System.Windows.Documents.Block> 요소, 여기서 <xref:System.Windows.Documents.Paragraph> 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="21c78-107">Content in a table cell must be contained in a <xref:System.Windows.Documents.Block> element; in this case <xref:System.Windows.Documents.Paragraph> elements are used.</span></span>  <span data-ttu-id="21c78-108">테이블에 하이퍼링크도 호스트 (나타내는 <xref:System.Windows.Documents.Hyperlink> 요소) 바닥글 행에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21c78-108">The table also hosts a hyperlink (represented by the <xref:System.Windows.Documents.Hyperlink> element) in the footer row.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21c78-109">예제</span><span class="sxs-lookup"><span data-stu-id="21c78-109">Example</span></span>  
 [!code-xaml[TableSnippetsXAML#_TableXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 <span data-ttu-id="21c78-110">다음 그림에서는 이 예제에 정의된 테이블이 렌더링되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="21c78-110">The following figure shows how the table defined in this example renders.</span></span>  
  
 <span data-ttu-id="21c78-111">![렌더링된 테이블.](./media/tableeg.png "TableEG")</span><span class="sxs-lookup"><span data-stu-id="21c78-111">![Rendered table.](./media/tableeg.png "TableEG")</span></span>
