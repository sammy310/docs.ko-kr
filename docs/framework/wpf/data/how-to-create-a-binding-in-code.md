---
title: '방법: 코드에서 바인딩 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: 616487a16ebbe6e23fe067fb7ce72644aa3f919f
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458853"
---
# <a name="how-to-create-a-binding-in-code"></a><span data-ttu-id="a328f-102">방법: 코드에서 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="a328f-102">How to: Create a Binding in Code</span></span>
<span data-ttu-id="a328f-103">이 예제에서는 코드에서 <xref:System.Windows.Data.Binding>를 만들고 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a328f-103">This example shows how to create and set a <xref:System.Windows.Data.Binding> in code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a328f-104">예제</span><span class="sxs-lookup"><span data-stu-id="a328f-104">Example</span></span>  
 <span data-ttu-id="a328f-105"><xref:System.Windows.FrameworkElement> 클래스와 <xref:System.Windows.FrameworkContentElement> 클래스는 모두 `SetBinding` 메서드를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a328f-105">The <xref:System.Windows.FrameworkElement> class and the <xref:System.Windows.FrameworkContentElement> class both expose a `SetBinding` method.</span></span> <span data-ttu-id="a328f-106">이러한 클래스 중 하나를 상속 하는 요소를 바인딩하는 경우 <xref:System.Windows.FrameworkElement.SetBinding%2A> 메서드를 직접 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a328f-106">If you are binding an element that inherits either of these classes, you can call the <xref:System.Windows.FrameworkElement.SetBinding%2A> method directly.</span></span>  
  
 <span data-ttu-id="a328f-107">다음 예제에서는 `MyDataProperty`라는 속성을 포함 하는 `MyData`이라는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a328f-107">The following example creates a class named, `MyData`, which contains a property named `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 <span data-ttu-id="a328f-108">다음 예제에서는 바인딩 개체를 만들어 바인딩의 원본을 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a328f-108">The following example shows how to create a binding object to set the source of the binding.</span></span>  <span data-ttu-id="a328f-109">이 예제에서는 <xref:System.Windows.FrameworkElement.SetBinding%2A>를 사용 하 여 <xref:System.Windows.Controls.TextBlock> 컨트롤인 `myText`의 <xref:System.Windows.Controls.TextBlock.Text%2A> 속성을 `MyDataProperty`에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="a328f-109">The example uses <xref:System.Windows.FrameworkElement.SetBinding%2A> to bind the <xref:System.Windows.Controls.TextBlock.Text%2A> property of `myText`, which is a <xref:System.Windows.Controls.TextBlock> control, to `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 <span data-ttu-id="a328f-110">전체 코드 샘플은 [코드 전용 바인딩 샘플](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a328f-110">For the complete code sample, see [Code-only Binding Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).</span></span>  
  
 <span data-ttu-id="a328f-111"><xref:System.Windows.FrameworkElement.SetBinding%2A>를 호출 하는 대신 <xref:System.Windows.Data.BindingOperations> 클래스의 <xref:System.Windows.Data.BindingOperations.SetBinding%2A> 정적 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a328f-111">Instead of calling <xref:System.Windows.FrameworkElement.SetBinding%2A>, you can use the <xref:System.Windows.Data.BindingOperations.SetBinding%2A> static method of the <xref:System.Windows.Data.BindingOperations> class.</span></span> <span data-ttu-id="a328f-112">다음 예에서는 <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> 대신 <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType>를 호출 하 여 `myText`를 `myDataProperty`에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="a328f-112">The following example, calls <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> instead of <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> to bind `myText` to `myDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a><span data-ttu-id="a328f-113">참조</span><span class="sxs-lookup"><span data-stu-id="a328f-113">See also</span></span>

- [<span data-ttu-id="a328f-114">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="a328f-114">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="a328f-115">방법 항목</span><span class="sxs-lookup"><span data-stu-id="a328f-115">How-to Topics</span></span>](data-binding-how-to-topics.md)
