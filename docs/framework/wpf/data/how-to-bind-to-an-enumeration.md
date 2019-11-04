---
title: '방법: 열거형 바인딩'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: 93f33e497fd7acb81c55f86bf38737d4e7d79bf2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454445"
---
# <a name="how-to-bind-to-an-enumeration"></a><span data-ttu-id="13871-102">방법: 열거형 바인딩</span><span class="sxs-lookup"><span data-stu-id="13871-102">How to: Bind to an Enumeration</span></span>
<span data-ttu-id="13871-103">이 예제에서는 열거형의 GetValues 메서드에 바인딩하여 열거형에 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="13871-103">This example shows how to bind to an enumeration by binding to the enumeration's GetValues method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13871-104">예제</span><span class="sxs-lookup"><span data-stu-id="13871-104">Example</span></span>  
 <span data-ttu-id="13871-105">다음 예제에서 <xref:System.Windows.Controls.ListBox>는 데이터 바인딩을 통해 <xref:System.Windows.HorizontalAlignment> 열거 값의 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="13871-105">In the following example, the <xref:System.Windows.Controls.ListBox> displays the list of <xref:System.Windows.HorizontalAlignment> enumeration values through data binding.</span></span> <span data-ttu-id="13871-106"><xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.Button>는 <xref:System.Windows.Controls.ListBox>에서 값을 선택 하 여 <xref:System.Windows.Controls.Button>의 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성 값을 변경할 수 있도록 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="13871-106">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.Button> are bound such that you can change the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property value of the <xref:System.Windows.Controls.Button> by selecting a value in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a><span data-ttu-id="13871-107">참조</span><span class="sxs-lookup"><span data-stu-id="13871-107">See also</span></span>

- [<span data-ttu-id="13871-108">메서드 바인딩</span><span class="sxs-lookup"><span data-stu-id="13871-108">Bind to a Method</span></span>](how-to-bind-to-a-method.md)
- [<span data-ttu-id="13871-109">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="13871-109">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="13871-110">방법 항목</span><span class="sxs-lookup"><span data-stu-id="13871-110">How-to Topics</span></span>](data-binding-how-to-topics.md)
