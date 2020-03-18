---
ms.openlocfilehash: 4091bdcf7d9ed8872aed5faa6e6d3ed143903787
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449407"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a>FileSystemInfo.Attributes가 throw하는 UnauthorizedAccessException

.NET Core에서 호출자가 파일 특성 값을 설정하려고 하지만 쓰기 권한이 없는 경우 <xref:System.UnauthorizedAccessException>이 throw됩니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Framework에서 호출자가 <xref:System.ArgumentException>에서 파일 특성 값을 설정하려고 하지만 쓰기 권한이 없는 경우 <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>이 throw됩니다. .NET Core에서는 대신 <xref:System.UnauthorizedAccessException>이 throw됩니다. (.NET Core에서 호출자가 잘못된 파일 특성을 설정하려고 시도하는 경우 여전히 <xref:System.ArgumentException>이 throw됩니다.)

#### <a name="version-introduced"></a>도입된 버전

1.0

#### <a name="recommended-action"></a>권장 조치

필요에 따라 `catch` 대신 또는 추가로 <xref:System.UnauthorizedAccessException>을 catch하도록 <xref:System.ArgumentException> 문을 수정합니다.

#### <a name="category"></a>범주

CoreFx

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
