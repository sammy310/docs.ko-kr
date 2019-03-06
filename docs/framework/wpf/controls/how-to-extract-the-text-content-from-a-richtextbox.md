---
title: '방법: RichTextBox에서 텍스트 콘텐츠 추출'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], extracting
- RichTextBox control [WPF], extracting text content
- content [WPF], extracting
- extracting text content [WPF]
ms.assetid: f13c093f-1a05-45b3-ac8f-c9ea5e4a11c5
ms.openlocfilehash: 8c7fd54931fad060a5d78e4c47c2cfce2767025a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355248"
---
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a><span data-ttu-id="4cf25-102">방법: RichTextBox에서 텍스트 콘텐츠 추출</span><span class="sxs-lookup"><span data-stu-id="4cf25-102">How to: Extract the Text Content from a RichTextBox</span></span>
<span data-ttu-id="4cf25-103">콘텐츠를 추출 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.RichTextBox> 일반 텍스트로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf25-103">This example shows how to extract the contents of a <xref:System.Windows.Controls.RichTextBox> as plain text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cf25-104">예제</span><span class="sxs-lookup"><span data-stu-id="4cf25-104">Example</span></span>  
 <span data-ttu-id="4cf25-105">다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 명명 된 코드에 설명 <xref:System.Windows.Controls.RichTextBox> 단순 콘텐츠를 사용 하 여 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf25-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a><span data-ttu-id="4cf25-106">예제</span><span class="sxs-lookup"><span data-stu-id="4cf25-106">Example</span></span>  
 <span data-ttu-id="4cf25-107">다음 코드를 사용 하는 메서드를 구현 하는 <xref:System.Windows.Controls.RichTextBox> 인수로 일반 텍스트 콘텐츠를 나타내는 문자열을 반환 하 고는 <xref:System.Windows.Controls.RichTextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf25-107">The following code implements a method that takes a <xref:System.Windows.Controls.RichTextBox> as an argument, and returns a string representing the plain text contents of the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="4cf25-108">메서드를 만듭니다 <xref:System.Windows.Documents.TextRange> 의 콘텐츠에서 합니다 <xref:System.Windows.Controls.RichTextBox>를 사용 하 여는 <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> 및 <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> 추출 콘텐츠의 범위를 지정 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf25-108">The method creates a new <xref:System.Windows.Documents.TextRange> from the contents of the <xref:System.Windows.Controls.RichTextBox>, using the <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> and <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> to indicate the range of the contents to extract.</span></span>  <span data-ttu-id="4cf25-109"><xref:System.Windows.Documents.FlowDocument.ContentStart%2A> 및 <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> 속성에는 각각 반환을 <xref:System.Windows.Documents.TextPointer>의 콘텐츠를 나타내는 기본 FlowDocument에 액세스할 수는 <xref:System.Windows.Controls.RichTextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf25-109"><xref:System.Windows.Documents.FlowDocument.ContentStart%2A> and <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> properties each return a <xref:System.Windows.Documents.TextPointer>, and are accessible on the underlying FlowDocument that represents the contents of the <xref:System.Windows.Controls.RichTextBox>.</span></span>  <span data-ttu-id="4cf25-110"><xref:System.Windows.Documents.TextRange> 일반 텍스트 부분을 반환 하는 텍스트 속성을 제공 합니다 <xref:System.Windows.Documents.TextRange> 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4cf25-110"><xref:System.Windows.Documents.TextRange> provides a Text property, which returns the plain text portions of the <xref:System.Windows.Documents.TextRange> as a string.</span></span>  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a><span data-ttu-id="4cf25-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="4cf25-111">See also</span></span>
- [<span data-ttu-id="4cf25-112">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="4cf25-112">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="4cf25-113">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="4cf25-113">TextBox Overview</span></span>](textbox-overview.md)
