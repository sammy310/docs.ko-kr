---
title: '방법: 상황에 맞는 메뉴로 맞춤법 검사 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling spell checking in a text box [WPF]
- reenabling spell checking in a text box [WPF]
- spell checking with a context menu [WPF]
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
ms.openlocfilehash: 38d41aa6710fd13ffd2a5d13a6900a1a05303f35
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377809"
---
# <a name="how-to-use-spell-checking-with-a-context-menu"></a><span data-ttu-id="78120-102">방법: 상황에 맞는 메뉴로 맞춤법 검사 사용</span><span class="sxs-lookup"><span data-stu-id="78120-102">How to: Use Spell Checking with a Context Menu</span></span>
<span data-ttu-id="78120-103">기본적으로 편집 컨트롤에서 맞춤법 검사를 사용 하도록 설정 하면 같은 <xref:System.Windows.Controls.TextBox> 또는 <xref:System.Windows.Controls.RichTextBox>, 맞춤법 검사 옵션이 상황에 맞는 메뉴에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="78120-103">By default, when you enable spell checking in an editing control like <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox>, you get spell-checking choices in the context menu.</span></span> <span data-ttu-id="78120-104">예를 들어 사용자가 맞춤법이 틀린된 단어를 마우스 오른쪽 단추로 받게 추천 또는 옵션 집합이 **모두 무시**합니다.</span><span class="sxs-lookup"><span data-stu-id="78120-104">For example, when users right-click a misspelled word, they get a set of spelling suggestions or the option to **Ignore All**.</span></span> <span data-ttu-id="78120-105">그러나 사용자 고유의 사용자 지정 상황에 맞는 메뉴를 사용 하 여 기본 상황에 맞는 메뉴를 재정의 하는 경우이 기능 손실 되 고 상황에 맞는 메뉴에서 맞춤법 검사 기능을 다시 사용 하도록 설정 하는 코드를 작성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78120-105">However, when you override the default context menu with your own custom context menu, this functionality is lost, and you need to write code to reenable the spell-checking feature in the context menu.</span></span> <span data-ttu-id="78120-106">다음 예제에서이 사용 하도록 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="78120-106">The following example shows how to enable this on a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78120-107">예제</span><span class="sxs-lookup"><span data-stu-id="78120-107">Example</span></span>  
 <span data-ttu-id="78120-108">다음 예제에서는 합니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 만들어지는 <xref:System.Windows.Controls.TextBox> 상황에 맞는 메뉴를 구현 하는 데 사용 되는 일부 이벤트를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="78120-108">The following example shows the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that creates a <xref:System.Windows.Controls.TextBox> with some events that are used to implement the context menu.</span></span>  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="78120-109">예제</span><span class="sxs-lookup"><span data-stu-id="78120-109">Example</span></span>  
 <span data-ttu-id="78120-110">다음 예제에서는 상황에 맞는 메뉴를 구현 하는 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78120-110">The following example shows the code that implements the context menu.</span></span>  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 <span data-ttu-id="78120-111">사용 하 여이 작업을 수행 하는 데 사용 하는 코드는 <xref:System.Windows.Controls.RichTextBox> 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="78120-111">The code used for doing this with a <xref:System.Windows.Controls.RichTextBox> is similar.</span></span> <span data-ttu-id="78120-112">주요 차이점은 전달 된 매개 변수는 `GetSpellingError` 메서드.</span><span class="sxs-lookup"><span data-stu-id="78120-112">The main difference is in the parameter passed to the `GetSpellingError` method.</span></span> <span data-ttu-id="78120-113">에 대 한는 <xref:System.Windows.Controls.TextBox>, 캐럿 위치의 정수 인덱스를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="78120-113">For a <xref:System.Windows.Controls.TextBox>, pass the integer index of the caret position:</span></span>  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 <span data-ttu-id="78120-114">에 대 한는 <xref:System.Windows.Controls.RichTextBox>에 전달 합니다 <xref:System.Windows.Documents.TextPointer> 캐럿 위치를 지정 하는:</span><span class="sxs-lookup"><span data-stu-id="78120-114">For a <xref:System.Windows.Controls.RichTextBox>, pass the <xref:System.Windows.Documents.TextPointer> that specifies the caret position:</span></span>  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a><span data-ttu-id="78120-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="78120-115">See also</span></span>
- [<span data-ttu-id="78120-116">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="78120-116">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="78120-117">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="78120-117">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="78120-118">텍스트 편집 컨트롤에서 맞춤법 검사 사용</span><span class="sxs-lookup"><span data-stu-id="78120-118">Enable Spell Checking in a Text Editing Control</span></span>](how-to-enable-spell-checking-in-a-text-editing-control.md)
- [<span data-ttu-id="78120-119">TextBox에 사용자 지정 컨텍스트 메뉴 사용</span><span class="sxs-lookup"><span data-stu-id="78120-119">Use a Custom Context Menu with a TextBox</span></span>](how-to-use-a-custom-context-menu-with-a-textbox.md)
