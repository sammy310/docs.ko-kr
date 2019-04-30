---
title: '방법: FontSizeConverter 클래스 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- FontSizeConverter objects [WPF]
- typography [WPF], FontSizeConverter objects
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
ms.openlocfilehash: f33a297ae07d5509d2b4d9a98636086ac433a57f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051041"
---
# <a name="how-to-use-the-fontsizeconverter-class"></a><span data-ttu-id="52dca-102">방법: FontSizeConverter 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="52dca-102">How to: Use the FontSizeConverter Class</span></span>
## <a name="example"></a><span data-ttu-id="52dca-103">예제</span><span class="sxs-lookup"><span data-stu-id="52dca-103">Example</span></span>  
 <span data-ttu-id="52dca-104">인스턴스를 만드는 방법을 보여 주는이 예제 <xref:System.Windows.FontSizeConverter> 를 글꼴 크기를 변경 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="52dca-104">This example shows how to create an instance of <xref:System.Windows.FontSizeConverter> and use it to change a font size.</span></span>  
  
 <span data-ttu-id="52dca-105">이 예제에서는 라는 사용자 지정 메서드를 정의 `changeSize` 의 콘텐츠를 변환 하는 <xref:System.Windows.Controls.ListBoxItem>별도의 정의 된 대로 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 인스턴스에 파일을 <xref:System.Double>, 고 나중에 다시는 <xref:System.String>합니다.</span><span class="sxs-lookup"><span data-stu-id="52dca-105">The example defines a custom method called `changeSize` that converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Double>, and later into a <xref:System.String>.</span></span> <span data-ttu-id="52dca-106">이 메서드는 전달를 <xref:System.Windows.Controls.ListBoxItem> 에 <xref:System.Windows.FontSizeConverter> 변환 하는 개체를 <xref:System.Windows.Controls.ContentControl.Content%2A> 의 <xref:System.Windows.Controls.ListBoxItem> 인스턴스에 <xref:System.Double>합니다.</span><span class="sxs-lookup"><span data-stu-id="52dca-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.FontSizeConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double>.</span></span> <span data-ttu-id="52dca-107">이 값은 다음 값으로 다시 전달 합니다 <xref:System.Windows.Controls.TextBlock.FontSize%2A> 의 속성을 <xref:System.Windows.Controls.TextBlock> 요소.</span><span class="sxs-lookup"><span data-stu-id="52dca-107">This value is then passed back as the value of the <xref:System.Windows.Controls.TextBlock.FontSize%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="52dca-108">이 예제에서는 호출 되는 두 번째 사용자 지정 메서드도 정의 `changeFamily`합니다.</span><span class="sxs-lookup"><span data-stu-id="52dca-108">This example also defines a second custom method that is called `changeFamily`.</span></span> <span data-ttu-id="52dca-109">이 메서드는 변환를 <xref:System.Windows.Controls.ContentControl.Content%2A> 의 <xref:System.Windows.Controls.ListBoxItem> 에 <xref:System.String>, 다음 해당 값을 전달를 <xref:System.Windows.Controls.TextBlock.FontFamily%2A> 속성은 <xref:System.Windows.Controls.TextBlock> 요소.</span><span class="sxs-lookup"><span data-stu-id="52dca-109">This method converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.String>, and then passes that value to the <xref:System.Windows.Controls.TextBlock.FontFamily%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="52dca-110">이 예제에서는 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52dca-110">This example does not run.</span></span>  
  
 [!code-csharp[FontSizeConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="52dca-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="52dca-111">See also</span></span>

- <xref:System.Windows.FontSizeConverter>
