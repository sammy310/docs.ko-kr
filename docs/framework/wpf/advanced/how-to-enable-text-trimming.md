---
title: '방법: 텍스트 잘라내기 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], trimming
- documents [WPF], trimming text
- trimming text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
ms.openlocfilehash: 25fff566868e792004a915fee195485c4a1f385f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776130"
---
# <a name="how-to-enable-text-trimming"></a><span data-ttu-id="7b285-102">방법: 텍스트 잘라내기 사용</span><span class="sxs-lookup"><span data-stu-id="7b285-102">How to: Enable Text Trimming</span></span>

<span data-ttu-id="7b285-103">사용 및 사용 가능한 값의 효과 보여 주는이 예제는 <xref:System.Windows.TextTrimming> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="7b285-103">This example demonstrates the usage and effects of the values available in the <xref:System.Windows.TextTrimming> enumeration.</span></span>

## <a name="example"></a><span data-ttu-id="7b285-104">예제</span><span class="sxs-lookup"><span data-stu-id="7b285-104">Example</span></span>

<span data-ttu-id="7b285-105">다음 예제에서는 정의 <xref:System.Windows.Controls.TextBlock> 요소는 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 특성이 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b285-105">The following example defines a <xref:System.Windows.Controls.TextBlock> element with the <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> attribute set.</span></span>

[!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]

<span data-ttu-id="7b285-106">해당 설정 <xref:System.Windows.TextTrimming> 코드에서 속성은 아래에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b285-106">Setting the corresponding <xref:System.Windows.TextTrimming> property in code is demonstrated below.</span></span>

[!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
[!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]

<span data-ttu-id="7b285-107">현재 세 가지 방법으로 텍스트 잘라내기에 있습니다. **CharacterEllipsis**하십시오 **WordEllipsis**, 및 **None**합니다.</span><span class="sxs-lookup"><span data-stu-id="7b285-107">There are currently three options for trimming text: **CharacterEllipsis**, **WordEllipsis**, and **None**.</span></span>

<span data-ttu-id="7b285-108">때 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 로 설정 된 **CharacterEllipsis**, 텍스트는 잘리고 잘리는 가장자리에서 가장 가까운 문자에 줄임표가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b285-108">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **CharacterEllipsis**, text is trimmed and continued with an ellipsis at the character closest to the trimming edge.</span></span>  <span data-ttu-id="7b285-109">이 설정은 잘리는 경계에 좀 더 가깝게 맞추어 텍스트를 잘라내기 때문에 단어가 부분적으로 잘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b285-109">This setting tends to trim text to fit more closely to the trimming boundary, but may result in words being partially trimmed.</span></span>  <span data-ttu-id="7b285-110">다음 그림에서이 설정의 효과 <xref:System.Windows.Controls.TextBlock> 위에 정의 된 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="7b285-110">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>

<span data-ttu-id="7b285-111">![예제: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span><span class="sxs-lookup"><span data-stu-id="7b285-111">![Example: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span></span>

<span data-ttu-id="7b285-112">때 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 로 설정 된 **WordEllipsis**, 텍스트는 잘리고 잘리는 가장자리에서 가장 가까운 첫 번째 전체 단어 끝에 줄임표가 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b285-112">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **WordEllipsis**, text is trimmed and continued with an ellipsis at the end of the first full word closest to the trimming edge.</span></span>  <span data-ttu-id="7b285-113">이 설정은 부분적으로 잘라낸된 단어를 표시 하지 것입니다 하지만 잘라낸 가장자리와 가깝게 텍스트 트리밍 필요가 합니다 **CharacterEllipsis** 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b285-113">This setting will not show partially trimmed words, but tends not to trim text as closely to the trimming edge as the **CharacterEllipsis** setting.</span></span>  <span data-ttu-id="7b285-114">다음 그림에서이 설정의 효과 <xref:System.Windows.Controls.TextBlock> 위에 정의 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b285-114">The following figure shows the effect of this setting on the <xref:System.Windows.Controls.TextBlock> defined above.</span></span>

<span data-ttu-id="7b285-115">![예제: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span><span class="sxs-lookup"><span data-stu-id="7b285-115">![Example: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span></span>

<span data-ttu-id="7b285-116">때 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 로 설정 된 **없음**, 없는 텍스트 잘라내기 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b285-116">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **None**, no text trimming is performed.</span></span>  <span data-ttu-id="7b285-117">이 경우 텍스트가 부모 텍스트 컨테이너의 경계로 잘릴 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="7b285-117">In this case, text is simply cropped to the boundary of the parent text container.</span></span>  <span data-ttu-id="7b285-118">다음 그림에서이 설정의 효과 <xref:System.Windows.Controls.TextBlock> 위에 정의 된 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="7b285-118">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>

<span data-ttu-id="7b285-119">![예제: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span><span class="sxs-lookup"><span data-stu-id="7b285-119">![Example: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span></span>
