---
title: '방법: 열거형에 바인딩'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: 5026261366d6abde82790f05780d8ba2c29c4a49
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62021013"
---
# <a name="how-to-bind-to-an-enumeration"></a><span data-ttu-id="fefb9-102">방법: 열거형에 바인딩</span><span class="sxs-lookup"><span data-stu-id="fefb9-102">How to: Bind to an Enumeration</span></span>
<span data-ttu-id="fefb9-103">이 예제에서는 열거형의 GetValues 메서드에 바인딩하여 열거형에 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fefb9-103">This example shows how to bind to an enumeration by binding to the enumeration's GetValues method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fefb9-104">예제</span><span class="sxs-lookup"><span data-stu-id="fefb9-104">Example</span></span>  
 <span data-ttu-id="fefb9-105">다음 예제에서는 <xref:System.Windows.Controls.ListBox> 목록이 표시 됩니다 <xref:System.Windows.HorizontalAlignment> 데이터 바인딩을 통해 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fefb9-105">In the following example, the <xref:System.Windows.Controls.ListBox> displays the list of <xref:System.Windows.HorizontalAlignment> enumeration values through data binding.</span></span> <span data-ttu-id="fefb9-106"><xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.Button> 변경할 수 있는 이러한 바인딩된를 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성 값을 <xref:System.Windows.Controls.Button> 값을 선택 하 여는 <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="fefb9-106">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.Button> are bound such that you can change the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property value of the <xref:System.Windows.Controls.Button> by selecting a value in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a><span data-ttu-id="fefb9-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="fefb9-107">See also</span></span>

- [<span data-ttu-id="fefb9-108">메서드 바인딩</span><span class="sxs-lookup"><span data-stu-id="fefb9-108">Bind to a Method</span></span>](how-to-bind-to-a-method.md)
- [<span data-ttu-id="fefb9-109">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="fefb9-109">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="fefb9-110">방법 항목</span><span class="sxs-lookup"><span data-stu-id="fefb9-110">How-to Topics</span></span>](data-binding-how-to-topics.md)
