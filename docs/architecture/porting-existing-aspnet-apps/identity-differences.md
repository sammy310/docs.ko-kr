---
title: ASP.NET Identity 및 ASP.NET Core Id 비교
description: 이 섹션에서는 .NET Framework에서 .NET Core로의 마이그레이션을 계획할 때 특히 중요 한 ASP.NET Identity와 ASP.NET Core Id의 차이점을 살펴봅니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 184c0e7c872b7676530b917727f380d6735ba10a
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401760"
---
# <a name="compare-aspnet-identity-and-aspnet-core-identity"></a>ASP.NET Identity 및 ASP.NET Core Id 비교

ASP.NET MVC에서 id 기능은 일반적으로 *App_Start* 폴더의 *IdentityConfig.cs* 에서 구성 됩니다. 기존 앱에서 구성 된 방법을 검토 하 고 *Startup.cs* 의 [id ASP.NET Core에 필요한 구성과](/aspnet/core/security/authentication/identity-configuration) 비교 합니다.

ASP.NET Identity은 사용자 인터페이스 로그인 기능을 지원 하 고 사용자, 암호, 프로필 데이터, 역할, 클레임, 토큰, 전자 메일 확인 등을 관리 하는 API입니다. Facebook, Google, Microsoft, Twitter 등의 외부 로그인 공급자를 지원 합니다.

ASP.NET MVC 앱이 ASP.NET 멤버 자격을 사용 하는 경우 [ASP.NET membership authentication에서 ASP.NET Core 2.0 id로 마이그레이션하기](/aspnet/core/migration/proper-to-2x/membership-to-core-identity)위한 가이드를 찾을 수 있습니다. 이는 주로 마이그레이션된 사용자 레코드를 사용 하 여 ASP.NET Core Id를 사용할 수 있어야 하는 데이터 마이그레이션 연습입니다.

ASP.NET Identity 사용자를 ASP.NET Core Id로 마이그레이션하는 경우 암호 해시를 업데이트 하거나, 새 ASP.NET Core Id 접근 방식이 나 이전 ASP.NET Identity 방법으로 해시 된 암호를 추적 해야 할 수 있습니다. [Stack Overflow에 설명 된이 방법은](https://stackoverflow.com/a/57074910/13729) 한 번에 모두 사용 하는 것이 아니라 시간에 따라 사용자 암호 해시를 마이그레이션하기 위한 몇 가지 옵션을 제공 합니다.

ASP.NET Identity와 비교할 때 가장 큰 차이점 중 하나는 프로젝트에 포함 해야 하는 코드의 양을 ASP.NET Core 하는 것입니다. 이제 ASP.NET Core Id는 Razor 클래스 라이브러리로 제공 됩니다. 즉, 해당 UI 및 논리는 모두 NuGet 패키지에서 사용할 수 있습니다. [ASP.NET Core id 파일의 스 캐 폴딩](/aspnet/core/security/authentication/scaffold-identity) 으로 기존 UI와 논리를 재정의할 수 있지만,이 경우에는 자신이 존재 하는 것이 아니라 수정 하려는 페이지만 스 캐 폴드 해야 합니다.

## <a name="migrate-from-owin--katana"></a>OWIN/Katana에서 마이그레이션

다음 리소스는 OWIN/Katana에서 마이그레이션하는 방법에 대 한 몇 가지 지침을 제공 합니다.

- [마이그레이션](/aspnet/core/migration/proper-to-2x/#globalasax-file-replacement)
- [Katana을 ASPNET 5로](https://devblogs.microsoft.com/aspnet/katana-asp-net-5-and-bridging-the-gap/)

## <a name="references"></a>참조

- [ASP.NET Core 인증 및 Id 마이그레이션](/aspnet/core/migration/identity)
- [ASP.NET Core의 Id 소개](/aspnet/core/security/authorization/introduction)
- [ASP.NET Core Id 구성](/aspnet/core/security/authentication/identity-configuration)
- [ASP.NET Core 프로젝트의 스 캐 폴드 Id](/aspnet/core/security/authentication/scaffold-identity)

>[!div class="step-by-step"]
>[이전](authentication-differences.md)
>[다음](controller-differences.md)
