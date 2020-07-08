---
ms.openlocfilehash: 35fc4782ebbba33f5fc6668712af9d89d00cafe9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614974"
---
### <a name="wpf-changing-a-primary-key-when-displaying-ado-data-in-a-masterdetail-scenario"></a>마스터/세부 정보 시나리오에서 ADO 데이터를 표시할 때 기본 키를 변경하는 WPF

#### <a name="details"></a>설명

`Order` 형식 항목의 ADO 컬렉션이 있고 기본 키 &quot;OrderID&quot;를 통해 ADO 컬렉션을 `Detail` 형식 항목의 컬렉션에 연결하는 &quot;OrderDetails&quot;라는 관계가 있다고 가정합니다. WPF 앱에서 목록 컨트롤을 지정된 순서에 대한 세부 정보에 바인딩할 수 있습니다.

```xaml
<ListBox ItemsSource="{Binding Path=OrderDetails}" >
```

DataContext가 `Order`인 경우. WPF는 `OrderID`가 마스터 항목의 `OrderID`와 일치하는 모든 `Detail` 항목의 컬렉션 D인 `OrderDetails` 속성 값을 가져옵니다. 마스터 항목의 기본 키 `OrderID`를 변경하면 동작 변경이 발생합니다. ADO는 세부 정보 컬렉션에 있는 영향을 받는 각 레코드(컬렉션 D로 복사된 레코드)의 `OrderID`를 자동으로 변경합니다.  하지만 D는 어떻게 처리될까요?

- 이전 동작: 컬렉션 D가 지워집니다. 마스터 항목이 `OrderDetails` 속성에 대한 변경 알림을 표시하지 *않습니다*. ListBox가 현재 비어 있는 컬렉션 D를 계속 사용합니다.
- 새 동작:  컬렉션 D가 변경되지 않습니다. 각 항목이 `OrderID` 속성에 대한 변경 알림을 표시합니다. ListBox가 컬렉션 D를 계속 사용하고 새 `OrderID`와 함께 세부 정보를 표시합니다. WPF는 `followParent` 인수를 `true`로 설정하고 ADO 메서드 <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType>를 호출하는 다른 방법으로 컬렉션 D를 만들어 새 동작을 구현합니다.

#### <a name="suggestion"></a>제안 해결 방법

앱은 다음 AppContext 스위치를 사용하여 새 동작을 가져옵니다.

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Data.DoNotUseFollowParentWhenBindingToADODataRelation=false"/>
  </runtime>
</configuration>
```

스위치는 기본적으로 .NET 4.7.1 이하를 대상으로 하는 앱의 경우 `true`(이전 동작)로 설정되고, .NET 4.7.2 이상을 대상으로 하는 앱의 경우 `false`(새 동작)로 설정됩니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.7.2       |
| 형식    | 대상 변경 |
