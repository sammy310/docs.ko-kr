---
ms.openlocfilehash: a54b17b2002bd0f85b8b47c5e37e040470d6c494
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621333"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>더 이상 리플렉션 개체를 관리 코드에서 out-of-process DCOM 클라이언트로 전달할 수 없습니다

#### <a name="details"></a>세부 정보

더이상 리플렉션 개체를 관리 코드에서 out-of-process DCOM 클라이언트로 전달할 수 없습니다. 다음 형식이 영향을 받습니다.<ul><li><xref:System.Reflection.Assembly?displayProperty=fullName></li><li><xref:System.Reflection.MemberInfo?displayProperty=fullName>(및 <xref:System.Reflection.FieldInfo?displayProperty=fullName>,<xref:System.Reflection.MethodInfo?displayProperty=fullName>,<xref:System.Type?displayProperty=fullName> 및 <xref:System.Reflection.TypeInfo?displayProperty=fullName>을 포함한 파생된 형식)</li><li><xref:System.Reflection.MethodBody?displayProperty=fullName></li><li><xref:System.Reflection.Module?displayProperty=fullName></li><li><xref:System.Reflection.ParameterInfo?displayProperty=fullName>.</li></ul>개체에 대한 <code>IMarshal</code>을 호출하면 <code>E_NOINTERFACE</code>를 반환합니다.

#### <a name="suggestion"></a>제안 해결 방법

마샬링 코드를 리플렉션이 아닌 개체를 사용하도록 업데이트

| 이름    | 값       |
|:--------|:------------|
| Scope   |부|
|버전|4.6|
|형식|런타임|
