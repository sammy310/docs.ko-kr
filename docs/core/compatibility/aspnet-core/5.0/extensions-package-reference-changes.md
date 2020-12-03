---
title: '호환성이 손상되는 변경: 확장: 일부 NuGet 패키지에 영향을 주는 패키지 참조 변경 내용'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. 확장: 일부 NuGet 패키지에 영향을 주는 패키지 참조 변경 내용'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 4a525d9f7aad4409fd507fcf80c00968ff4b63d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759727"
---
# <a name="extensions-package-reference-changes-affecting-some-nuget-packages"></a>확장: 일부 NuGet 패키지에 영향을 주는 패키지 참조 변경 내용

[aspnet/Announcements#411](https://github.com/aspnet/Announcements/issues/411)에 설명된 대로 [dotnet/extensions](https://github.com/dotnet/extensions) 리포지토리에서 [dotnet/runtime](https://github.com/dotnet/runtime)으로 일부 `Microsoft.Extensions.*` NuGet 패키지를 마이그레이션하면 패키징 변경 내용이 마이그레이션된 일부 패키지에 적용됩니다. 이 문제에 관한 자세한 내용은 [dotnet/aspnetcore#21033](https://github.com/dotnet/aspnetcore/issues/21033)을 참조하세요.

## <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 4

## <a name="old-behavior"></a>이전 동작

일부 `Microsoft.Extensions.*` 패키지에는 앱이 사용하는 API의 패키지 참조가 포함되었습니다.

## <a name="new-behavior"></a>새 동작

앱이 `Microsoft.Extensions.*` 패키지 종속성을 추가해야 할 수 있습니다.

## <a name="reason-for-change"></a>변경 이유

*dotnet/runtime* 리포지토리에 더 잘 맞도록 패키징 정책이 업데이트되었습니다. 새 정책에 따라 사용되지 않는 패키지 참조는 패키징 중에 *.nupkg* 파일에서 제거됩니다.

## <a name="recommended-action"></a>권장 조치

제거된 패키지 종속성의 API를 사용하는 경우 영향을 받는 패키지의 소비자는 프로젝트에서 제거된 패키지 종속성에 대한 직접 종속성을 추가해야 합니다. 다음 표에는 영향을 받는 패키지와 해당 변경 내용이 나와 있습니다.

|패키지 이름|변경 내용 설명|
|------------|------------------|
|[Microsoft.Extensions.Configuration.Binder](https://nuget.org/packages/Microsoft.Extensions.Configuration.Binder)|`Microsoft.Extensions.Configuration`에 대한 참조가 제거됨|
|[Microsoft.Extensions.Configuration.Json](https://nuget.org/packages/Microsoft.Extensions.Configuration.Json)    |`System.Threading.Tasks.Extensions`에 대한 참조가 제거됨|
|[Microsoft.Extensions.Hosting.Abstractions](https://nuget.org/packages/Microsoft.Extensions.Hosting.Abstractions)|`Microsoft.Extensions.Logging.Abstractions`에 대한 참조가 제거됨|
|[Microsoft.Extensions.Logging](https://nuget.org/packages/Microsoft.Extensions.Logging)                          |`Microsoft.Extensions.Configuration.Binder`에 대한 참조가 제거됨|
|[Microsoft.Extensions.Logging.Console](https://nuget.org/packages/Microsoft.Extensions.Logging.Console)          |`Microsoft.Extensions.Configuration.Abstractions`에 대한 참조가 제거됨|
|[Microsoft.Extensions.Logging.EventLog](https://nuget.org/packages/Microsoft.Extensions.Logging.EventLog)        |.NET Framework 4.6.1 대상 프레임워크 모니커의 `System.Diagnostics.EventLog`에 대한 참조가 제거됨|
|[Microsoft.Extensions.Logging.EventSource](https://nuget.org/packages/Microsoft.Extensions.Logging.EventSource)  |`System.Threading.Tasks.Extensions`에 대한 참조가 제거됨|
|[Microsoft.Extensions.Options](https://nuget.org/packages/Microsoft.Extensions.Options)                          |`System.ComponentModel.Annotations`에 대한 참조가 제거됨|

예를 들어 `Microsoft.Extensions.Configuration`에 대한 패키지 참조가 `Microsoft.Extensions.Configuration.Binder`에서 제거되었습니다. 종속성의 API가 패키지에서 사용되지 않았습니다. `Microsoft.Extensions.Configuration`의 API를 사용하는 `Microsoft.Extensions.Configuration.Binder`의 사용자는 프로젝트에서 이에 대한 직접 참조를 추가해야 합니다.

## <a name="affected-apis"></a>영향을 받는 API

없음

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
