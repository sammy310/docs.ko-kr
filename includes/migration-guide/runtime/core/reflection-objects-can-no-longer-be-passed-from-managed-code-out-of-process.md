---
ms.openlocfilehash: f011f6ebe0fa85a59f3e69c93bba9eddc4c1689b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496908"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>더 이상 리플렉션 개체를 관리 코드에서 out-of-process DCOM 클라이언트로 전달할 수 없습니다

#### <a name="details"></a>세부 정보

더이상 리플렉션 개체를 관리 코드에서 out-of-process DCOM 클라이언트로 전달할 수 없습니다. 다음 형식이 영향을 받습니다.

- <xref:System.Reflection.Assembly?displayProperty=fullName>
- <xref:System.Reflection.MemberInfo?displayProperty=fullName>(및 <xref:System.Reflection.FieldInfo?displayProperty=fullName>,<xref:System.Reflection.MethodInfo?displayProperty=fullName>,<xref:System.Type?displayProperty=fullName> 및 <xref:System.Reflection.TypeInfo?displayProperty=fullName>을 포함한 파생된 형식)
- <xref:System.Reflection.MethodBody?displayProperty=fullName>
- <xref:System.Reflection.Module?displayProperty=fullName>
- <xref:System.Reflection.ParameterInfo?displayProperty=fullName>

개체에 대한 <code>IMarshal</code>을 호출하면 <code>E_NOINTERFACE</code>를 반환합니다.

#### <a name="suggestion"></a>제안 해결 방법

비리플렉션 개체에서 작동하도록 마샬링 코드를 업데이트합니다.

| Name    | 값       |
|:--------|:------------|
| Scope   |부|
|버전|4.6|
|형식|런타임|

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Reflection.Assembly?displayProperty=fullName>
- <xref:System.Reflection.FieldInfo?displayProperty=fullName>
- <xref:System.Reflection.MemberInfo?displayProperty=fullName>
- <xref:System.Reflection.MethodBody?displayProperty=fullName>
- <xref:System.Reflection.MethodInfo?displayProperty=fullName>
- <xref:System.Reflection.Module?displayProperty=fullName>
- <xref:System.Reflection.ParameterInfo?displayProperty=fullName>
- <xref:System.Reflection.TypeInfo?displayProperty=fullName>
- <xref:System.Type?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Reflection.Assembly`
- `T:System.Reflection.FieldInfo`
- `T:System.Reflection.MemberInfo`
- `T:System.Reflection.MethodBody`
- `T:System.Reflection.MethodInfo`
- `T:System.Reflection.Module`
- `T:System.Reflection.ParameterInfo`
- `T:System.Reflection.TypeInfo`
- `T:System.Type`

-->
