---
title: 클라이언트 애플리케이션에서 데이터 서비스 사용(WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- WCF Data Services, getting started
ms.assetid: 90872d0c-e989-4490-b3e9-54afb10d33d4
ms.openlocfilehash: 49e5ad2e6ae3dc50a0f48fcc3df2f7ec49ed7f88
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544403"
---
# <a name="using-a-data-service-in-a-client-application-wcf-data-services"></a>클라이언트 애플리케이션에서 데이터 서비스 사용(WCF Data Services)
웹 브라우저에 URI를 제공 하 여 OData (Open Data Protocol) 피드를 노출 하는 서비스에 액세스할 수 있습니다. URI는 리소스의 주소를 제공하고 요청 메시지는 해당 리소스가 나타내는 기본 데이터에 액세스하거나 변경하기 위해 이러한 주소로 전송됩니다. 브라우저는 HTTP GET 명령을 실행 하 고 요청 된 리소스를 OData 피드로 반환 합니다. 자세한 내용은 [웹 브라우저에서 서비스 액세스](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)를 참조 하세요.  
  
 웹 브라우저가 OData 서비스에서 필요한 데이터를 반환 하는지 테스트 하는 데 유용할 수 있지만, 데이터를 만들고 업데이트 하 고 삭제할 수 있는 프로덕션 OData 서비스는 일반적으로 웹 페이지의 응용 프로그램 코드나 스크립팅 언어를 통해 액세스 됩니다. 이 항목에서는 클라이언트 응용 프로그램에서 OData 피드에 액세스 하는 방법에 대 한 개요를 제공 합니다.  
  
## <a name="accessing-and-changing-data-using-rest-semantics"></a>REST 의미 체계를 사용하여 데이터 액세스 및 변경  
 Odata는 odata 피드를 노출 하는 서비스와 OData 피드를 사용 하는 응용 프로그램 간의 상호 운용성을 보장 합니다. 응용 프로그램은 특정 HTTP 작업의 요청 메시지를 보내고 작업이 수행 되어야 하는 엔터티 리소스의 주소를 지정 하는 URI를 사용 하 여 OData 기반 서비스의 데이터에 액세스 하 고 변경 합니다. 엔터티 데이터를 제공해야 하는 경우 메시지 본문에 특정하게 인코딩된 페이로드로 제공됩니다.  
  
### <a name="http-actions"></a>HTTP 작업  
 OData는 주소가 지정 된 리소스가 나타내는 엔터티 데이터에 대해 만들기, 읽기, 업데이트 및 삭제 작업을 수행 하는 다음 HTTP 작업을 지원 합니다.  
  
- **HTTP GET** -브라우저에서 리소스에 액세스할 때의 기본 작업입니다. 페이로드는 요청 메시지에 제공되지 않으며 요청한 데이터가 포함된 페이로드가 있는 응답 메서드가 반환됩니다.  
  
- **HTTP POST** -제공 된 리소스에 새 엔터티 데이터를 삽입 합니다. 삽입할 데이터가 요청 메시지의 페이로드에 제공됩니다. 응답 메시지의 페이로드에는 새로 만든 엔터티의 데이터가 들어 있습니다. 여기에는 자동으로 생성된 모든 키 값이 포함됩니다. 헤더에는 새 엔터티 리소스의 주소를 지정하는 URI도 포함됩니다.  
  
- **HTTP DELETE** -지정 된 리소스가 나타내는 엔터티 데이터를 삭제 합니다. 요청 또는 응답 메시지에 페이로드가 없습니다.  
  
- **HTTP PUT** -요청 메시지의 페이로드에 제공 된 새 데이터로 요청 된 리소스의 기존 엔터티 데이터를 바꿉니다.  
  
- **HTTP 병합** -엔터티 데이터를 변경 하기 위해 데이터 소스에서 삭제를 실행 하는 비효율성이 있으므로 OData는 새로운 HTTP 병합 동작을 제공 합니다. 요청 메시지의 페이로드에는 주소가 지정된 엔터티 리소스에서 변경되어야 하는 속성이 포함되어 있습니다. Http MERGE는 http 사양에 정의 되어 있지 않으므로 비 OData 인식 서버를 통해 HTTP 병합 요청을 라우팅하는 추가 처리가 필요할 수 있습니다.  
  
 자세한 내용은 [OData: 작업](https://www.odata.org/documentation/odata-version-2-0/operations/)을 참조 하세요.
  
### <a name="payload-formats"></a>페이로드 형식  
 HTTP PUT, HTTP POST 또는 HTTP MERGE 요청의 경우 요청 메시지의 페이로드에 데이터 서비스로 보내는 엔터티 데이터가 포함되어 있습니다. 페이로드의 내용은 메시지의 데이터 형식에 따라 달라집니다. DELETE를 제외한 모든 작업에 대한 HTTP 응답에도 이러한 페이로드가 들어 있습니다. OData는 서비스를 사용 하 여 데이터에 액세스 하 고 데이터를 변경 하기 위해 다음 페이로드 형식을 지원 합니다.  
  
- **Atom** -OData에서 AtomPub (Atom Publishing Protocol)에 대 한 확장으로 정의 된 XML 기반 메시지 인코딩으로, 웹 피드, 팟캐스트, WIKI 및 XML 기반 인터넷 기능을 위해 HTTP를 통해 데이터를 교환할 수 있도록 합니다. 자세한 내용은 [OData: Atom Format](https://www.odata.org/documentation/odata-version-2-0/atom-format/)을 참조 하십시오.
  
- Json ( **json** JavaScript Object Notation)은 JavaScript 프로그래밍 언어의 하위 집합을 기반으로 하는 간단한 데이터 교환 형식입니다. 자세한 내용은 [OData: JSON Format](https://www.odata.org/documentation/odata-version-2-0/json-format/)을 참조 하십시오.
  
 페이로드의 메시지 형식은 HTTP 요청 메시지의 헤더에서 요청됩니다. 자세한 내용은 [OData: 작업](https://www.odata.org/documentation/odata-version-2-0/operations/)을 참조 하세요.
  
## <a name="accessing-and-changing-data-using-client-libraries"></a>클라이언트 라이브러리를 사용하여 데이터 액세스 및 변경  
 WCF Data Services에는 .NET Framework 및 Silverlight 기반 클라이언트 응용 프로그램에서 OData 피드를 보다 쉽게 사용할 수 있도록 하는 클라이언트 라이브러리가 포함 되어 있습니다. 이러한 라이브러리는 HTTP 메시지를 보내고 받는 작업을 단순화합니다. 또한 엔터티 데이터를 나타내는 CLR 개체로 메시지 페이로드를 변환합니다. 클라이언트 라이브러리는 두 가지 핵심 클래스인 <xref:System.Data.Services.Client.DataServiceContext> 및 <xref:System.Data.Services.Client.DataServiceQuery%601>를 제공합니다. 이러한 클래스를 사용하면 데이터 서비스를 쿼리한 다음 반환된 엔터티 데이터를 CLR 개체로 사용하여 작업할 수 있습니다. 자세한 내용은 [WCF Data Services 클라이언트 라이브러리](wcf-data-services-client-library.md) 및 [WCF Data Services (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc838234(v=vs.95))를 참조 하세요.  
  
 Visual Studio의 **서비스 참조 추가** 대화 상자를 사용 하 여 데이터 서비스에 대 한 참조를 추가할 수 있습니다. 이 도구는 참조된 데이터 서비스에서 서비스 메타데이터를 요청하고 데이터 서비스를 나타내는 <xref:System.Data.Services.Client.DataServiceContext> 및 엔터티를 나타내는 클라이언트 데이터 서비스 클래스를 생성합니다. 자세한 내용은 [데이터 서비스 클라이언트 라이브러리 생성](generating-the-data-service-client-library-wcf-data-services.md)을 참조 하십시오.  
  
 다른 종류의 클라이언트 응용 프로그램에서 OData 피드를 사용 하는 데 사용할 수 있는 프로그래밍 라이브러리가 있습니다. OData SDK에 대 한 자세한 내용은 [ODATA sdk-샘플 코드](https://www.odata.org/ecosystem/#sdk)를 참조 하세요.
  
## <a name="see-also"></a>참조

- [데이터 서비스 리소스 액세스](accessing-data-service-resources-wcf-data-services.md)
- [빠른 시작](quickstart-wcf-data-services.md)
