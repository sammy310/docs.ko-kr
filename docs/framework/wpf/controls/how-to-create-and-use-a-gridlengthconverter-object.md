---
title: '방법: GridLengthConverter 개체 만들기 및 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], GridLengthConverter objects
ms.assetid: 5ab75911-e36a-4825-80e4-081c57e8e182
ms.openlocfilehash: 498d2b9c531f391f4cbeb1478469a99d381deec7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050989"
---
# <a name="how-to-create-and-use-a-gridlengthconverter-object"></a><span data-ttu-id="91ce5-102">방법: GridLengthConverter 개체 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="91ce5-102">How to: Create and Use a GridLengthConverter Object</span></span>
## <a name="example"></a><span data-ttu-id="91ce5-103">예제</span><span class="sxs-lookup"><span data-stu-id="91ce5-103">Example</span></span>  
 <span data-ttu-id="91ce5-104">다음 예제에서는 만들고의 인스턴스를 사용 하는 방법을 보여 줍니다 <xref:System.Windows.GridLengthConverter>합니다.</span><span class="sxs-lookup"><span data-stu-id="91ce5-104">The following example shows how to create and use an instance of <xref:System.Windows.GridLengthConverter>.</span></span> <span data-ttu-id="91ce5-105">이 예제에서는 라는 사용자 지정 메서드를 정의 `changeCol`, 전달 하는 <xref:System.Windows.Controls.ListBoxItem> 에 <xref:System.Windows.GridLengthConverter> 으로 변환 하는 <xref:System.Windows.Controls.ContentControl.Content%2A> 의 <xref:System.Windows.Controls.ListBoxItem> 인스턴스에 <xref:System.Windows.GridLength>합니다.</span><span class="sxs-lookup"><span data-stu-id="91ce5-105">The example defines a custom method called `changeCol`, which passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.GridLengthConverter> that converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.GridLength>.</span></span> <span data-ttu-id="91ce5-106">변환 된 값의 값으로 다시 전달 되는 <xref:System.Windows.Controls.ColumnDefinition.Width%2A> 의 속성을 <xref:System.Windows.Controls.ColumnDefinition> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="91ce5-106">The converted value is then passed back as the value of the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> property of the <xref:System.Windows.Controls.ColumnDefinition> element.</span></span>  
  
 <span data-ttu-id="91ce5-107">이 예제에서는 라는 두 번째 사용자 지정 메서드를 정의 `changeColVal`합니다.</span><span class="sxs-lookup"><span data-stu-id="91ce5-107">The example also defines a second custom method, called `changeColVal`.</span></span> <span data-ttu-id="91ce5-108">이 사용자 지정 메서드를 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 의 <xref:System.Windows.Controls.Slider> 에 <xref:System.String> 및 해당 값에 다시 전달 됩니다는 <xref:System.Windows.Controls.ColumnDefinition> 으로 <xref:System.Windows.Controls.ColumnDefinition.Width%2A> 요소의.</span><span class="sxs-lookup"><span data-stu-id="91ce5-108">This custom method converts the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> of a <xref:System.Windows.Controls.Slider> to a <xref:System.String> and then passes that value back to the <xref:System.Windows.Controls.ColumnDefinition> as the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of the element.</span></span>  
  
 <span data-ttu-id="91ce5-109">별도 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일의 내용을 정의 <xref:System.Windows.Controls.ListBoxItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="91ce5-109">Note that a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file defines the contents of a <xref:System.Windows.Controls.ListBoxItem>.</span></span>  
  
 [!code-csharp[gridlengthConverterGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridlengthConverterGrid/CSharp/Window1.xaml.cs#1)]
 [!code-vb[gridlengthConverterGrid#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridlengthConverterGrid/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="91ce5-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="91ce5-110">See also</span></span>

- <xref:System.Windows.GridLengthConverter>
- <xref:System.Windows.GridLength>
