---
title: 데이터 바인딩과 관련된 인터페이스
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], data-binding interfaces
- INotifyPropertyChanged interface
- IBindingListView interface
- IList interface [Windows Forms], Windows Forms data binding
- IBindingList interface [Windows Forms], Windows Forms data binding
- interfaces [Windows Forms], Windows Forms data binding
- IEditableObject interface [Windows Forms], Windows Forms data binding
- data binding [Windows Forms], interfaces
- IDataErrorInfo interface [Windows Forms], Windows Forms data binding
ms.assetid: 14e49a2e-3e46-47ca-b491-70d546333277
ms.openlocfilehash: ffda85b2704212ea5323117447e0cfe17ffb33db
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226967"
---
# <a name="interfaces-related-to-data-binding"></a>데이터 바인딩과 관련된 인터페이스
[!INCLUDE[vstecado](../../../includes/vstecado-md.md)]을 사용하면 애플리케이션과 처리할 데이터의 바인딩 요구를 충족시킬 다양한 데이터 구조를 만들 수 있습니다. Windows Forms에서 데이터를 제공하거나 사용하는 고유 클래스를 만들고 싶을 수도 있습니다. 이러한 개체는 기본 데이터 바인딩부터 디자인 타임 지원, 오류 확인, 변경 사항 알림, 심지어 데이터 자체에 적용된 변경 내용의 구조화된 롤백 지원에 이르기까지 다양한 수준의 복합 기능을 제공할 수 있습니다.  
  
## <a name="consumers-of-data-binding-interfaces"></a>데이터 바인딩 인터페이스의 소비자  
 다음 섹션에서는 두 그룹의 인터페이스 개체를 설명합니다. 첫 번째 그룹에서는 데이터 소스 작성자에 의해 데이터 소스에 구현된 인터페이스를 나열합니다. 이러한 인터페이스는 데이터 소스 소비자가 사용하며, 이러한 소비자의 대부분은 Windows Forms 컨트롤 또는 구성 요소입니다. 두 번째 그룹에서는 구성 요소 작성자를 위해 설계된 인터페이스를 나열합니다. 구성 요소 작성자는 Windows Forms 데이터 바인딩 엔진에서 사용할 데이터 바인딩을 지원하는 구성 요소를 만들 때 이러한 인터페이스를 사용합니다. 양식과 연결된 클래스 내에 이러한 인터페이스를 구현하여 데이터 바인딩을 사용할 수 있습니다. 각 경우에 데이터와의 상호 작용이 가능한 인터페이스를 구현하는 클래스가 제공됩니다. Visual Studio 신속한 응용 프로그램 RAD (개발) 데이터 디자인 환경 도구는 이미이 기능을 활용을 수행 합니다.  
  
### <a name="interfaces-for-implementation-by-data-source-authors"></a>데이터 소스 작성자가 구현할 수 있는 인터페이스  
 다음 인터페이스는 Windows Forms 컨트롤에서 사용할 수 있도록 설계되었습니다.  
  
-   <xref:System.Collections.IList> interface(인터페이스)  
  
     구현 하는 클래스를 <xref:System.Collections.IList> 인터페이스 수는 <xref:System.Array>를 <xref:System.Collections.ArrayList>, 또는 <xref:System.Collections.CollectionBase>합니다. 인덱싱된 항목 유형 목록을 이들은 <xref:System.Object>합니다. 인덱스의 첫 번째 항목에 따라 형식이 결정되기 때문에 이러한 목록에는 같은 형식이 포함되어 있어야 합니다. <xref:System.Collections.IList> 런타임에만 바인딩에 사용할 수 있습니다.  
  
    > [!NOTE]
    >  Windows Forms와 바인딩할 비즈니스 개체 목록을 만들려는 경우 사용을 고려해 야 하는 <xref:System.ComponentModel.BindingList%601>합니다. <xref:System.ComponentModel.BindingList%601> 양방향 Windows Forms 데이터 바인딩에 필요한 기본 인터페이스를 구현 하는 확장 가능한 클래스입니다.  
  
