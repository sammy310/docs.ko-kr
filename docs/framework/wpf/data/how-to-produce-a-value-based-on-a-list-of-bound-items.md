---
title: '방법: 바인딩된 항목 목록을 기반으로 값 산출'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
ms.openlocfilehash: da183a34eb85de54b1e3f54f8d14c09e25640165
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459699"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a><span data-ttu-id="ec3e6-102">방법: 바인딩된 항목 목록을 기반으로 값 산출</span><span class="sxs-lookup"><span data-stu-id="ec3e6-102">How to: Produce a Value Based on a List of Bound Items</span></span>
<span data-ttu-id="ec3e6-103"><xref:System.Windows.Data.MultiBinding>를 사용 하 여 바인딩 대상 속성을 소스 속성 목록에 바인딩한 다음 지정 된 입력을 사용 하 여 값을 생성 하는 논리를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec3e6-103"><xref:System.Windows.Data.MultiBinding> allows you to bind a binding target property to a list of source properties and then apply logic to produce a value with the given inputs.</span></span> <span data-ttu-id="ec3e6-104">이 예제에서는 <xref:System.Windows.Data.MultiBinding>를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ec3e6-104">This example demonstrates how to use <xref:System.Windows.Data.MultiBinding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec3e6-105">예제</span><span class="sxs-lookup"><span data-stu-id="ec3e6-105">Example</span></span>  
 <span data-ttu-id="ec3e6-106">다음 예제에서 `NameListData`은 `firstName`과 `lastName` 두 개의 속성을 포함하는 `PersonName` 개체의 컬렉션을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="ec3e6-106">In the following example, `NameListData` refers to a collection of `PersonName` objects, which are objects that contain two properties, `firstName` and `lastName`.</span></span> <span data-ttu-id="ec3e6-107">다음 예에서는 성을 가진 사람의 성과 이름을 먼저 표시 하는 <xref:System.Windows.Controls.TextBlock>를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec3e6-107">The following example produces a <xref:System.Windows.Controls.TextBlock> that shows the first and last names of a person with the last name first.</span></span>  
  
 [!code-xaml[MultiBinding#Resources1](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 <span data-ttu-id="ec3e6-108">성이 먼저 표시되는 형식이 생성되는 방법을 이해하기 위해 `NameConverter`의 구현을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="ec3e6-108">To understand how the last-name-first format is produced, let's take a look at the implementation of the `NameConverter`:</span></span>  
  
 [!code-csharp[MultiBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 <span data-ttu-id="ec3e6-109">`NameConverter`는 <xref:System.Windows.Data.IMultiValueConverter> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ec3e6-109">`NameConverter` implements the <xref:System.Windows.Data.IMultiValueConverter> interface.</span></span> <span data-ttu-id="ec3e6-110">`NameConverter`은 개별 바인딩에서 값을 가져오고 값 개체 배열에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ec3e6-110">`NameConverter` takes the values from the individual bindings and stores them in the values object array.</span></span> <span data-ttu-id="ec3e6-111"><xref:System.Windows.Data.Binding> 요소가 <xref:System.Windows.Data.MultiBinding> 요소 아래에 표시 되는 순서는 배열에 해당 값이 저장 되는 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="ec3e6-111">The order in which the <xref:System.Windows.Data.Binding> elements appear under the <xref:System.Windows.Data.MultiBinding> element is the order in which those values are stored in the array.</span></span> <span data-ttu-id="ec3e6-112"><xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> 특성의 값은 매개 변수에 대 한 스위치를 수행 하 여 이름의 형식을 지정 하는 방법을 결정 하는 <xref:System.Windows.Data.MultiBinding.Converter%2A> 메서드의 매개 변수 인수에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec3e6-112">The value of the <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> attribute is referenced by the parameter argument of the <xref:System.Windows.Data.MultiBinding.Converter%2A> method, which performs a switch on the parameter to determine how to format the name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec3e6-113">참조</span><span class="sxs-lookup"><span data-stu-id="ec3e6-113">See also</span></span>

- [<span data-ttu-id="ec3e6-114">바인딩된 데이터 변환</span><span class="sxs-lookup"><span data-stu-id="ec3e6-114">Convert Bound Data</span></span>](how-to-convert-bound-data.md)
- [<span data-ttu-id="ec3e6-115">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="ec3e6-115">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="ec3e6-116">방법 항목</span><span class="sxs-lookup"><span data-stu-id="ec3e6-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
