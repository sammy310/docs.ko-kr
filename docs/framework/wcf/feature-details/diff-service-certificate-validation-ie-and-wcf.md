---
title: Internet Explorer와 WCF로 완료된 서비스 인증서 유효성 검사의 차이점
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: 151075f2894b895ab90418748df9face3aa70252
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599193"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a>Internet Explorer와 WCF로 완료된 서비스 인증서 유효성 검사의 차이점
HTTPS를 사용 하는 경우 Internet Explorer와 Windows Communication Foundation (WCF) 서비스 인증서의 유효성을 검사 하는 방법의 차이로 인해 WCF 클라이언트가 서비스 끝점에 메시지를 성공적으로 보낼 수 있는 경우에도 Internet Explorer가 서비스의 도움말 페이지 또는 WSDL (Web Services Description Language)에 액세스할 수 없습니다. 이는 Internet Explorer는 서비스 인증서가 `ServerAuthentication` 향상 된 사용 플래그에 OID (개체 식별자)를 포함 하는지 여부를 확인 하는 반면 WCF는 이러한 제약 조건을 적용 하지 않기 때문입니다. Internet Explorer가 서비스 도움말 페이지 또는 서비스에 대 한 WSDL에 액세스할 수 없는 경우 [ServiceModel Metadata 유틸리티 도구 (svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) 를 사용 하 여 서비스 메타 데이터에 액세스 합니다.  
  
## <a name="see-also"></a>참고 항목

- [HTTPS, TCP를 통한 SSL 및 SOAP 보안의 인증서 유효성 검사 차이점](cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [방법: 메타데이터 검색 및 규정 준수 서비스 구현](how-to-retrieve-metadata-and-implement-a-compliant-service.md)
