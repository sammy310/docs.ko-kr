---
title: 지원 되는 배포 시나리오
ms.date: 03/30/2017
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
ms.openlocfilehash: 299c8f2e29806a123e0a8b6e1e70d8cc13daa7bf
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546252"
---
# <a name="supported-deployment-scenarios"></a>지원 되는 배포 시나리오

부분적으로 신뢰할 수 있는 응용 프로그램에서 사용할 수 있도록 지원 되는 WCF (Windows Communication Foundation) 기능의 하위 집합은 WCF 사용에 대 한 일부 시나리오의 요구 사항을 충족 하도록 설계 되었습니다. 서버에서 WCF는 보안상의 이유로 ASP.NET 2.0 보통 신뢰 권한 집합에서 타사 응용 프로그램을 실행 하는 인터넷 범위의 공유 호스팅 공급자 요구 사항을 충족 합니다. 클라이언트에서 WCF 부분 신뢰 지원은 [ClickOnce 배포](/visualstudio/deployment/clickonce-security-and-deployment) 또는 WPF의 XAML 브라우저 응용 프로그램 기술과 같은 배포 기술의 요구 사항을 충족 하도록 설계 되어 신뢰할 수 없는 사이트에서 데스크톱 응용 프로그램을 원활 하 고 안전 하 게 배포할 수 있습니다.

## <a name="minimum-permission-requirements"></a>최소 권한 요구 사항

WCF는 다음 표준 명명 된 권한 집합 중 하나에서 실행 되는 응용 프로그램의 기능 하위 집합을 지원 합니다.

- 보통 신뢰 권한

- 인터넷 영역 권한

좀 더 제한적인 권한을 가진 부분적으로 신뢰할 수 있는 응용 프로그램에서 WCF를 사용 하려는 경우 런타임에 보안 예외가 발생할 수 있습니다.

이러한 권한 집합에서 지원되는 기능에 대한 자세한 내용은 [Partial Trust Feature Compatibility](partial-trust-feature-compatibility.md)을 참조하십시오.

## <a name="partial-trust-on-the-server"></a>서버의 부분 신뢰

ASP.NET 웹 응용 프로그램 호스팅 서비스의 많은 상업적 공급자는 서버에서 실행 중인 응용 프로그램이 ASP.NET 2.0 Medium Trust 권한 집합에서 실행 되도록 합니다. WCF 서비스는 <xref:System.ServiceModel.BasicHttpBinding> <xref:System.ServiceModel.WebHttpBinding> <xref:System.ServiceModel.WSHttpBinding> 전송 수준 보안과 함께, 또는를 사용 하는 경우 이러한 환경에서 실행할 수 있습니다.

보통 신뢰 호스팅 환경에서 실행 되는 WCF 서비스는 클라이언트 요청에 대 한 응답으로 다른 서버에 메시지를 전송 하 여 중간 계층 서비스 역할을 할 수도 있습니다. 서버에서 중간 계층 시나리오는 호스팅 환경이 애플리케이션에 적합한 <xref:System.Net.WebPermission> 을 부여해서 원하는 서버로 아웃바운드 요청을 한 경우 지원됩니다.

WCF는 지원 되는 SOAP 바인딩 중 하나를 사용 하는 SOAP 메시징 외에도 <xref:System.ServiceModel.WebHttpBinding> 부분 신뢰 응용 프로그램에서 웹 스타일 서비스를 빌드하기 위한를 지원 합니다. Wcf의 wcf [웹 HTTP 프로그래밍 모델](wcf-web-http-programming-model.md), [Wcf 배포](wcf-syndication.md)및 [AJAX 통합 및 JSON 지원](ajax-integration-and-json-support.md) 기능은 모두 부분 신뢰에서 지원 됩니다.

워크플로 서비스는 완전 신뢰 권한이 필요하며, 부분 신뢰 애플리케이션에서 사용할 수 없습니다.

자세한 내용은 [How to: Use Medium Trust in ASP.NET 2.0](/previous-versions/msp-n-p/ff648344(v=pandp.10))을 참조 하세요.

## <a name="partial-trust-on-the-client"></a>클라이언트의 부분 신뢰

신뢰할 수 없는 인터넷 사이트에서 코드를 다운로드하고 실행할 때 특정 보안 조치를 취해야 합니다. [ClickOnce 배포](/visualstudio/deployment/clickonce-security-and-deployment) 와 WPF의 XBAP (XAML 브라우저 응용 프로그램) 기술은 모두 부분 신뢰를 사용 하 여 제한 된 권한 (인터넷 영역)을 신뢰할 수 없는 코드에 부여 합니다.

WCF는 [ClickOnce 배포](/visualstudio/deployment/clickonce-security-and-deployment) 또는 XBAP에서 배포한 부분 신뢰 응용 프로그램 내에서 원격 서버와 통신 하는 데 사용할 수 있습니다. 인터넷 영역 권한 집합에는 <xref:System.Net.WebPermission> 원래 호스트에 대 한가 포함 되어 있으며, 이러한 응용 프로그램은 [부분 신뢰 기능 호환성](partial-trust-feature-compatibility.md)에 설명 된 지원 되는 WCF 바인딩 중 하나를 사용 하 여 원본 서버와 통신할 수 있습니다.

## <a name="see-also"></a>참조

- [코드 액세스 보안](../../misc/code-access-security.md)
- [Windows Presentation Foundation 브라우저에서 호스팅되는 애플리케이션 개요](/dotnet/desktop/wpf/app-development/wpf-xaml-browser-applications-overview)
- [부분 신뢰](partial-trust.md)
- [ASP.NET Trust Levels and Policy Files](/previous-versions/wyts434y(v=vs.140))
