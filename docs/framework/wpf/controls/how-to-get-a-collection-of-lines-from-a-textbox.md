---
title: '방법: TextBox에서 줄 컬렉션 가져오기'
ms.date: 03/30/2017
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
ms.openlocfilehash: 1aa73e55a3fdfd658c6a337b598dff96244ace40
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354195"
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a><span data-ttu-id="7eee8-102">방법: TextBox에서 줄 컬렉션 가져오기</span><span class="sxs-lookup"><span data-stu-id="7eee8-102">How to: Get a Collection of Lines from a TextBox</span></span>
<span data-ttu-id="7eee8-103">이 예제에서는 텍스트에서 줄 컬렉션 가져오기는 <xref:System.Windows.Controls.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="7eee8-103">This example shows how to get a collection of lines of text from a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7eee8-104">예제</span><span class="sxs-lookup"><span data-stu-id="7eee8-104">Example</span></span>  
 <span data-ttu-id="7eee8-105">다음 예제는 간단한 메서드를 보여 줍니다.는 <xref:System.Windows.Controls.TextBox> 인수 및 반환을 <xref:System.Collections.Specialized.StringCollection> 의 텍스트 줄을 포함 하는 **텍스트 상자에 붙여넣습니다**합니다.</span><span class="sxs-lookup"><span data-stu-id="7eee8-105">The following example shows a simple method that takes a <xref:System.Windows.Controls.TextBox> as the argument, and returns a <xref:System.Collections.Specialized.StringCollection> containing the lines of text in the **TextBox**.</span></span>  <span data-ttu-id="7eee8-106"><xref:System.Windows.Controls.TextBox.LineCount%2A> 속성을 사용 하는 줄은 현재 확인 합니다 **텍스트 상자**, 및 <xref:System.Windows.Controls.TextBox.GetLineText%2A> 메서드는 다음 각 줄을 추출 하 고 선 컬렉션에 추가 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7eee8-106">The <xref:System.Windows.Controls.TextBox.LineCount%2A> property is used to determine how many lines are currently in the **TextBox**, and the <xref:System.Windows.Controls.TextBox.GetLineText%2A> method is then used to extract each line and add it to the collection of lines.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a><span data-ttu-id="7eee8-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="7eee8-107">See also</span></span>
- [<span data-ttu-id="7eee8-108">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="7eee8-108">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="7eee8-109">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="7eee8-109">RichTextBox Overview</span></span>](richtextbox-overview.md)