-   <xref:System.ComponentModel.IBindingList> interface(인터페이스)  
  
     구현 하는 클래스는 <xref:System.ComponentModel.IBindingList> 인터페이스를 훨씬 더 높은 수준의 데이터 바인딩 기능을 제공 합니다. 이 구현은 목록 자체가 변경된 경우(예: 목록 항목 개수의 증가/감소)뿐 아니라 목록 항목이 변경된 경우(예: 고객 목록의 세 번째 항목에서 주소 필드가 변경됨)에도 기본적인 정렬 기능과 변경 알림을 제공합니다. 변경 알림은 여러 컨트롤을 같은 데이터에 바인딩할 때 한 컨트롤의 데이터 변경을 다른 바인딩된 컨트롤에 전파하려는 경우에 중요합니다.  
  
    > [!NOTE]
    >  에 대 한 변경 알림을 사용 하도록 설정할지를 <xref:System.ComponentModel.IBindingList> 인터페이스를 통해를 <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A> 속성은 경우 `true`를 발생 시킵니다를 <xref:System.ComponentModel.IBindingList.ListChanged> 변경 변경 목록 또는 목록의 항목을 나타내는 이벤트를 합니다.  
  
     변경 형식에 의해 설명 됩니다는 <xref:System.ComponentModel.ListChangedType> 의 속성을 <xref:System.ComponentModel.ListChangedEventArgs> 매개 변수입니다. 그러므로 데이터 모델이 업데이트될 때마다 같은 데이터 소스에 바인딩된 다른 컨트롤과 같은 모든 종속 뷰도 업데이트됩니다. 그러나 목록에 포함 된 개체를 발생 시킬 수 있도록이 변경 될 때 목록에 알리기 위해 사항이 <xref:System.ComponentModel.IBindingList.ListChanged> 이벤트입니다.  
  
    > [!NOTE]
    >  합니다 <xref:System.ComponentModel.BindingList%601> 의 제네릭 구현을 제공 합니다 <xref:System.ComponentModel.IBindingList> 인터페이스입니다.  
  
-   <xref:System.ComponentModel.IBindingListView> interface(인터페이스)  
  
     구현 하는 클래스를 <xref:System.ComponentModel.IBindingListView> 인터페이스 구현의 모든 기능을 제공 <xref:System.ComponentModel.IBindingList>, 필터링 및 고급 기능을 정렬 합니다. 이 구현은 문자열 기반 필터링 기능과 속성 설명자 방향 쌍을 사용한 여러 열 정렬 기능을 제공합니다.  
  
-   <xref:System.ComponentModel.IEditableObject> interface(인터페이스)  
  
     구현 하는 클래스는 <xref:System.ComponentModel.IEditableObject> 인터페이스를 사용 하면 해당 개체의 변경 내용을 영구화할 시기를 제어 하는 개체입니다. 이 구현 된 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, 및 <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> 개체에 변경 내용을 롤백할 수 있는 메서드. 다음은 작동에 대해 간략히 설명 합니다 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, 및 <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> 메서드 및 데이터에 대 한 변경 내용을 롤백하기 위해 함께에서 작동 방식:  
  
    -   <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 메서드 개체에 대 한 편집 시작 되었음을 나타냅니다. 이 인터페이스를 구현 하는 개체를 이후의 모든 업데이트를 저장 해야 합니다는 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 업데이트를 삭제할 수 있습니다 하는 방식으로 메서드 호출 하는 경우는 <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> 메서드가 호출 됩니다. 데이터 바인딩 Windows Forms에서에서 호출할 수 있습니다 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 여러 번 단일 범위 내에서 편집 트랜잭션 (예를 들어 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>를 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>). 구현의 <xref:System.ComponentModel.IEditableObject> 여부를 추적 해야 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 에 대 한 후속 호출을 무시 하 고 이미 호출 된 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>합니다. 이 메서드를 여러 번 호출할 수 있습니다, 되므로 이후 호출 하는 비파괴적; 즉, 후속 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 호출에서 적용 된 또는 저장 된 데이터를 변경 하는 업데이트를 제거할 수 없습니다 첫 번째 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 호출 합니다.  
  
    -   합니다 <xref:System.ComponentModel.IEditableObject.EndEdit%2A> 메서드는 이후 모든 변경 내용 푸시 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 개체가 현재 편집 모드의 경우 기본 개체에 호출 되었습니다.  
  
    -   <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> 메서드는 개체에 대 한 변경 내용을 취소 합니다.  
  
     방법에 대 한 자세한 내용은 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, 및 <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> 메서드 작업을 참조 하십시오 [데이터를 데이터베이스에 다시 저장](/visualstudio/data-tools/save-data-back-to-the-database)합니다.  
  
     데이터 기능의 이러한 트랜잭션 개념에서 사용 되는 <xref:System.Windows.Forms.DataGridView> 제어 합니다.  
  
