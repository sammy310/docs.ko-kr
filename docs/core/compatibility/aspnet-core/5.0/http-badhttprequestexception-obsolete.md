---
title: '호환성이 손상되는 변경: HTTP: Kestrel 및 IIS BadHttpRequestException 형식이 사용되지 않는 것으로 표시되고 대체됨'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. HTTP: Kestrel 및 IIS BadHttpRequestException 형식이 사용되지 않는 것으로 표시되고 대체됨'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c51b1dd9d708c04bc1bbcfb65ea2e9daea5330b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759724"
---
# <a name="http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced"></a>HTTP: Kestrel 및 IIS BadHttpRequestException 형식이 사용되지 않는 것으로 표시되고 대체됨

`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` 및 `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`은 사용되지 않는 것으로 표시되며 `Microsoft.AspNetCore.Http.BadHttpRequestException`에서 파생되도록 변경되었습니다. Kestrel 및 IIS 서버는 이전 버전과의 호환성을 위해 이전 예외 형식을 계속 throw합니다. 사용 되지 않는 형식은 이후 릴리스에서 제거될 예정입니다.

자세한 내용은 [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614)를 참조하세요.

## <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 4

## <a name="old-behavior"></a>이전 동작

`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` 및 `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`이 <xref:System.IO.IOException?displayProperty=nameWithType>에서 파생되었습니다.

## <a name="new-behavior"></a>새 동작

`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` 및 `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`는 사용되지 않습니다. 또한 형식은 `System.IO.IOException`에서 파생되는 `Microsoft.AspNetCore.Http.BadHttpRequestException`에서 파생됩니다.

## <a name="reason-for-change"></a>변경 이유

변경 내용:

* 중복된 형식을 통합합니다.
* 여러 서버 구현에서 동작을 통합합니다.

이제 앱은 Kestrel 또는 IIS를 사용할 때 기본 예외 `Microsoft.AspNetCore.Http.BadHttpRequestException`을 catch할 수 있습니다.

## <a name="recommended-action"></a>권장 조치

`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` 및 `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` 사용을 `Microsoft.AspNetCore.Http.BadHttpRequestException`으로 바꿉니다.

## <a name="affected-apis"></a>영향을 받는 API

- [Microsoft.AspNetCore.Server.IIS.BadHttpRequestException](/dotnet/api/microsoft.aspnetcore.server.iis.badhttprequestexception?view=aspnetcore-3.1)
- [Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException](/dotnet/api/microsoft.aspnetcore.server.kestrel.badhttprequestexception?view=aspnetcore-1.1)

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`
- `T:Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`

-->
