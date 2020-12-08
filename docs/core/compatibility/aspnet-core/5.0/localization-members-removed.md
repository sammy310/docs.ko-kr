---
title: '호환성이 손상되는 변경: 지역화: ResourceManagerWithCultureStringLocalizer 클래스 및 WithCulture 인터페이스 멤버가 제거됨'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. 지역화: ResourceManagerWithCultureStringLocalizer 클래스 및 WithCulture 인터페이스 멤버가 제거됨'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: ac7723cd9b961b34b3f87a55119d421668c87417
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96437851"
---
# <a name="localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed"></a>지역화: ResourceManagerWithCultureStringLocalizer 클래스 및 WithCulture 인터페이스 멤버가 제거됨

[ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) 클래스 및 [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) 메서드가 .NET 5.0 미리 보기 1에서 제거되었습니다.

컨텍스트는 [aspnet/Announcements#346](https://github.com/aspnet/Announcements/issues/346) 및 [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324)를 참조하세요. 이 문제에 관한 자세한 내용은 [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756)을 참조하세요.

## <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 1

## <a name="old-behavior"></a>이전 동작

`ResourceManagerWithCultureStringLocalizer` 클래스 및 `ResourceManagerStringLocalizer.WithCulture` 메서드는 [.NET Core 3.0 미리 보기 3 이상에서 사용되지 않습니다](../../3.0.md#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete).

## <a name="new-behavior"></a>새 동작

`ResourceManagerWithCultureStringLocalizer` 클래스 및 `ResourceManagerStringLocalizer.WithCulture` 메서드는 .NET 5.0 미리 보기 1에서 제거되었습니다. 변경된 내용의 인벤토리는 [dotnet/extensions#2562](https://github.com/dotnet/extensions/pull/2562/files)에서 끌어오기 요청을 참조하세요.

## <a name="reason-for-change"></a>변경 이유

[ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) 클래스 및 [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) 메서드는 사용자가 지역화에 관해 혼란스러워하는 원인이기도 했습니다. 특히 사용자 지정 <xref:Microsoft.Extensions.Localization.IStringLocalizer> 구현을 만들 때 크게 혼란스러워했습니다. 이 클래스와 메서드는 소비자가 `IStringLocalizer` 인스턴스가 “언어별, 리소스별”이어야 한다는 인상을 줍니다. 실제로 인스턴스는 “리소스별”이어야 합니다. 런타임에 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> 속성은 사용할 언어를 결정합니다.

## <a name="recommended-action"></a>권장 조치

`ResourceManagerWithCultureStringLocalizer` 클래스 및 `ResourceManagerStringLocalizer.WithCulture` 메서드 사용을 중지합니다.

## <a name="affected-apis"></a>영향을 받는 API

- [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1)
- [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1)

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
