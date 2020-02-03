---
title: 데이터 바인딩의 변경 알림
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, data binding
- Windows Forms, adding change notification for data binding
ms.assetid: b5b10f90-0585-41d9-a377-409835262a92
ms.openlocfilehash: 2dffea46bf0db54d28ef55e507767d88bd29ebc2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746357"
---
# <a name="change-notification-in-windows-forms-data-binding"></a>Windows Forms 데이터 바인딩의 변경 알림
Windows Forms 데이터 바인딩의 가장 중요 한 개념 중 하나는 *변경 알림*입니다. 데이터 원본 및 바인딩된 컨트롤에 항상 최신 데이터가 포함 되도록 하려면 데이터 바인딩에 대 한 변경 알림을 추가 해야 합니다. 특히 바인딩된 컨트롤이 데이터 소스에 적용 된 변경 내용에 대 한 알림 메시지를 표시 하 고 컨트롤의 바인딩된 속성에 적용 된 변경 내용에 대 한 알림이 데이터 소스에 표시 되도록 합니다.  
  
 데이터 바인딩의 종류에 따라 다음과 같은 다양 한 종류의 변경 알림이 있습니다.  
  
- 단일 컨트롤 속성이 개체의 단일 인스턴스에 바인딩되는 단순 바인딩입니다.  
  
- 목록에 있는 항목의 속성 또는 개체 목록에 바인딩된 컨트롤 속성에 바인딩된 단일 컨트롤 속성을 포함할 수 있는 목록 기반 바인딩입니다.  
  
 또한 데이터 바인딩에 사용 하려는 Windows Forms 컨트롤을 만드는 경우 컨트롤의 바인딩된 속성에 대 한 변경 내용이 데이터 소스에 전파 되도록 *PropertyName*변경 패턴을 컨트롤에 적용 해야 합니다.  
  
## <a name="change-notification-for-simple-binding"></a>단순 바인딩에 대 한 변경 알림  
 단순 바인딩의 경우 비즈니스 개체는 바인딩된 속성 값이 변경 될 때 변경 알림을 제공 해야 합니다. 이렇게 하려면 비즈니스 개체의 각 속성에 대해 *PropertyName*Changed 이벤트를 표시 하 고 비즈니스 개체를 <xref:System.Windows.Forms.BindingSource> 또는 비즈니스 개체가 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현 하는 기본 설정 방법으로 컨트롤에 바인딩한 다음 속성 값이 변경 될 때 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 이벤트를 발생 시킵니다. 자세한 내용은 [방법: INotifyPropertyChanged 인터페이스 구현](how-to-implement-the-inotifypropertychanged-interface.md)을 참조 하세요. <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현 하는 개체를 사용 하는 경우 <xref:System.Windows.Forms.BindingSource>를 사용 하 여 개체를 컨트롤에 바인딩할 필요가 없지만 <xref:System.Windows.Forms.BindingSource>를 사용 하는 것이 좋습니다.  
  
## <a name="change-notification-for-list-based-binding"></a>목록 기반 바인딩에 대 한 변경 알림  
 Windows Forms은 바인딩된 목록에 의존 하 여 속성 변경 (목록 항목 속성 값 변경) 및 변경 된 목록 (항목을 삭제 하거나 목록에 추가) 정보를 바인딩된 컨트롤에 제공 합니다. 따라서 데이터 바인딩에 사용 되는 목록은 두 형식의 변경 알림을 모두 제공 하는 <xref:System.ComponentModel.IBindingList>를 구현 해야 합니다. <xref:System.ComponentModel.BindingList%601>은 <xref:System.ComponentModel.IBindingList>의 제네릭 구현 이며 Windows Forms 데이터 바인딩과 함께 사용 하도록 설계 되었습니다. <xref:System.ComponentModel.INotifyPropertyChanged>를 구현 하는 비즈니스 개체 유형을 포함 하는 <xref:System.ComponentModel.BindingList%601>를 만들 수 있으며,이 목록에서 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 이벤트를 <xref:System.ComponentModel.IBindingList.ListChanged> 이벤트로 자동으로 변환 합니다. 바인딩된 목록이 <xref:System.ComponentModel.IBindingList>아닌 경우 <xref:System.Windows.Forms.BindingSource> 구성 요소를 사용 하 여 개체 목록을 Windows Forms 컨트롤에 바인딩해야 합니다. <xref:System.Windows.Forms.BindingSource> 구성 요소는 <xref:System.ComponentModel.BindingList%601>와 유사한 속성-목록 변환 기능을 제공 합니다. 자세한 내용은 [방법: BindingSource와 INotifyPropertyChanged 인터페이스를 사용 하 여 변경 알림 발생](./controls/raise-change-notifications--bindingsource.md)을 참조 하세요.  
  
## <a name="change-notification-for-custom-controls"></a>사용자 지정 컨트롤에 대 한 변경 알림  
 마지막으로, 컨트롤 쪽에서 데이터에 바인딩하기 위해 디자인 된 각 속성에 대해 *PropertyName*Changed 이벤트를 노출 해야 합니다. 그러면 컨트롤 속성에 대 한 변경 내용이 바인딩된 데이터 소스에 전파 됩니다. 자세한 내용은 [방법: PropertyNameChanged 패턴 적용](how-to-apply-the-propertynamechanged-pattern.md) 을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.ComponentModel.INotifyPropertyChanged>
- <xref:System.ComponentModel.BindingList%601>
- [Windows Forms 데이터 바인딩](windows-forms-data-binding.md)
- [Windows Forms에서 지원하는 데이터 소스](data-sources-supported-by-windows-forms.md)
- [데이터 바인딩 및 Windows Forms](data-binding-and-windows-forms.md)
