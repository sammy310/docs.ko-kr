---
ms.openlocfilehash: 9f8a790718fbb9d685bb8959808338dc1766bf2c
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021573"
---
### <a name="fieldinfosetvalue-throws-exception-for-static-init-only-fields"></a>FieldInfo.SetValue가 초기화 전용 정적 필드에 대해 예외를 throw

.NET Core 3.0부터 <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>를 호출하여 정적 <xref:System.Reflection.FieldAttributes.InitOnly> 필드에 값을 설정하려고 하면 예외가 throw됩니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Framework 및 3.0 이전 버전의 .NET Core에서는 <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>을 호출하여 초기화 후 상수인 정적 필드의 값을 설정할 수 있습니다([C#의 readonly](~/docs/csharp/language-reference/keywords/readonly.md)). 그러나 이러한 필드를 이 방식으로 설정하면 대상 프레임워크 및 최적화 설정에 따라 예기치 않은 동작이 발생합니다.

.NET Core 3.0 이상 버전에서 정적 <xref:System.Reflection.FieldAttributes.InitOnly> 필드에 <xref:System.Reflection.FieldInfo.SetValue%2A>를 호출하면 <xref:System.FieldAccessException?displayProperty=nameWithType> 예외가 throw됩니다.

> [!TIP]
> <xref:System.Reflection.FieldAttributes.InitOnly> 필드는 선언되는 시점에 또는 포함하는 클래스의 생성자에서만 설정할 수 있는 필드입니다. 즉, 초기화 후에는 상수입니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="recommended-action"></a>권장 조치

정적 생성자에서 정적 <xref:System.Reflection.FieldAttributes.InitOnly> 필드를 초기화합니다. 이는 동적 형식과 비동적 형식 모두에 적용됩니다.

또는 필드에서 <xref:System.Reflection.FieldAttributes.InitOnly?displayProperty=nameWithType> 특성을 제거한 다음 <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=nameWithType>를 호출할 수 있습니다.

#### <a name="category"></a>범주

핵심 .NET 라이브러리

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)?displayProperty=nameWithType>
- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)`
- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)`

-->
