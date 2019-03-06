---
title: '방법: InkCanvas에 데이터 바인딩'
ms.date: 03/30/2017
helpviewer_keywords:
- InkCanvas [WPF], binding data to
- binding data [WPF], to InkCanvas
ms.assetid: 8d6b4d9e-ea7f-4412-ba83-3feccec5a515
ms.openlocfilehash: 5d3fc0ed7b6176d7bc68bf20af42c311b5563908
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372947"
---
# <a name="how-to-data-bind-to-an-inkcanvas"></a><span data-ttu-id="cafc1-102">방법: InkCanvas에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="cafc1-102">How to: Data Bind to an InkCanvas</span></span>
## <a name="example"></a><span data-ttu-id="cafc1-103">예제</span><span class="sxs-lookup"><span data-stu-id="cafc1-103">Example</span></span>  
 <span data-ttu-id="cafc1-104">다음 예제에서는 바인딩하는 방법을 보여는 <xref:System.Windows.Controls.InkCanvas.Strokes%2A> 의 속성을 <xref:System.Windows.Controls.InkCanvas> 다른 <xref:System.Windows.Controls.InkCanvas>합니다.</span><span class="sxs-lookup"><span data-stu-id="cafc1-104">The following example demonstrates how to bind the <xref:System.Windows.Controls.InkCanvas.Strokes%2A> property of an <xref:System.Windows.Controls.InkCanvas> to another <xref:System.Windows.Controls.InkCanvas>.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#2)]  
  
 <span data-ttu-id="cafc1-105">다음 예제에서는 바인딩하는 방법을 보여는 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 속성을 데이터 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="cafc1-105">The following example demonstrates how to bind the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property to a data source.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#3)]  
[!code-xaml[InkCanvasBindingSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#4)]  
  
 <span data-ttu-id="cafc1-106">다음 예제에서는 두 개의 선언 <xref:System.Windows.Controls.InkCanvas> XAML 개체 및 해당 및 기타 데이터 원본 간의 데이터 바인딩을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cafc1-106">The following example declares two <xref:System.Windows.Controls.InkCanvas> objects in XAML and establishes data binding between them and other data sources.</span></span>  <span data-ttu-id="cafc1-107">첫 번째 <xref:System.Windows.Controls.InkCanvas>라는 `ic`, 두 데이터 소스에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="cafc1-107">The first <xref:System.Windows.Controls.InkCanvas>, called `ic`, is bound to two data sources.</span></span>  <span data-ttu-id="cafc1-108">합니다 <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> 및 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 속성을 `ic` 바인딩되는 <xref:System.Windows.Controls.ListBox> 에 XAML에 정의 된 배열에 바인딩되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cafc1-108">The <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> and <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties on `ic` are bound to <xref:System.Windows.Controls.ListBox> objects, which are in turn bound to arrays defined in the XAML.</span></span>  <span data-ttu-id="cafc1-109"><xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, 및 <xref:System.Windows.Controls.InkCanvas.Strokes%2A> 의 두 번째 속성 <xref:System.Windows.Controls.InkCanvas> 바인딩되는 첫 번째 <xref:System.Windows.Controls.InkCanvas>, `ic`합니다.</span><span class="sxs-lookup"><span data-stu-id="cafc1-109">The <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, and <xref:System.Windows.Controls.InkCanvas.Strokes%2A> properties of the second <xref:System.Windows.Controls.InkCanvas> are bound to the first <xref:System.Windows.Controls.InkCanvas>, `ic`.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window1.xaml#1)]
