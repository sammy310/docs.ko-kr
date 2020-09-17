---
title: 메타데이터 형식
ms.date: 03/30/2017
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
ms.openlocfilehash: 01f0d7a2212b2af7e2d3a959ed91624edec46ce8
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720467"
---
# <a name="metadata-formats"></a>메타 데이터 형식

WCF (Windows Communication Foundation)는 다음 표에 나와 있는 메타 데이터 형식을 지원 합니다.  
  
## <a name="metadata-specifications-and-usage"></a>메타데이터 사양 및 사용  
  
|프로토콜|사양 및 사용|  
|--------------|-----------------------------|  
|WSDL 1.1|[Web Services Description Language (WSDL) 1.1](https://www.w3.org/TR/wsdl/)<br /><br /> WCF는 WSDL (웹 서비스 기술 언어)을 사용 하 여 서비스를 설명 합니다.|  
|XML 스키마|[Xml 스키마 파트 2: 데이터 형식 Second edition](https://www.w3.org/TR/2004/REC-xmlschema-2-20041028/) 및 [XML Schema Part 1: 구조 second edition](https://www.w3.org/TR/2004/REC-xmlschema-1-20041028/)<br /><br /> WCF는 XML 스키마를 사용 하 여 메시지에 사용 되는 데이터 형식을 설명 합니다.|  
|WS Policy|[Web Services Policy 1.2 - Framework (WS-Policy)](https://www.w3.org/Submission/WS-Policy/)<br /><br /> [Web Services Policy 1.5 - Framework](https://www.w3.org/TR/ws-policy/)<br /><br /> WCF는 도메인 특정 어설션과 함께 WS-POLICY 1.2 또는 1.5 사양을 사용 하 여 서비스 요구 사항 및 기능을 설명 합니다.|  
|WS Policy 첨부 파일|[Web Services Policy 1.2 - Attachment (WS-PolicyAttachment)](https://www.w3.org/Submission/WS-PolicyAttachment/)<br /><br /> WCF는 WS-POLICY 첨부 파일을 구현 하 여 WSDL의 다양 한 범위에서 정책 식을 연결 합니다.|  
|WS Metadata Exchange|[Web Services Metadata Exchange (WS-MetadataExchange) version 1.1](http://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF는 Ws-metadataexchange를 구현 하 여 XML 스키마, WSDL 및 WS-POLICY를 검색 합니다.|  
|WSDL에 대한 WS-Addressing 바인딩|[Web Services Addressing 1.0 - WSDL Binding](https://www.w3.org/TR/ws-addr-wsdl/)<br /><br /> WCF는 wsdl에 대 한 ws-addressing 바인딩을 구현 하 여 WSDL에서 주소 지정 정보를 첨부 합니다.|  
  
## <a name="see-also"></a>추가 정보

- [시스템 제공 상호 운용성 바인딩에서 지원하는 웹 서비스 프로토콜](web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [WSDL 및 정책](wsdl-and-policy.md)
