---
title: '방법: SelectedValue, SelectedValuePath 및 SelectedItem 사용'
description: SelectedValue 및 SelectedValuePath 속성을 사용 하 여 Windows Presentation Foundation TreeView의 SelectedItem에 대 한 값을 지정 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], SelectedValue properties
- Control class [WPF], SelectedItem properties
- Control class [WPF], TreeView properties
- Control class [WPF], SelectedValue properties
- TreeView control [WPF], SelectedItem properties
- SelectedValue [WPF], SelectedValuePath properties
- TreeView control [WPF], SelectedValuePath properties
- Control class [WPF], SelectedValuePath properties
- SelectedValue [WPF], SelectedItem properties
ms.assetid: 2fc92ad4-f02c-4f89-bbe9-d4978a7af0db
ms.openlocfilehash: ddac2455dee0bf69d25307340eddd5364e43e823
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166277"
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a><span data-ttu-id="8d110-103">방법: SelectedValue, SelectedValuePath 및 SelectedItem 사용</span><span class="sxs-lookup"><span data-stu-id="8d110-103">How to: Use SelectedValue, SelectedValuePath, and SelectedItem</span></span>
<span data-ttu-id="8d110-104">이 예제에서는 및 속성을 사용 하 여 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 의에 대 한 값을 지정 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> <xref:System.Windows.Controls.TreeView> .</span><span class="sxs-lookup"><span data-stu-id="8d110-104">This example shows how to use the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> and <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> properties to specify a value for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> of a <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d110-105">예제</span><span class="sxs-lookup"><span data-stu-id="8d110-105">Example</span></span>  
 <span data-ttu-id="8d110-106">속성은의에 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 대 한를 지정 하는 방법을 제공 합니다 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> <xref:System.Windows.Controls.TreeView.SelectedItem%2A> <xref:System.Windows.Controls.TreeView> .</span><span class="sxs-lookup"><span data-stu-id="8d110-106">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property provides a way to specify a <xref:System.Windows.Controls.TreeView.SelectedValue%2A> for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in a <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="8d110-107">는 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 컬렉션의 개체를 나타내고 <xref:System.Windows.Controls.ItemsControl.Items%2A> 는 <xref:System.Windows.Controls.TreeView> 선택한 항목의 단일 속성 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d110-107">The <xref:System.Windows.Controls.TreeView.SelectedItem%2A> represents an object in the <xref:System.Windows.Controls.ItemsControl.Items%2A> collection and the <xref:System.Windows.Controls.TreeView> displays the value of a single property of the selected item.</span></span> <span data-ttu-id="8d110-108">속성은 속성 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 의 값을 결정 하는 데 사용 되는 속성의 경로를 지정 합니다 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> .</span><span class="sxs-lookup"><span data-stu-id="8d110-108">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property specifies the path to the property that is used to determine the value of the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property.</span></span> <span data-ttu-id="8d110-109">이 항목의 예제에서는 이러한 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d110-109">The examples in this topic illustrate this concept.</span></span>  
  
 <span data-ttu-id="8d110-110">다음 예제에서는 <xref:System.Windows.Data.XmlDataProvider> 직원 정보를 포함 하는을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d110-110">The following example shows an <xref:System.Windows.Data.XmlDataProvider> that contains employee information.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 <span data-ttu-id="8d110-111">다음 예제에서는 <xref:System.Windows.HierarchicalDataTemplate> 의 및를 표시 하는를 정의 합니다 `EmployeeName` `EmployeeWorkDay` `Employee` .</span><span class="sxs-lookup"><span data-stu-id="8d110-111">The following example defines a <xref:System.Windows.HierarchicalDataTemplate> that displays the `EmployeeName` and `EmployeeWorkDay` of the `Employee`.</span></span> <span data-ttu-id="8d110-112">는 <xref:System.Windows.HierarchicalDataTemplate> 템플릿의 일부로를 지정 하지 않습니다 `EmployeeNumber` .</span><span class="sxs-lookup"><span data-stu-id="8d110-112">Note that the <xref:System.Windows.HierarchicalDataTemplate> does not specify the `EmployeeNumber` as part of the template.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 <span data-ttu-id="8d110-113">다음 예제에서는 이전에 <xref:System.Windows.Controls.TreeView> 정의 된를 사용 하 <xref:System.Windows.HierarchicalDataTemplate> 고 속성을로 설정 하는을 보여 줍니다 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> `EmployeeNumber` .</span><span class="sxs-lookup"><span data-stu-id="8d110-113">The following example shows a <xref:System.Windows.Controls.TreeView> that uses the previously defined <xref:System.Windows.HierarchicalDataTemplate> and that sets the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property to the `EmployeeNumber`.</span></span> <span data-ttu-id="8d110-114">에서을 선택 하면 `EmployeeName` <xref:System.Windows.Controls.TreeView> 속성이 선택 된에 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> `EmployeeInfo` 해당 하는 데이터 항목을 반환 합니다 `EmployeeName` .</span><span class="sxs-lookup"><span data-stu-id="8d110-114">When you select an `EmployeeName` in the <xref:System.Windows.Controls.TreeView>, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property returns the `EmployeeInfo` data item that corresponds to the selected `EmployeeName`.</span></span> <span data-ttu-id="8d110-115">그러나이의가로 설정 되어 있기 때문에는로 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> <xref:System.Windows.Controls.TreeView> `EmployeeNumber` <xref:System.Windows.Controls.TreeView.SelectedValue%2A> 설정 됩니다 `EmployeeNumber` .</span><span class="sxs-lookup"><span data-stu-id="8d110-115">However, because the <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> of this <xref:System.Windows.Controls.TreeView> is set to `EmployeeNumber`, the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> is set to the `EmployeeNumber`.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a><span data-ttu-id="8d110-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d110-116">See also</span></span>

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [<span data-ttu-id="8d110-117">TreeView 개요</span><span class="sxs-lookup"><span data-stu-id="8d110-117">TreeView Overview</span></span>](treeview-overview.md)
- [<span data-ttu-id="8d110-118">방법 항목</span><span class="sxs-lookup"><span data-stu-id="8d110-118">How-to Topics</span></span>](treeview-how-to-topics.md)
