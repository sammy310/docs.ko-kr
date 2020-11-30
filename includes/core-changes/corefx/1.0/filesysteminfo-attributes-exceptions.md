---
ms.openlocfilehash: 2ea9abca7578c2ddf92712a1c597f8f1ff4a5c0c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032082"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a>FileSystemInfo.Attributes가 throw하는 UnauthorizedAccessException

.NET Core에서 호출자가 파일 특성 값을 설정하려고 하지만 쓰기 권한이 없는 경우 <xref:System.UnauthorizedAccessException>이 throw됩니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Framework에서 호출자가 <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>에서 파일 특성 값을 설정하려고 하지만 쓰기 권한이 없는 경우 <xref:System.ArgumentException>이 throw됩니다. .NET Core에서는 대신 <xref:System.UnauthorizedAccessException>이 throw됩니다. (.NET Core에서 호출자가 잘못된 파일 특성을 설정하려고 시도하는 경우 여전히 <xref:System.ArgumentException>이 throw됩니다.)

#### <a name="version-introduced"></a>도입된 버전

1.0

#### <a name="recommended-action"></a>권장 조치

필요에 따라 <xref:System.ArgumentException> 대신 또는 추가로 <xref:System.UnauthorizedAccessException>을 catch하도록 `catch` 문을 수정합니다.

#### <a name="category"></a>범주

핵심 .NET 라이브러리

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