-   <xref:System.ComponentModel.ICancelAddNew> interface(인터페이스)  
  
     구현 하는 클래스를 <xref:System.ComponentModel.ICancelAddNew> 일반적으로 인터페이스를 구현 합니다 <xref:System.ComponentModel.IBindingList> 인터페이스를 사용 하 여 데이터 원본에 대 한 추가 롤백할 수 있습니다는 <xref:System.ComponentModel.IBindingList.AddNew%2A> 메서드. 데이터 원본을 구현 하는 경우는 <xref:System.ComponentModel.IBindingList> 인터페이스를 있어야을 구현할 수는 <xref:System.ComponentModel.ICancelAddNew> 인터페이스입니다.  
  
-   <xref:System.ComponentModel.IDataErrorInfo> interface(인터페이스)  
  
     구현 하는 클래스는 <xref:System.ComponentModel.IDataErrorInfo> 인터페이스를 바인딩된 컨트롤에 사용자 지정 오류 정보를 제공 하는 개체를 사용 합니다.  
  
    -   <xref:System.ComponentModel.IDataErrorInfo.Error%2A> 속성 일반 오류 메시지 텍스트를 반환 합니다 (예를 들어, "오류가 발생 했습니다").  
  
    -   <xref:System.ComponentModel.IDataErrorInfo.Item%2A> 열에서 특정 오류 메시지를 사용 하 여 문자열을 반환 하는 속성 (예를 들어, "값은 `State` 열 올바르지 않습니다.").  
  
-   <xref:System.Collections.IEnumerable> interface(인터페이스)  
  
     구현 하는 클래스를 <xref:System.Collections.IEnumerable> 인터페이스에서 일반적으로 사용 됩니다 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]합니다. 이 인터페이스에 대 한 Windows Forms 지원 까지만 유효 합니다 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다.  
  
    > [!NOTE]
    >  합니다 <xref:System.Windows.Forms.BindingSource> 모든 구성 요소 복사 <xref:System.Collections.IEnumerable> 바인딩할 목적으로 별도 목록 항목입니다.  
  
-   <xref:System.ComponentModel.ITypedList> interface(인터페이스)  
  
     구현 하는 컬렉션 클래스는 <xref:System.ComponentModel.ITypedList> 인터페이스 순서 및 바인딩된 컨트롤에 노출 된 속성 집합을 제어 하는 기능을 제공 합니다.  
  
    > [!NOTE]
    >  구현 하는 경우는 <xref:System.ComponentModel.ITypedList.GetItemProperties%2A> 메서드 및 <xref:System.ComponentModel.PropertyDescriptor> 배열은 null이 아니고, 배열의 마지막 항목이 다른 항목 목록인 목록 속성을 설명 하는 속성 설명자 됩니다.  
  
