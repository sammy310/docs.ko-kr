---
title: WCF에서 사용되는 보안 개념
ms.date: 03/30/2017
ms.assetid: 3b9dfcf5-4bf1-4f35-9070-723171c823a1
ms.openlocfilehash: faf7b44c0ff1b207a7b017163ad2b032f26199b8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743887"
---
# <a name="security-concepts-used-in-wcf"></a>WCF에서 사용되는 보안 개념
WCF (Windows Communication Foundation) 보안은 이미 사용 되 고 다양 한 보안 인프라에서 배포 된 개념을 기반으로 빌드됩니다.  
  
 WCF는 HTTP (HTTPS)를 통한 SSL(Secure Sockets Layer) (SSL)와 같은 이러한 인프라 중 일부를 지원 합니다. 그러나 WCF는 SOAP 인코딩된 메시지에 대해 새로운 상호 운용 가능한 보안 표준 (예: WS-SECURITY)을 구현 하 여 기존 보안 인프라를 지 원하는 것 이상으로 진행 됩니다. 기존 메커니즘 또는 새로운 상호 운용 가능한 표준을 사용하는지 여부에 따라 두 가지의 보안 개념은 동일합니다. 따라서 기존 인프라 및 최신 표준에 적용된 개념을 이해하는 것이 특정 애플리케이션에 대해 가장 적합한 보안 모델을 구현하는 데 매우 중요합니다.  
  
## <a name="introduction-to-security-for-wcf-web-services"></a>WCF 웹 서비스 보안에 대한 소개  

Microsoft 패턴 및 사례 그룹은 [WCF 보안 가이드](https://archive.codeplex.com/?p=wcfsecurityguide)라는 심층 백서를 작성 했습니다. 이 백서는 웹 서비스, 주요 WCF 보안 개념, 인트라넷 응용 프로그램 시나리오 및 인터넷 응용 프로그램 시나리오와 관련 하 여 기본적인 보안 개념을 설명 합니다.  
  
## <a name="industry-wide-security-specifications"></a>산업 전반 보안 사양  
  
### <a name="public-key-infrastructure"></a>공개 키 인프라  

PKI (공개 키 인프라)는 공개 키 암호화를 사용 하 여 전자적 트랜잭션과 관련 된 각 파티를 확인 하 고 인증 하는 디지털 인증서, 인증 기관 및 기타 등록 기관의 시스템입니다.
  
### <a name="kerberos-protocol"></a>Kerberos 프로토콜  
 *Kerberos 프로토콜* 은 Windows 도메인에서 사용자를 인증 하는 보안 메커니즘을 만들기 위한 사양입니다. 이를 통해 사용자가 도메인 내의 다른 엔터티로 보안 컨텍스트를 설정할 수 있습니다. Windows 2000 이상 플랫폼은 기본적으로 Kerberos 프로토콜을 사용합니다. 인트라넷 클라이언트와 상호 작용할 서비스를 만들 때 시스템의 메커니즘을 이해하는 것이 좋습니다. 또한 *Web Services Security Kerberos 바인딩이* 널리 게시 되기 때문에 kerberos 프로토콜을 사용 하 여 인터넷 클라이언트와 통신할 수 있습니다. 즉, kerberos 프로토콜을 상호 운용할 수 있습니다. Windows에서 Kerberos 프로토콜을 구현 하는 방법에 대 한 자세한 내용은 [Microsoft kerberos](/windows/win32/secauthn/microsoft-kerberos)를 참조 하십시오.  
  
### <a name="x509-certificates"></a>X.509 인증서  
 X.509 인증서는 보안 애플리케이션에 사용되는 기본 자격 증명 양식입니다. X.509 인증서에 대 한 자세한 내용은 [X.509 공개 키 인증서](/windows/win32/seccertenroll/about-x-509-public-key-certificates)를 참조 하세요. X.509 인증서는 인증서 저장소 내에 저장됩니다. Windows를 실행하는 컴퓨터에는 여러 종류의 인증서 저장소가 있으며 저장소마다 용도가 다릅니다. 여러 저장소에 대 한 자세한 내용은 [인증서 저장소](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc757138(v=ws.10))를 참조 하세요.  
  
## <a name="web-services-security-specifications"></a>웹 서비스 보안 사양  
 시스템 정의 바인딩에서는 일반적으로 많이 사용되는 웹 서비스 보안 사양을 지원합니다. 시스템에서 제공 하는 바인딩 및 지원 되는 웹 서비스 사양의 전체 목록은 [시스템 제공 상호 운용성 바인딩에서 지 원하는 웹 서비스 프로토콜](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md) 을 참조 하세요.  
  
## <a name="access-control-mechanisms"></a>Access Control 메커니즘  
 WCF에서는 서비스 또는 작업에 대한 액세스를 제어하는 여러 방법을 제공합니다. 다음과 같은 방법이 포함됩니다.  
  
1. <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
2. ASP.NET 멤버 자격 공급자  
  
3. ASP.NET 역할 공급자  
  
4. 권한 부여 관리자  
  
5. ID 모델  
  
 이러한 항목에 대 한 자세한 내용은 [Access Control 메커니즘](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md) (영문)을 참조 하세요.  
  
## <a name="see-also"></a>참조

- [보안 개요](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Windows Server Fabric 용 보안 모델](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
