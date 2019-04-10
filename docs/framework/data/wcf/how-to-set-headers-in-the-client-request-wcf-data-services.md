---
title: '방법: (WCF Data Services) 클라이언트 요청의 헤더 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing requests
ms.assetid: 3d55168d-5901-4f48-8117-6c93da3ab5ae
ms.openlocfilehash: 0d821ca499e0b0e9151a724de5149f35bb815861
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143262"
---
# <a name="how-to-set-headers-in-the-client-request-wcf-data-services"></a>방법: (WCF Data Services) 클라이언트 요청의 헤더 설정
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트 라이브러리를 사용하여 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]을 지원하는 데이터 서비스에 액세스할 때 클라이언트 라이브러리에서 데이터 서비스로 전송되는 요청 메시지의 필수 HTTP 헤더를 자동으로 설정합니다. 하지만 클라이언트 라이브러리는 데이터 서비스에 청구 기반 인증이나 쿠키가 필요한 경우와 같은 특정 상황에서 필요한 메시지 헤더를 설정하지 못합니다. 자세한 내용은 [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md#clientAuthentication)을 참조하세요. 이런 경우에는 전송하기 전에 요청 메시지의 메시지 헤더를 수동으로 설정해야 합니다. 이 항목의 예제에서는 데이터 서비스로 전송하기 전에 요청 메시지에 새로운 헤더를 추가하도록 <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> 이벤트를 처리하는 방법을 설명합니다.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다. 이 서비스 및 클라이언트 데이터 클래스를 수행할 때 생성 됩니다는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다. 사용할 수도 있습니다는 [Northwind 샘플 데이터 서비스](https://go.microsoft.com/fwlink/?LinkId=187426) 에 게시 된는 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] ; 웹 사이트를이 샘플 데이터 서비스는 읽기 전용 이며 변경 내용을 저장 하려고 하면 오류가 발생 합니다. 샘플 데이터 서비스는 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 웹 사이트는 익명 인증을 허용 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>이벤트에 대한 처리기를 등록한 다음 데이터 서비스에 대해 쿼리를 실행합니다.  
  
> [!NOTE]
>  데이터 서비스에서 모든 요청의 메시지 헤더를 수동으로 설정하도록 요구하는 경우 데이터 서비스를 나타내는 엔터티 컨테이너(이 경우에는 <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>)에서 `OnContextCreated` 부분 메서드를 재정의하여 `NorthwindEntities` 이벤트 처리기를 등록하는 것이 좋습니다.  
  
[!code-csharp[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#registerheadersquery)]   
[!code-vb[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#registerheadersquery)]
  
## <a name="example"></a>예제  
 다음 메서드가 <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> 이벤트를 처리하고 인증 헤더를 요청에 추가합니다.   
  
 [!code-csharp[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#onsendingrequest)]  
 [!code-vb[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#onsendingrequest)]  
  
## <a name="see-also"></a>참고자료

- [WCF Data Services에 보안 설정](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)
- [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
