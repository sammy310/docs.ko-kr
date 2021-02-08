---
description: '자세히 알아보기: 방법: 서명을 확인 하는 데 사용 되는 인증 기관 인증서 체인 지정 (WCF)'
title: '방법: 서명을 확인하는 데 사용되는 인증 기관 인증서 체인 지정(WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], specifying the certificate authority certificate chain
- certificates [WCF], verifying signatures
ms.assetid: 7c719355-aa41-4567-80d0-5115a8cf73fd
ms.openlocfilehash: f3bfcb378641db2a4bdba054f25042a5e7e9be07
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793456"
---
# <a name="how-to-specify-the-certificate-authority-certificate-chain-used-to-verify-signatures-wcf"></a>방법: 서명을 확인하는 데 사용되는 인증 기관 인증서 체인 지정(WCF)

Windows Communication Foundation (WCF)는 x.509 인증서를 사용 하 여 서명 된 SOAP 메시지를 수신 하는 경우 기본적으로 신뢰할 수 있는 인증 기관에서 x.509 인증서를 발급 했는지 확인 합니다. 이렇게 하려면 인증서 저장소를 찾고 해당 인증 기관의 인증서가 신뢰할 수 있는 것으로 지정되었는지 확인합니다. WCF가 이러한 결정을 내릴 수 있도록 하려면 올바른 인증서 저장소에 인증 기관 인증서 체인을 설치 해야 합니다.  
  
### <a name="to-install-a-certification-authority-certificate-chain"></a>인증 기관 인증서 체인을 설치하려면  
  
- SOAP 메시지 수신자가에서 발급 한 x.509 인증서를 신뢰 하는 각 인증 기관에 대해 WCF가 x.509 인증서를 검색 하도록 구성 된 인증서 저장소에 인증 기관 인증서 체인을 설치 합니다.  
  
     예를 들어, SOAP 메시지 받는 사람이 Microsoft에서 발급 한 x.509 인증서를 신뢰 하려는 경우 Microsoft 용 인증 기관 인증서 체인은 WCF가 x.509 인증서를 찾도록 설정 된 인증서 저장소에 설치 해야 합니다. WCF가 x.509 인증서를 검색 하는 인증서 저장소는 코드 또는 구성에서 지정할 수 있습니다. 예를 들어 메서드를 사용 하 여 코드에서이를 지정 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> 하거나를 비롯 한 몇 가지 방법을 구성에서 지정할 수 있습니다 [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) .  
  
     Windows는 신뢰할 수 있는 인증 기관에 대한 기본 인증서 체인 집합이 함께 제공되므로 모든 인증 기관에 대한 인증서 체인을 반드시 설치할 필요는 없습니다.  
  
    1. 인증 기관 인증서 체인을 내보냅니다.  
  
         이 작업을 수행하는 방법은 인증 기관에 따라 다릅니다. 인증 기관에서 Microsoft 인증서 서비스를 실행 하는 경우 **ca 인증서, 인증서 체인 또는 CRL 다운로드** 를 선택한 다음 **ca 인증서 다운로드** 를 선택 합니다.  
  
    2. 인증 기관 인증서 체인을 가져옵니다.  
  
         MMC(Microsoft Management Console)에서 인증서 스냅인을 엽니다. WCF가 x.509 인증서를 검색 하도록 구성 된 인증서 저장소에 대해 **신뢰할 수 있는 루트** **인증 기관** 폴더를 선택 합니다. **신뢰할 수 있는 루트 인증 기관** 폴더에서 **인증서** 폴더를 마우스 오른쪽 단추로 클릭 하 고 **모든 작업** 을 가리킨 다음 **가져오기** 를 클릭 합니다. a 단계에서 내보낸 파일을 제공합니다.  
  
         MMC에서 인증서 스냅인을 사용 하는 방법에 대 한 자세한 내용은 [방법: Mmc 스냅인을 사용 하 여 인증서 보기](how-to-view-certificates-with-the-mmc-snap-in.md)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [인증서 사용](working-with-certificates.md)
