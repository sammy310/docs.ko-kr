---
title: GRPC 응용 프로그램의 보안 - WCF 개발자를 위한 gRPC
description: gRPC의 통화 및 채널 인증 및 권한 부여 개요.
ms.date: 09/02/2019
ms.openlocfilehash: 70cbf441bbc1b299b997f7d1f02bcd2bf7fde60c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147817"
---
# <a name="security-in-grpc-applications"></a>gRPC 애플리케이션의 보안

모든 실제 시나리오에서 응용 프로그램 및 서비스를 보호하는 것은 필수적입니다. 보안은 세 가지 주요 영역을 다룹니다.

* 악의적인 해커가 네트워크 트래픽을 가로채는 것을 방지하기 위해 네트워크 트래픽을 암호화합니다.
* ID와 신뢰를 구축하기 위해 클라이언트와 서버를 인증합니다.
* 클라이언트가 시스템에 대한 액세스를 제어하고 ID를 기반으로 권한을 적용할 수 있도록 권한을 부여합니다.

> [!NOTE]
> *인증은* 클라이언트 또는 서버의 ID를 설정하는 데 중요합니다. *권한 부여는* 클라이언트가 리소스에 액세스하거나 명령을 발급할 수 있는 권한이 있는지 여부를 결정하는 데 중요합니다.

이 장에서는 ASP.NET 코어에 대한 gRPC의 인증 및 권한 부여 기능을 다룹니다. 또한 TLS 암호화 된 연결을 통해 네트워크 보안에 대해 설명합니다.

## <a name="wcf-authentication-and-authorization"></a>WCF 인증 및 권한 부여

WCF(Windows 통신 재단)에서는 사용 중인 전송 및 바인딩에 따라 인증 및 권한 부여가 여러 가지 방식으로 처리되었습니다. WCF는 다양한\* WS-보안 표준을 지원했습니다. 또한 Windows 시스템 간에 IIS 또는 NetTCP 서비스에서 실행되는 HTTP 서비스에 대한 Windows 인증을 지원했습니다.

## <a name="grpc-authentication-and-authorization"></a>gRPC 인증 및 권한 부여

gRPC 인증 및 권한 부여는 다음 두 가지 수준에서 작동합니다.

* 통화 수준 인증/권한 부여는 일반적으로 호출이 이루어질 때 메타데이터에 적용되는 토큰을 통해 처리됩니다.
* 채널 수준 인증은 연결 수준에서 적용되는 클라이언트 인증서를 사용합니다. 또한 채널의 모든 통화에 자동으로 적용할 호출 수준 인증/권한 부여 자격 증명을 포함할 수도 있습니다.

이러한 메커니즘 중 하나 또는 둘 다를 사용하여 서비스를 보호할 수 있습니다.

gRPC의 ASP.NET 코어 구현은 대부분의 표준 ASP.NET 핵심 메커니즘을 통해 인증 및 권한 부여를 지원합니다.

- 통화 인증
  - Azure Active Directory
  - 아이덴티티 서버
  - JWT 베어러 토큰
  - OAuth 2.0
  - OpenID Connect
  - WS-Federation
- 채널 인증
  - 클라이언트 인증서

호출 인증 메서드는 모두 토큰을 기반으로 *합니다.* 유일한 차이점은 토큰이 생성되는 방법과 ASP.NET Core 서비스에서 토큰의 유효성을 검사하는 데 사용되는 라이브러리입니다.

자세한 내용은 인증 [및 권한 부여](/aspnet/core/grpc/authn-and-authz) 문서를 참조하세요.

> [!NOTE]
> TLS 암호화 된 HTTP/2 연결을 통해 gRPC를 사용하는 경우 채널 수준 인증을 사용하지 않더라도 클라이언트와 서버 간의 모든 트래픽이 암호화됩니다.

이 장에서는 gRPC 서비스에 통화 자격 증명 및 채널 자격 증명을 적용하는 방법을 보여 줄 것입니다. 또한 .NET Core gRPC 클라이언트의 자격 증명을 사용하여 서비스를 인증하는 방법도 보여 줍니다.

>[!div class="step-by-step"]
>[이전](client-libraries.md)
>[다음](call-credentials.md)
