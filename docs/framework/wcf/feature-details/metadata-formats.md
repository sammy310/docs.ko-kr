---
title: 메타데이터 형식
ms.date: 03/30/2017
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
ms.openlocfilehash: 55f68f4b56e50b19da19ecc941e9ec537b846006
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173825"
---
# <a name="metadata-formats"></a>메타데이터 형식
Windows Communication Foundation (WCF)는 다음 테이블의 메타 데이터 형식 지원합니다.  
  
## <a name="metadata-specifications-and-usage"></a>메타데이터 사양 및 사용  
  
|프로토콜|사양 및 사용|  
|--------------|-----------------------------|  
|WSDL 1.1|[Web Services Description Language (WSDL) 1.1](https://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> WCF 웹 서비스 설명 언어 (WSDL)를 사용 하 여 서비스 설명.|  
|XML 스키마|[XML Schema Part 2: Datatypes Second Edition](https://go.microsoft.com/fwlink/?LinkId=94861) 고 [XML Schema Part 1: 구조 제 2 판](https://go.microsoft.com/fwlink/?LinkId=94862)<br /><br /> WCF는 메시지에 사용 되는 데이터 형식을 설명 하는 XML 스키마를 사용 합니다.|  
|WS Policy|[Web Services Policy 1.2 - Framework (WS-Policy)](https://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> [Web Services Policy 1.5 - Framework](https://go.microsoft.com/fwlink/?LinkId=94865)<br /><br /> WCF를 사용 하 여 Ws-policy 1.2 또는 1.5 사양을 도메인별 어설션과 사용 하 여 서비스 요구 사항 및 기능에 설명 합니다.|  
|WS Policy 첨부 파일|[Web Services Policy 1.2 - Attachment (WS-PolicyAttachment)](https://go.microsoft.com/fwlink/?LinkId=94866)<br /><br /> WCF는 WSDL에서 다양 한 범위의 정책 식을 연결할 Ws-policy 첨부 파일을 구현 합니다.|  
|WS Metadata Exchange|[Web Services Metadata Exchange (WS-MetadataExchange) version 1.1](https://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> WCF는 XML 스키마, WSDL 및 Ws-policy를 검색 하려면 Ws-metadataexchange를 구현 합니다.|  
|WSDL에 대한 WS-Addressing 바인딩|[Web Services Addressing 1.0 - WSDL Binding](https://go.microsoft.com/fwlink/?LinkId=94869)<br /><br /> WCF는 WSDL에서 주소 지정 정보를 연결 하는 WSDL에 대 한 Ws-addressing 바인딩을 구현 합니다.|  
  
## <a name="see-also"></a>참고자료

- [시스템 제공 상호 운용성 바인딩에서 지원하는 웹 서비스 프로토콜](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [WSDL 및 정책](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)
