---
title: '방법: 속성 변경 알림 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- notifications of change [WPF]
- data binding [WPF], property change notifications
- change notifications [WPF]
- properties [WPF], change notifications
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
ms.openlocfilehash: 4f9ff49a443577e119b0c1079abbe23bd7ede4c4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459750"
---
# <a name="how-to-implement-property-change-notification"></a><span data-ttu-id="8e642-102">방법: 속성 변경 알림 구현</span><span class="sxs-lookup"><span data-stu-id="8e642-102">How to: Implement Property Change Notification</span></span>
<span data-ttu-id="8e642-103">바인딩 대상 속성에서 바인딩 소스의 동적 변경 내용을 자동으로 반영 하도록 <xref:System.Windows.Data.BindingMode.OneWay> 또는 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩을 지원 하려면 (예를 들어 사용자가 양식을 편집할 때 미리 보기 창이 자동으로 업데이트 되도록 하려면) 클래스는 다음을 포함 해야 합니다. 적절 한 속성 변경 알림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e642-103">To support <xref:System.Windows.Data.BindingMode.OneWay> or <xref:System.Windows.Data.BindingMode.TwoWay> binding to enable your binding target properties to automatically reflect the dynamic changes of the binding source (for example, to have the preview pane updated automatically when the user edits a form), your class needs to provide the proper property changed notifications.</span></span> <span data-ttu-id="8e642-104">이 예제에서는 <xref:System.ComponentModel.INotifyPropertyChanged>를 구현 하는 클래스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8e642-104">This example shows how to create a class that implements <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e642-105">예제</span><span class="sxs-lookup"><span data-stu-id="8e642-105">Example</span></span>  
 <span data-ttu-id="8e642-106"><xref:System.ComponentModel.INotifyPropertyChanged>를 구현 하려면 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 이벤트를 선언 하 고 `OnPropertyChanged` 메서드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e642-106">To implement <xref:System.ComponentModel.INotifyPropertyChanged> you need to declare the <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> event and create the `OnPropertyChanged` method.</span></span> <span data-ttu-id="8e642-107">그런 다음 변경 알림이 필요한 각 속성이 업데이트될 때마다 `OnPropertyChanged`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8e642-107">Then for each property you want change notifications for, you call `OnPropertyChanged` whenever the property is updated.</span></span>  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 <span data-ttu-id="8e642-108">`Person` 클래스를 사용 하 여 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩을 지 원하는 방법에 대 한 예제를 보려면 [TextBox 텍스트가 소스를 업데이트 하는 시점 제어](how-to-control-when-the-textbox-text-updates-the-source.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8e642-108">To see an example of how the `Person` class can be used to support <xref:System.Windows.Data.BindingMode.TwoWay> binding, see [Control When the TextBox Text Updates the Source](how-to-control-when-the-textbox-text-updates-the-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e642-109">참조</span><span class="sxs-lookup"><span data-stu-id="8e642-109">See also</span></span>

- [<span data-ttu-id="8e642-110">바인딩 소스 개요</span><span class="sxs-lookup"><span data-stu-id="8e642-110">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="8e642-111">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="8e642-111">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="8e642-112">방법 항목</span><span class="sxs-lookup"><span data-stu-id="8e642-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