-   <xref:System.ComponentModel.ICustomTypeDescriptor> interface(인터페이스)  
  
     구현 하는 클래스는 <xref:System.ComponentModel.ICustomTypeDescriptor> 인터페이스 자체에 대 한 동적 정보를 제공 합니다. 이 인터페이스는 비슷합니다 <xref:System.ComponentModel.ITypedList> 하지만 목록이 아닌 개체에 사용 됩니다. 이 인터페이스를 사용해 <xref:System.Data.DataRowView> 기본 행의 스키마를 프로젝트에 있습니다. 간단한 구현을 <xref:System.ComponentModel.ICustomTypeDescriptor> 에서 제공 되는 <xref:System.ComponentModel.CustomTypeDescriptor> 클래스입니다.  
  
    > [!NOTE]
    >  디자인 타임 바인딩을 지원 하기 위해 구현 하는 형식을 <xref:System.ComponentModel.ICustomTypeDescriptor>, 형식을 구현 해야 합니다 <xref:System.ComponentModel.IComponent> 양식에 인스턴스로 존재 합니다.  
  
-   <xref:System.ComponentModel.IListSource> interface(인터페이스)  
  
     구현 하는 클래스는 <xref:System.ComponentModel.IListSource> 인터페이스 목록이 아닌 개체에서 목록 기반 바인딩을 사용 하도록 설정 합니다. 합니다 <xref:System.ComponentModel.IListSource.GetList%2A> 메서드의 <xref:System.ComponentModel.IListSource> 바인딩 가능한 목록에서 상속 되지 않는 개체에서 반환 하는 데 사용 됩니다 <xref:System.Collections.IList>합니다. <xref:System.ComponentModel.IListSource> 사용 되는 <xref:System.Data.DataSet> 클래스입니다.  
  
-   <xref:System.ComponentModel.IRaiseItemChangedEvents> interface(인터페이스)  
  
     구현 하는 클래스를 <xref:System.ComponentModel.IRaiseItemChangedEvents> 인터페이스는 바인딩 가능한 목록을 구현 하는 <xref:System.ComponentModel.IBindingList> 인터페이스입니다. 이 인터페이스 형식이 발생 하는 경우를 나타내기 위해 사용 됩니다 <xref:System.ComponentModel.IBindingList.ListChanged> 형식의 이벤트 <xref:System.ComponentModel.ListChangedType.ItemChanged> 를 통해 해당 <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A> 속성입니다.  
  
    > [!NOTE]
    >  구현 해야 합니다 <xref:System.ComponentModel.IRaiseItemChangedEvents> 데이터 원본에는 앞에서 설명한 이벤트 변환 나열 하는 속성을 제공 하 고 상호 작용 하는 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다. 이 고, 그렇지는 <xref:System.Windows.Forms.BindingSource> 는 성능이 저하 이벤트 변환 나열 하는 속성을 수행할 수도 있습니다.  
  
-   <xref:System.ComponentModel.ISupportInitialize> interface(인터페이스)  
  
     구현 하는 구성 요소는 <xref:System.ComponentModel.ISupportInitialize> 인터페이스 속성을 설정 하 고 상호 종속적인 속성 초기화에 대 한 일괄 처리 최적화가 활용 합니다. <xref:System.ComponentModel.ISupportInitialize> 두 메서드가 포함 되어 있습니다.  
  
    -   <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> 개체 초기화가 시작 됨을 알립니다.  
  
    -   <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> 해당 개체 초기화가 완료 신호를 보냅니다.  
  
