---
title: 클라우드 네이티브 앱의 인증 및 권한 부여
description: Azure 용 클라우드 네이티브 .NET 앱 설계 | 클라우드 네이티브 앱의 인증 및 권한 부여
ms.date: 06/30/2019
ms.openlocfilehash: a397175e98c2e8103d2a8c372c81fcca65f19b11
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840750"
---
# <a name="authentication-and-authorization-in-cloud-native-apps"></a>클라우드 네이티브 앱의 인증 및 권한 부여

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

*인증은* 보안 주체의 id를 확인 하는 프로세스입니다. *권한 부여* 는 인증 된 보안 주체에 게 작업을 수행 하거나 리소스에 액세스할 수 있는 권한을 부여 하는 동작입니다. 경우에 따라 인증을 `AuthN` 하 고 권한 부여를 `AuthZ`으로 줄일 수 있습니다. 클라우드 네이티브 응용 프로그램은 오픈 HTTP 기반 프로토콜을 사용 하 여 모든 플랫폼 또는 장치에서 전 세계 어디에서 든 클라이언트와 응용 프로그램을 실행할 수 있기 때문에 보안 주체를 인증 해야 합니다. 유일한 일반적인 요소는 HTTP입니다.

대부분의 조직에서는 Active Directory Federation Services (ADFS)와 같은 로컬 인증 서비스를 계속 사용 합니다. 이 접근 방식에서는 온-프레미스 인증 요구 사항에 대해 전통적으로 제공 되는 조직을 제공 하지만 클라우드 네이티브 응용 프로그램은 클라우드 용으로 특별히 설계 된 시스템을 활용 합니다. 최근 2019 영국 NCSC (국립 사이버 Security Center) 권고는 "Azure AD를 기본 인증 원본으로 사용 하는 조직이 ADFS와 비교 하 여 실제로 위험을 낮추는 것을 말합니다." [이 분석](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) 에서 설명 하는 몇 가지 이유는 다음과 같습니다.

- Microsoft 자격 증명 보호 기술의 전체 집합에 액세스할 수 있습니다.
- 대부분의 조직에서는 Azure AD를 어느 정도까지 이미 의존 하 고 있습니다.
- NTLM 해시를 이중으로 해시 하면 손상으로 인해 로컬 Active Directory에서 작동 하는 자격 증명이 허용 되지 않습니다.

## <a name="references"></a>참조 항목

- [인증 기본 사항](https://docs.microsoft.com/azure/active-directory/develop/authentication-scenarios)
- [액세스 토큰 및 클레임](https://docs.microsoft.com/azure/active-directory/develop/access-tokens)
- [온-프레미스 인증 서비스를 버릴 시간이 걸릴 수 있습니다.](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
>[이전](identity.md)
>[다음](azure-active-directory.md)
