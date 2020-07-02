---
ms.openlocfilehash: 2d0798917b639bc90bf3f78f6fb9f19d0eaf2c71
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614820"
---
### <a name="incorrect-implementation-of-memberdescriptorequals"></a>MemberDescriptor.Equals의 잘못된 구현

#### <a name="details"></a>설명

<xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> 메서드의 원래 구현은 비교되는 개체의 두 가지 문자열 속성을 비교합니다. 즉, 범주 이름과 설명 문자열입니다. 수정은 첫 번째 개체의 <xref:System.ComponentModel.MemberDescriptor.Category>를 두 번째의 <xref:System.ComponentModel.MemberDescriptor.Category>와 비교하고, 첫 번째의 <xref:System.ComponentModel.MemberDescriptor.Description>을 두 번째의 <xref:System.ComponentModel.MemberDescriptor.Description>과 비교하는 것입니다.

#### <a name="suggestion"></a>제안 해결 방법

애플리케이션이 <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType>에 종속되어 있고 설명자가 동일할 때 `false`를 반환하는 경우 및 .NET Framework 4.6.2 이상 버전을 대상으로 하는 경우에 몇 가지 옵션이 있습니다.

- <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> 메서드를 호출하는 것 외에도 <xref:System.ComponentModel.MemberDescriptor.Category> 및 <xref:System.ComponentModel.MemberDescriptor.Description> 필드를 수동으로 비교하도록 코드를 변경합니다.
- app.config 파일에 다음 값을 추가하여 이러한 변경 내용을 옵트아웃합니다.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true" />
</runtime>
```

애플리케이션이 .NET Framework 4.6.1 이하를 대상으로 하고 .NET Framework 4.6.2 이상에서 실행되는 경우 이 변경 내용을 활성화하려면 app.config 파일에 다음 값을 추가하여 호환성 스위치를 `false`로 설정하면 됩니다.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=false" />
</runtime>
```

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.6.2       |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.ComponentModel.MemberDescriptor.Equals(System.Object)?displayProperty=nameWithType>
