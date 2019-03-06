---
title: '방법: FlowDocument 열 구분 속성 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- FlowDocument column-separating attributes
- column-separating attributes
- documents [WPF], FlowDocument column-separating attributes
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
ms.openlocfilehash: 8693c8973442a5c6e65e64c5c66194c11bbff119
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363785"
---
# <a name="how-to-use-flowdocument-column-separating-attributes"></a><span data-ttu-id="704fa-102">방법: FlowDocument 열 구분 속성 사용</span><span class="sxs-lookup"><span data-stu-id="704fa-102">How to: Use FlowDocument Column-Separating Attributes</span></span>
<span data-ttu-id="704fa-103">열 구분 기능을 사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Documents.FlowDocument>합니다.</span><span class="sxs-lookup"><span data-stu-id="704fa-103">This example shows how to use the column-separating features of a <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="704fa-104">예제</span><span class="sxs-lookup"><span data-stu-id="704fa-104">Example</span></span>  
 <span data-ttu-id="704fa-105">다음 예제에서는 정의 <xref:System.Windows.Documents.FlowDocument>를 설정 합니다 <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, 및 <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> 특성.</span><span class="sxs-lookup"><span data-stu-id="704fa-105">The following example defines a <xref:System.Windows.Documents.FlowDocument>, and sets the <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, and <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributes.</span></span>  <span data-ttu-id="704fa-106"><xref:System.Windows.Documents.FlowDocument> 단일 단락 샘플 콘텐츠를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="704fa-106">The <xref:System.Windows.Documents.FlowDocument> contains a single paragraph of sample content.</span></span>  
  
 [!code-xaml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 <span data-ttu-id="704fa-107">다음 그림의 효과 보여 줍니다.는 <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, 및 <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> 렌더링된 된 특성 <xref:System.Windows.Documents.FlowDocument>합니다.</span><span class="sxs-lookup"><span data-stu-id="704fa-107">The following figure shows the effects of the <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, and <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributes in a rendered <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 <span data-ttu-id="704fa-108">![스크린 샷: FlowDocument 내부 열](./media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")</span><span class="sxs-lookup"><span data-stu-id="704fa-108">![Screenshot: FlowDocument Intra Column](./media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")</span></span>
