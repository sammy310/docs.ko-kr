---
title: Internet Explorer와 WCF로 완료된 서비스 인증서 유효성 검사의 차이점
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: 0bced548cdc9423d1907de09e8b52ebe078d7c19
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225922"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a><span data-ttu-id="5354c-102">Internet Explorer와 WCF로 완료된 서비스 인증서 유효성 검사의 차이점</span><span class="sxs-lookup"><span data-stu-id="5354c-102">Differences Between Service Certificate Validation Done by Internet Explorer and WCF</span></span>
<span data-ttu-id="5354c-103">Internet Explorer 및 Windows Communication Foundation (WCF) HTTPS를 사용 하는 경우 서비스 인증서를 확인 하는 방법은 간의 차이로 인해 있기 Internet Explorer는 도움말 페이지 또는 웹 서비스 기술 언어에 액세스할 수 없습니다. (WSDL) 서비스의 WCF 클라이언트를 성공적으로 할 경우에 메시지를 서비스 끝점으로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="5354c-103">Because of difference between the way Internet Explorer and Windows Communication Foundation (WCF) validate service certificates when HTTPS is used, it is possible that Internet Explorer will not be able to access the Help page or Web Services Description Language (WSDL) of a service even though a WCF client is able to successfully send messages to the service endpoints.</span></span> <span data-ttu-id="5354c-104">이 Internet Explorer 확인 하기 때문에 서비스 인증서에 있는지 여부는 `ServerAuthentication` OID (object identifier)의 향상 된 사용 플래그 하지만 WCF는 이러한 제약 조건을 적용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5354c-104">This is because Internet Explorer checks whether the service certificate has the `ServerAuthentication` object identifiers (OID) in the enhanced usage flags, whereas WCF does not enforce such a constraint.</span></span> <span data-ttu-id="5354c-105">Internet Explorer 서비스 도움말 페이지 또는 서비스에 대 한 WSDL에 액세스할 수 없는 경우 사용 합니다 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 서비스 메타 데이터에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="5354c-105">If Internet Explorer is unable to access the service Help page or the WSDL for the service, use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to access the service metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5354c-106">참고자료</span><span class="sxs-lookup"><span data-stu-id="5354c-106">See also</span></span>

- [<span data-ttu-id="5354c-107">HTTPS, TCP를 통한 SSL 및 SOAP 보안의 인증서 유효성 검사 차이점</span><span class="sxs-lookup"><span data-stu-id="5354c-107">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [<span data-ttu-id="5354c-108">방법: 메타데이터 검색 및 규정 준수 서비스 구현</span><span class="sxs-lookup"><span data-stu-id="5354c-108">How to: Retrieve Metadata and Implement a Compliant Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
