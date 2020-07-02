---
ms.openlocfilehash: 67e3ff5000ebd38064ed8a57e4fe561afa31f8d8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614710"
---
### <a name="long-path-support"></a>긴 경로 지원

#### <a name="details"></a>설명

.NET Framework 4.6.2를 대상으로 하는 앱부터 긴 경로(최대 32K자)가 지원되고 260자(또는 `MAX_PATH`)의 경로 길이 제한이 제거되었습니다. .NET Framework 4.6.2를 대상으로 다시 컴파일된 앱의 경우, 이전에는 260자를 초과했기 때문에 <xref:System.IO.PathTooLongException?displayProperty=fullName>을 throw했던 코드 경로는 이제 다음 조건에서만 <xref:System.IO.PathTooLongException?displayProperty=fullName>을 throw합니다.

- 경로의 길이가 <xref:System.Int16.MaxValue>(32,767)자보다 긴 경우
- 운영 체제가 `COR_E_PATHTOOLONG` 또는 동급을 반환하는 경우
.NET Framework 4.6.1 이하 버전을 대상으로 하는 앱의 경우, 경로가 260자를 초과할 때마다 런타임에서 자동으로 <xref:System.IO.PathTooLongException?displayProperty=fullName>을 throw합니다.

#### <a name="suggestion"></a>제안 해결 방법

.NET Framework 4.6.2를 대상으로 하는 앱의 경우, 필요하지 않으면 `app.config` 파일의 `<runtime>` 섹션에 다음을 추가하여 긴 경로 지원을 옵트아웃할 수 있습니다.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=true" />
</runtime>
```

이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.6.2 이상에서 실행되는 앱의 경우 `app.config` 파일의 `<runtime>` 섹션에 다음 줄을 추가하여 긴 경로 지원을 옵트인할 수 있습니다.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=false" />
</runtime>
```

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.6.2       |
| 형식    | 대상 변경 |