-   <xref:System.ComponentModel.ISupportInitializeNotification> interface(인터페이스)  
  
     구현 하는 구성 요소를 <xref:System.ComponentModel.ISupportInitializeNotification> 구현도 인터페이스는 <xref:System.ComponentModel.ISupportInitialize> 인터페이스입니다. 이 인터페이스를 사용 하면 다른에 알리기 위해 <xref:System.ComponentModel.ISupportInitialize> 구성 요소는 초기화가 완료 합니다. <xref:System.ComponentModel.ISupportInitializeNotification> 인터페이스에는 두 멤버가 포함 되어 있습니다.:  
  
    -   <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A> 반환 된 `boolean` 구성 요소가 초기화 되었는지 여부를 나타내는 값입니다.  
  
    -   <xref:System.ComponentModel.ISupportInitializeNotification.Initialized> 발생 경우 <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> 라고 합니다.  
  
-   <xref:System.ComponentModel.INotifyPropertyChanged> interface(인터페이스)  
  
     이 인터페이스를 구현하는 클래스는 해당 속성 값이 변경될 때 이벤트를 발생시키는 형식입니다. 이 인터페이스는 각 컨트롤 속성에서 변경 이벤트를 갖는 패턴을 바꾸는 데 사용됩니다. 에 사용 되는 경우는 <xref:System.ComponentModel.BindingList%601>, 비즈니스 개체를 구현 해야 합니다 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스 및 BindingList\`1은 변환 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 이벤트를 <xref:System.ComponentModel.BindingList%601.ListChanged> 유형의 이벤트 <xref:System.ComponentModel.ListChangedType.ItemChanged>.  
  
    > [!NOTE]
    >  변경에 대 한 알림이 바인딩된 클라이언트와 데이터 간의 바인딩에 발생 하도록 원본에 바인딩된 데이터 소스 형식 중 하나를 구현 해야 합니다 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스 (기본 설정) 하거나 제공할 수 있습니다 *propertyName* `Changed` 바인딩된 형식에 대 한 이벤트는 둘 다는 수행 하지 않아야 합니다.  
  
### <a name="interfaces-for-implementation-by-component-authors"></a>구성 요소 작성자가 구현할 수 있는 인터페이스  
 다음 인터페이스는 Windows Forms 데이터 바인딩 엔진에서 사용됩니다.  
  
-   <xref:System.Windows.Forms.IBindableComponent> interface(인터페이스)  
  
     이 인터페이스를 구현하는 클래스는 컨트롤이 아닌 구성 요소이며 데이터 바인딩을 지원합니다. 이 클래스는 데이터 바인딩 및 바인딩 컨텍스트를 통해 구성 요소를 반환 합니다 <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> 고 <xref:System.Windows.Forms.IBindableComponent.BindingContext%2A> 이 인터페이스의 속성입니다.  
  
    > [!NOTE]
    >  구성 요소에서 상속 하는 경우 <xref:System.Windows.Forms.Control>를 구현할 필요가 없습니다를 <xref:System.Windows.Forms.IBindableComponent> 인터페이스입니다.  
  
-   <xref:System.Windows.Forms.ICurrencyManagerProvider> interface(인터페이스)  
  
     구현 하는 클래스를 <xref:System.Windows.Forms.ICurrencyManagerProvider> 인터페이스는 자체를 제공 하는 구성 <xref:System.Windows.Forms.CurrencyManager> 이 특정 구성 요소와 연결 된 바인딩을 관리 하려면. 사용자 지정에 대 한 액세스 <xref:System.Windows.Forms.CurrencyManager> 에서 제공 되는 <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> 속성입니다.  
  
    > [!NOTE]
    >  상속 된 클래스 <xref:System.Windows.Forms.Control> 바인딩을 통해 자동으로 관리 해당 <xref:System.Windows.Forms.Control.BindingContext%2A> 속성을 구현 해야 하므로 사례는 <xref:System.Windows.Forms.ICurrencyManagerProvider> 모두 아주 드문 경우입니다.  
  
## <a name="see-also"></a>참고자료

- [데이터 바인딩 및 Windows Forms](data-binding-and-windows-forms.md)
- [방법: Windows Form에 단순 바인딩된 컨트롤 만들기](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [Windows Forms 데이터 바인딩](windows-forms-data-binding.md)
