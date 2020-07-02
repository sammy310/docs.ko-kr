---
ms.openlocfilehash: f4ff938b2d0e9ead481fdf239aed8a6b918a99b0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620451"
---
### <a name="listboxitem-isselected-binding-issue-with-observablecollectionlttgtmove"></a>ObservableCollection&lt;T&gt;.Move의 ListBoxItem IsSelected 바인딩 문제

#### <a name="details"></a>설명

선택한 항목을 사용하여 <xref:System.Windows.Controls.ListBox?displayProperty=fullName>에 바인딩된 컬렉션에서 <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> 또는 <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)>을 호출하면 이후에 <xref:System.Windows.Controls.ListBox?displayProperty=fullName> 항목을 선택하거나 선택 취소할 때 비정상적인 동작이 발생할 수 있습니다.

#### <a name="suggestion"></a>제안 해결 방법

<xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> 대신 <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> 및 <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName>을 호출하면 이 문제가 해결됩니다. 또는 .NET Framework 4.6에서 이 문제가 수정되어 해당 버전의 .NET Framework로 업그레이드하여 해결할 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |부|
|버전|4.5|
|형식|런타임

#### <a name="affected-apis"></a>영향을 받는 API

-<xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|
