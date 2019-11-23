---
title: GRPC 응용 프로그램의 보안-WCF 개발자를 위한 gRPC
description: GRPC의 호출 및 채널 인증 및 권한 부여에 대 한 개요입니다.
ms.date: 09/02/2019
ms.openlocfilehash: b88ed0c01d1ca4432c7e4fe7115246f4227159df
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967247"
---
# <a name="security-in-grpc-applications"></a>gRPC 애플리케이션의 보안

모든 실제 시나리오에서는 응용 프로그램 및 서비스를 보호 하는 것이 필수적입니다. 보안은 잘못 된 행위자가 가로챌 수 없도록 네트워크 트래픽 암호화의 세 가지 주요 영역을 다룹니다. 클라이언트 및 서버를 인증 하 여 id 및 트러스트 설정 클라이언트에서 시스템에 대 한 액세스를 제어 하 고 id를 기준으로 권한을 적용 하도록 권한을 부여 합니다.

> [!NOTE]
> **인증은** 클라이언트 또는 서버의 id를 설정 하는 것과 관련이 있습니다. **권한 부여** 는 클라이언트에 리소스에 대 한 액세스 권한이 있는지 여부를 확인 하거나 명령을 실행할 수 있습니다.

이 장에서는 ASP.NET Core에 대 한 gRPC의 인증 및 권한 부여 기능에 대해 설명 하 고 TLS 암호화 연결을 사용 하 여 네트워크 보안에 대해 설명 합니다.

## <a name="wcf-authentication-and-authorization"></a>WCF 인증 및 권한 부여

WCF에서 인증 및 권한 부여는 사용 되는 전송 및 바인딩에 따라 서로 다른 방식으로 처리 되었습니다. WCF는 IIS에서 실행 되는 HTTP 서비스에 대 한 Windows 인증 및 Windows 시스템 간에 다양 한 WS\* 보안 표준 및 Windows 인증을 지원 합니다.

## <a name="grpc-authentication-and-authorization"></a>gRPC 인증 및 권한 부여

gRPC 인증 및 권한 부여는 두 수준에서 작동 합니다. 호출 수준 인증/권한 부여는 일반적으로 호출이 수행 될 때 메타 데이터에 적용 되는 토큰을 사용 하 여 처리 됩니다. 채널 수준 인증은 연결 수준에서 적용 되는 클라이언트 인증서를 사용 하며, 채널의 모든 호출에 자동으로 적용 되는 호출 수준 인증/권한 부여 자격 증명을 포함할 수도 있습니다. 이러한 메커니즘 중 하나 또는 둘 모두를 사용 하 여 서비스를 보호할 수 있습니다.

GRPC의 ASP.NET Core 구현에서는 대부분의 표준 ASP.NET Core 메커니즘을 사용 하 여 인증 및 권한 부여를 지원 합니다.

- 인증 호출
  - Azure Active Directory
  - IdentityServer
  - JWT 전달자 토큰
  - OAuth 2.0
  - Openid connect 연결
  - WS-Federation
- 채널 인증
  - 클라이언트 인증서

호출 인증 방법은 모두 *토큰*을 기반으로 합니다. 유일한 차이점은 토큰을 생성 하는 방법과 ASP.NET Core 서비스에서 토큰의 유효성을 검사 하는 데 사용 되는 라이브러리입니다.

자세한 내용은 [Microsoft Docs의 인증 및 권한 부여 설명서](https://docs.microsoft.com/aspnet/core/grpc/authn-and-authz?view=aspnetcore-3.0)를 참조 하세요.

> [!NOTE]
> TLS로 암호화 된 HTTP/2 연결에서 gRPC를 사용할 때 채널 수준 인증을 사용 하지 않는 경우에도 클라이언트와 서버 간의 모든 트래픽이 암호화 됩니다.

이 장에서는 gRPC 서비스에 통화 자격 증명과 채널 자격 증명을 적용 하는 방법과 .NET Core gRPC 클라이언트의 자격 증명을 사용 하 여 서비스에 인증 하는 방법을 보여 줍니다.

>[!div class="step-by-step"]
>[이전](client-libraries.md)
>[다음](call-credentials.md)
