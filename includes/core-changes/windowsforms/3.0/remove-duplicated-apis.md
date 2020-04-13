---
ms.openlocfilehash: 0be59258df10aa13920551f011d68bc8efe20b93
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888134"
---
### <a name="duplicated-apis-removed-from-windows-forms"></a>Windows Forms에서 중복된 API가 제거되었습니다.

.Net core 3.0 미리 보기 4부터 <xref:System.Windows.Forms?displayProperty=fullName> 네임스페이스에서 실수로 중복된 많은 API가 .NET Core 3.0 RC1에서 제거되었습니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Core 3.0 미리 보기 4가 <xref:System.ComponentModel.Design?displayProperty=fullName> 네임스페이스에 이미 있던 <xref:System.Windows.Forms?displayProperty=fullName> 네임스페이스의 여러 형식을 잘못 복제했습니다. .NET Core 3.0 RC1부터 이러한 중복된 형식은 더 이상 사용할 수 없습니다. 다음 표에서는 원래 형식과 중복된 형식을 보여줍니다.

> [!div class="mx-tdCol2BreakAll"]
> |원래 형식|중복된 형식|
> |---|---|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventArgs?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventArgs`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventHandler?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventHandler`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedType?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedType`|
> |<xref:System.ComponentModel.Design.DesignerActionUIService?displayProperty=fullName>|`System.Windows.Forms.DesignerActionUIService`|
> |<xref:System.ComponentModel.Design.DesignerCommandSet?displayProperty=fullName>|`System.Windows.Forms.DesignerCommandSet`|

#### <a name="version-introduced"></a>도입된 버전

3.0 RC1

#### <a name="recommended-action"></a>권장 조치

테이블의 **원래 형식** 열에 표시된 대로 원래 형식을 참조하도록 코드를 업데이트합니다.

#### <a name="category"></a>범주

Windows Forms

#### <a name="affected-apis"></a>영향을 받는 API

- 없음

<!--

### Affected APIs

- Not detectable via API analysis.

-->
