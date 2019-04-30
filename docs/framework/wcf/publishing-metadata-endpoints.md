---
title: 메타데이터 엔드포인트 게시
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 143a46ce18a0d9dee89bbbffac9be9a467e951df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955159"
---
# <a name="publishing-metadata-endpoints"></a><span data-ttu-id="d9d8b-102">메타데이터 엔드포인트 게시</span><span class="sxs-lookup"><span data-stu-id="d9d8b-102">Publishing Metadata Endpoints</span></span>
<span data-ttu-id="d9d8b-103">Windows Communication Foundation (WCF) 서비스는 하나 이상의 메타 데이터 끝점을 게시 하 여 메타 데이터를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8b-103">Windows Communication Foundation (WCF) services publish metadata by publishing one or more metadata endpoints.</span></span> <span data-ttu-id="d9d8b-104">서비스 메타데이터를 게시하면 WS-MetadataExchange(MEX) 및 HTTP/GET 요청과 같이 표준화된 프로토콜을 통해 메타데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8b-104">Publishing service metadata makes the metadata available using standardized protocols, such as WS-MetadataExchange (MEX) and HTTP/GET requests.</span></span> <span data-ttu-id="d9d8b-105">메타데이터 엔드포인트는 주소, 바인딩 및 계약에 포함된 다른 서비스 엔드포인트와 유사하며 구성 또는 코드를 통해 서비스 호스트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8b-105">Metadata endpoints are similar to other service endpoints in that they have an address, a binding, and a contract, and they can be added to a service host through configuration or in code.</span></span> <span data-ttu-id="d9d8b-106">메타데이터 엔드포인트 게시를 사용하도록 설정하려면 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 서비스 동작을 서비스에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8b-106">To enable publishing metadata endpoints, you must add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> service behavior to the service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d9d8b-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d9d8b-107">In This Section</span></span>  
 [<span data-ttu-id="d9d8b-108">방법: 구성 파일을 사용 하는 서비스의 메타 데이터 게시</span><span class="sxs-lookup"><span data-stu-id="d9d8b-108">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 <span data-ttu-id="d9d8b-109">클라이언트는 Ws-metadataexchange 또는 사용 하 여 HTTP/GET 요청을 사용 하 여 메타 데이터를 검색할 수 있도록 메타 데이터를 게시할 WCF 서비스를 구성 하는 방법에 설명 합니다 `?wsdl` 쿼리 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8b-109">Demonstrates how to configure a WCF service to publish metadata so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
 [<span data-ttu-id="d9d8b-110">방법: 코드를 사용 하는 서비스의 메타 데이터 게시</span><span class="sxs-lookup"><span data-stu-id="d9d8b-110">How to: Publish Metadata for a Service Using Code</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 <span data-ttu-id="d9d8b-111">클라이언트는 Ws-metadataexchange 또는 사용 하 여 HTTP/GET 요청을 사용 하 여 메타 데이터를 검색할 수 있도록 코드에서 WCF 서비스에 대 한 메타 데이터 게시를 사용 하도록 설정 하는 방법에 설명 합니다 `?wsdl` 쿼리 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8b-111">Demonstrates how to enable metadata publishing for a WCF service in code so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9d8b-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="d9d8b-112">See also</span></span>

- [<span data-ttu-id="d9d8b-113">메타데이터 게시</span><span class="sxs-lookup"><span data-stu-id="d9d8b-113">Publishing Metadata</span></span>](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
