---
title: '방법: 코드에서 바인딩 만들기'
description: SetBinding 메서드를 직접 호출 하 여 Windows Presentation Foundation 응용 프로그램의 코드에서 바인딩을 만드는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: aa2a29f4c1262d8ac54641b856c297b284b23a38
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165806"
---
# <a name="how-to-create-a-binding-in-code"></a><span data-ttu-id="9810e-103">방법: 코드에서 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="9810e-103">How to: Create a Binding in Code</span></span>
<span data-ttu-id="9810e-104">이 예제에서는 코드에서을 만들고 설정 하는 방법을 보여 줍니다 <xref:System.Windows.Data.Binding> .</span><span class="sxs-lookup"><span data-stu-id="9810e-104">This example shows how to create and set a <xref:System.Windows.Data.Binding> in code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9810e-105">예제</span><span class="sxs-lookup"><span data-stu-id="9810e-105">Example</span></span>  
 <span data-ttu-id="9810e-106"><xref:System.Windows.FrameworkElement>클래스와 클래스는 <xref:System.Windows.FrameworkContentElement> 모두 메서드를 노출 합니다 `SetBinding` .</span><span class="sxs-lookup"><span data-stu-id="9810e-106">The <xref:System.Windows.FrameworkElement> class and the <xref:System.Windows.FrameworkContentElement> class both expose a `SetBinding` method.</span></span> <span data-ttu-id="9810e-107">이러한 클래스 중 하나를 상속 하는 요소를 바인딩하는 경우 메서드를 직접 호출할 수 있습니다 <xref:System.Windows.FrameworkElement.SetBinding%2A> .</span><span class="sxs-lookup"><span data-stu-id="9810e-107">If you are binding an element that inherits either of these classes, you can call the <xref:System.Windows.FrameworkElement.SetBinding%2A> method directly.</span></span>  
  
 <span data-ttu-id="9810e-108">다음 예제에서는 라는 속성을 포함 하는 라는 클래스를 만듭니다 `MyData` `MyDataProperty` .</span><span class="sxs-lookup"><span data-stu-id="9810e-108">The following example creates a class named, `MyData`, which contains a property named `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 <span data-ttu-id="9810e-109">다음 예제에서는 바인딩 개체를 만들어 바인딩의 원본을 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9810e-109">The following example shows how to create a binding object to set the source of the binding.</span></span>  <span data-ttu-id="9810e-110">이 예제에서는를 사용 하 여 <xref:System.Windows.FrameworkElement.SetBinding%2A> <xref:System.Windows.Controls.TextBlock.Text%2A> 컨트롤인의 속성을 `myText` <xref:System.Windows.Controls.TextBlock> 에 바인딩합니다 `MyDataProperty` .</span><span class="sxs-lookup"><span data-stu-id="9810e-110">The example uses <xref:System.Windows.FrameworkElement.SetBinding%2A> to bind the <xref:System.Windows.Controls.TextBlock.Text%2A> property of `myText`, which is a <xref:System.Windows.Controls.TextBlock> control, to `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 <span data-ttu-id="9810e-111">전체 코드 샘플은 [코드 전용 바인딩 샘플](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9810e-111">For the complete code sample, see [Code-only Binding Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).</span></span>  
  
 <span data-ttu-id="9810e-112">를 호출 하는 대신 <xref:System.Windows.FrameworkElement.SetBinding%2A> <xref:System.Windows.Data.BindingOperations.SetBinding%2A> 클래스의 정적 메서드를 사용할 수 있습니다 <xref:System.Windows.Data.BindingOperations> .</span><span class="sxs-lookup"><span data-stu-id="9810e-112">Instead of calling <xref:System.Windows.FrameworkElement.SetBinding%2A>, you can use the <xref:System.Windows.Data.BindingOperations.SetBinding%2A> static method of the <xref:System.Windows.Data.BindingOperations> class.</span></span> <span data-ttu-id="9810e-113">다음 예제에서는 대신를 호출 하 여 <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> `myText` 에 바인딩합니다 `myDataProperty` .</span><span class="sxs-lookup"><span data-stu-id="9810e-113">The following example, calls <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> instead of <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> to bind `myText` to `myDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a><span data-ttu-id="9810e-114">참조</span><span class="sxs-lookup"><span data-stu-id="9810e-114">See also</span></span>

- [<span data-ttu-id="9810e-115">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="9810e-115">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="9810e-116">방법 항목</span><span class="sxs-lookup"><span data-stu-id="9810e-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
