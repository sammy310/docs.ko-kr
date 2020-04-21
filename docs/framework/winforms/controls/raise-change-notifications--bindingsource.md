---
title: '방법: BindingSource 및 INotifyPropertyChanged 인터페이스를 사용하여 변경 알림 발생'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- change notifications [Windows Forms], raising
- BindingSource component [Windows Forms], and IPropertyChange
- data sources [Windows Forms], detecting changes
- examples [Windows Forms], BindingSource component
- change notifications
- INotifyPropertyChanged interface [Windows Forms], using with BindingSource
- BindingSource component [Windows Forms], examples
ms.assetid: 7fa2cf51-c09f-4375-adf0-e36c5617f099
ms.openlocfilehash: 2fe4458aa43144a9c29ed67fd7bee99a37fe1434
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739689"
---
# <a name="how-to-raise-change-notifications-using-a-bindingsource-and-the-inotifypropertychanged-interface"></a><span data-ttu-id="0f2da-102">방법: BindingSource 및 INotifyPropertyChanged 인터페이스를 사용하여 변경 알림 발생</span><span class="sxs-lookup"><span data-stu-id="0f2da-102">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="0f2da-103">구성 <xref:System.Windows.Forms.BindingSource> 요소는 데이터 원본에 포함된 형식이 <xref:System.ComponentModel.INotifyPropertyChanged> 구현될 때 데이터 원본의 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 변경 내용을 자동으로 감지하고 속성 값이 변경될 때 이벤트를 발생시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2da-103">The <xref:System.Windows.Forms.BindingSource> component automatically detects changes in a data source when the type contained in the data source implements <xref:System.ComponentModel.INotifyPropertyChanged> and raises <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> events when a property value is changed.</span></span> <span data-ttu-id="0f2da-104">이 변경 검색은 데이터 원본 <xref:System.Windows.Forms.BindingSource> 값이 변경될 때 컨트롤이 자동으로 업데이트에 바인딩되기 때문에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2da-104">This change detection is useful because controls bound to the <xref:System.Windows.Forms.BindingSource> automatically update as the data source values change.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f2da-105">데이터 소스가 <xref:System.ComponentModel.INotifyPropertyChanged>를 구현하고 비동기 작업을 수행하는 경우 백그라운드 스레드에서 데이터 소스를 변경하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f2da-105">If your data source implements <xref:System.ComponentModel.INotifyPropertyChanged> and you are performing asynchronous operations, you should not make changes to the data source on a background thread.</span></span> <span data-ttu-id="0f2da-106">대신, 백그라운드 스레드에서 데이터를 읽은 다음 UI 스레드의 목록에 데이터를 병합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2da-106">Instead, you should read the data on a background thread and merge the data into a list on the UI thread.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f2da-107">예제</span><span class="sxs-lookup"><span data-stu-id="0f2da-107">Example</span></span>  
 <span data-ttu-id="0f2da-108">다음 코드 예제에서는 인터페이스의 간단한 <xref:System.ComponentModel.INotifyPropertyChanged> 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f2da-108">The following code example demonstrates a simple implementation of the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="0f2da-109">또한 <xref:System.Windows.Forms.BindingSource>가 <xref:System.ComponentModel.INotifyPropertyChanged> 형식 목록에 바인딩된 경우 <xref:System.Windows.Forms.BindingSource>가 자동으로 데이터 소스 변경 내용을 바인딩된 컨트롤에 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f2da-109">It also shows how the <xref:System.Windows.Forms.BindingSource> automatically passes a data source change to a bound control when the <xref:System.Windows.Forms.BindingSource> is bound to a list of the <xref:System.ComponentModel.INotifyPropertyChanged> type.</span></span>  
  
 <span data-ttu-id="0f2da-110">특성을 `CallerMemberName` 사용하는 경우 `NotifyPropertyChanged` 메서드에 대한 호출은 속성 이름을 문자열 인수로 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2da-110">If you use the `CallerMemberName` attribute, calls to the `NotifyPropertyChanged` method don't have to specify the property name as a string argument.</span></span> <span data-ttu-id="0f2da-111">자세한 내용은 [발신자 정보(C#)](../../../csharp/language-reference/attributes/caller-information.md) 또는 [발신자 정보(Visual Basic)를](../../../visual-basic/programming-guide/concepts/caller-information.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0f2da-111">For more information, see [Caller Information (C#)](../../../csharp/language-reference/attributes/caller-information.md) or [Caller Information (Visual Basic)](../../../visual-basic/programming-guide/concepts/caller-information.md).</span></span>  
  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0f2da-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="0f2da-112">Compiling the Code</span></span>  
 <span data-ttu-id="0f2da-113">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2da-113">This example requires:</span></span>  
  
- <span data-ttu-id="0f2da-114">시스템, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="0f2da-114">References to the System, System.Data, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f2da-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f2da-115">See also</span></span>

- <xref:System.ComponentModel.INotifyPropertyChanged>
- [<span data-ttu-id="0f2da-116">BindingSource 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0f2da-116">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="0f2da-117">방법: BindingSource ResetItem 메서드를 사용하여 변경 알림 발생</span><span class="sxs-lookup"><span data-stu-id="0f2da-117">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)
