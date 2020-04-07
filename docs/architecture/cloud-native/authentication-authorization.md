---
title: 클라우드 네이티브 앱의 인증 및 권한 부여
description: Azure용 클라우드 네이티브 .NET 앱 설계 | 클라우드 네이티브 앱의 인증 및 권한 부여
ms.date: 03/02/2020
ms.openlocfilehash: 6261a0a72405bc1c984a04a7851aea4dd6664ddf
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805547"
---
# <a name="authentication-and-authorization-in-cloud-native-apps"></a>클라우드 네이티브 앱의 인증 및 권한 부여

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

*인증은* 보안 주체의 ID를 확인하는 프로세스입니다. *권한 부여는* 작업을 수행하거나 리소스에 액세스할 수 있는 인증된 보안 주체 권한을 부여하는 작업입니다. 인증이 로 `AuthN` 단축되고 권한 부여가 `AuthZ`로 단축되는 경우도 있습니다. 클라우드 네이티브 응용 프로그램은 클라이언트와 응용 프로그램이 모든 플랫폼 또는 장치에서 전 세계 어디에서나 실행될 수 있기 때문에 보안 주체를 인증하기 위해 개방형 HTTP 기반 프로토콜에 의존해야 합니다. 유일한 일반적인 요소는 HTTP입니다.

많은 조직에서여전히 ADFS(Active Directory Federation 서비스)와 같은 로컬 인증 서비스에 의존하고 있습니다. 이 접근 방식은 전통적으로 조직에 온프레미스 인증 요구 사항에 적합했지만 클라우드 네이티브 응용 프로그램은 클라우드를 위해 특별히 설계된 시스템의 이점을 활용합니다. 최근 2019년 영국 국가 사이버 보안 센터(NCSC) 권고에 따르면 "Azure AD를 기본 인증 소스로 사용하는 조직은 실제로 ADFS에 비해 위험을 낮출 수 있습니다." [이 분석에](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) 설명된 몇 가지 이유는 다음과 같습니다.

- 전체 Microsoft 자격 증명 보호 기술 집합에 액세스합니다.
- 대부분의 조직은 이미 Azure AD에 어느 정도 의존하고 있습니다.
- NTLM 해시를 두 번 해시하면 로컬 Active Directory에서 작동하는 자격 증명이 허용되지 않습니다.

## <a name="references"></a>참조

- [인증 기본 사항](https://docs.microsoft.com/azure/active-directory/develop/authentication-scenarios)
- [토큰 및 클레임 액세스](https://docs.microsoft.com/azure/active-directory/develop/access-tokens)
- [온-프레미스 인증 서비스를 폐기할 때가 될 수 있습니다.](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
>[이전](identity.md)
>[다음](azure-active-directory.md)
