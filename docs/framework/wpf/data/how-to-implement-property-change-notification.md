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
ms.openlocfilehash: 93a291b6dd35f9cc13c3c6f88aca5dc376b8bc1b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352752"
---
# <a name="how-to-implement-property-change-notification"></a><span data-ttu-id="1334f-102">방법: 속성 변경 알림 구현</span><span class="sxs-lookup"><span data-stu-id="1334f-102">How to: Implement Property Change Notification</span></span>
<span data-ttu-id="1334f-103">지원 하기 위해 <xref:System.Windows.Data.BindingMode.OneWay> 또는 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩 소스 (예를 들어 사용자가 폼을 편집할 때 자동으로 업데이트 미리 보기 창이), 동적 변경 사항을 자동으로 반영 하도록 바인딩 대상 속성을 사용 하도록 설정 하려면 바인딩 클래스 적절 한 속성 변경 알림을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1334f-103">To support <xref:System.Windows.Data.BindingMode.OneWay> or <xref:System.Windows.Data.BindingMode.TwoWay> binding to enable your binding target properties to automatically reflect the dynamic changes of the binding source (for example, to have the preview pane updated automatically when the user edits a form), your class needs to provide the proper property changed notifications.</span></span> <span data-ttu-id="1334f-104">이 예제에는 구현 하는 클래스를 만드는 방법을 보여 줍니다 <xref:System.ComponentModel.INotifyPropertyChanged>합니다.</span><span class="sxs-lookup"><span data-stu-id="1334f-104">This example shows how to create a class that implements <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1334f-105">예제</span><span class="sxs-lookup"><span data-stu-id="1334f-105">Example</span></span>  
 <span data-ttu-id="1334f-106">구현 <xref:System.ComponentModel.INotifyPropertyChanged> 선언 해야 합니다 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 이벤트 만들고를 `OnPropertyChanged` 메서드.</span><span class="sxs-lookup"><span data-stu-id="1334f-106">To implement <xref:System.ComponentModel.INotifyPropertyChanged> you need to declare the <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> event and create the `OnPropertyChanged` method.</span></span> <span data-ttu-id="1334f-107">그런 다음 변경 알림이 필요한 각 속성이 업데이트될 때마다 `OnPropertyChanged`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1334f-107">Then for each property you want change notifications for, you call `OnPropertyChanged` whenever the property is updated.</span></span>  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 <span data-ttu-id="1334f-108">예제를 보려면 `Person` 클래스를 사용 하 여를 지원할 수 있습니다 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩 참조 [TextBox 텍스트의 소스를 업데이트 하는 경우 제어](how-to-control-when-the-textbox-text-updates-the-source.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="1334f-108">To see an example of how the `Person` class can be used to support <xref:System.Windows.Data.BindingMode.TwoWay> binding, see [Control When the TextBox Text Updates the Source](how-to-control-when-the-textbox-text-updates-the-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1334f-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="1334f-109">See also</span></span>
- [<span data-ttu-id="1334f-110">바인딩 소스 개요</span><span class="sxs-lookup"><span data-stu-id="1334f-110">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="1334f-111">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="1334f-111">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="1334f-112">방법 항목</span><span class="sxs-lookup"><span data-stu-id="1334f-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
