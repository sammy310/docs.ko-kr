---
title: ID
description: Azure 용 클라우드 네이티브 .NET 앱 설계 | 신분을
ms.date: 05/13/2020
ms.openlocfilehash: 9fa48977e58e2ca5a5f3e231372a4791640a85fd
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614021"
---
# <a name="identity"></a>ID

대부분의 소프트웨어 응용 프로그램에는 해당 응용 프로그램을 호출 하는 사용자 또는 프로세스에 대 한 지식이 있어야 합니다. 응용 프로그램과 상호 작용 하는 사용자 또는 프로세스를 보안 주체 라고 하며 이러한 보안 주체를 인증 하 고 권한을 부여 하는 프로세스를 id 관리 또는 간단히 *id*라고 합니다. 간단한 응용 프로그램은 응용 프로그램 내에서 모든 id 관리를 포함할 수 있지만이 접근 방식은 많은 응용 프로그램 및 다양 한 종류의 보안 주체를 사용 하 여 제대로 확장 되지 않습니다. Windows에서는 Active Directory를 사용 하 여 중앙 집중식 인증 및 권한 부여를 제공 합니다.

<!-- (insert figure showing Windows AD auth model) -->

이 솔루션은 회사 네트워크 내에서 효과적 이지만 AD 도메인 외부에 있는 사용자 또는 응용 프로그램에서 사용 하도록 설계 되지 않았습니다. 인터넷 기반 응용 프로그램 및 클라우드 네이티브 앱의 증가로 인해 보안 모델이 진화 했습니다.

오늘날의 클라우드 기본 id 모델에서는 아키텍처가 배포 되는 것으로 간주 됩니다. 앱은 어디에서 나 배포할 수 있으며 어디에서 나 다른 앱과 통신할 수 있습니다. 클라이언트는 어디에서 나 이러한 앱과 통신할 수 있습니다. 실제로 클라이언트는 플랫폼과 장치를 조합 하 여 구성할 수 있습니다. 클라우드 기본 id 솔루션은 오픈 표준을 활용 하 여 클라이언트의 보안 응용 프로그램 액세스를 구현 합니다. 이러한 클라이언트는 Pc 또는 휴대폰의 사용자와 전 세계 어디에서 든 모든 소프트웨어 플랫폼을 실행 하는 셋톱 박스 및 IOT 장치에 이르기까지 다양 합니다.

최신 클라우드 네이티브 id 솔루션은 일반적으로 id가 결정 된 후 보안 주체에 게 STS (보안 토큰 서비스/서버)에서 발급 한 액세스 토큰을 활용 합니다. 액세스 토큰 (일반적으로 JWT (JSON Web Token))에는 보안 주체에 대 한 *클레임이* 포함 되어 있습니다. 이러한 클레임에는 최소한 사용자의 id가 포함 되지만 응용 프로그램에서 보안 주체를 부여할 액세스 수준을 결정 하는 데 사용할 수 있는 추가 클레임이 포함 될 수도 있습니다.

<!-- (insert figure showing basic handshake involving a principal, an STS, and an app) -->

일반적으로 STS는 주 서버 인증을 담당 합니다. 리소스에 대 한 액세스 수준을 결정 하는 것은 응용 프로그램의 다른 부분에 남아 있습니다.

## <a name="references"></a>참조

- [Microsoft ID 플랫폼](https://docs.microsoft.com/azure/active-directory/develop/)

>[!div class="step-by-step"]
>[이전](azure-monitor.md)
>[다음](authentication-authorization.md)
