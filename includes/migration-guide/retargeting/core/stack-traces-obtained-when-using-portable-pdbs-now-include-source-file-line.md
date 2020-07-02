---
ms.openlocfilehash: c7500550cd9714a9788a7dea68af04823f000f7f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614795"
---
### <a name="stack-traces-obtained-when-using-portable-pdbs-now-include-source-file-and-line-information-if-requested"></a>휴대용 PDB를 사용할 때 가져온 스택 추적은 이제 요청된 경우 원본 파일 및 줄 정보를 포함합니다.

#### <a name="details"></a>설명

.NET Framework 4.7.2부터 휴대용 PDB를 사용할 때 가져온 스택 추적은 요청된 경우 원본 파일 및 줄 정보를 포함합니다. .NET Framework 4.7.2 이전 버전에서 명시적으로 요청된 경우에도 휴대용 PDB를 사용할 때 원본 파일 및 줄 정보를 사용할 수 없습니다.

#### <a name="suggestion"></a>제안 해결 방법

.NET Framework 4.7.2를 대상으로 하는 애플리케이션의 경우, 필요하지 않으면 `app.config` 파일의 `<runtime>` 섹션에 다음을 추가하여 휴대용 PDB를 사용할 때 원본 파일 및 줄 정보를 옵트아웃할 수 있습니다.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=true" />
</runtime>
```

이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.7.2 이상에서 실행되는 애플리케이션의 경우 `app.config` 파일의 `<runtime>` 섹션에 다음을 추가하여 휴대용 PDB를 사용할 때 원본 파일 및 줄 정보를 옵트인할 수 있습니다.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=false" />
</runtime>
```

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.7.2       |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Diagnostics.StackTrace.%23ctor(System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Int32,System.Boolean)>
