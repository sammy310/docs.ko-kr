---
description: '자세한 정보: 데이터 서비스 클라이언트 라이브러리 생성 (WCF Data Services)'
title: 데이터 서비스 클라이언트 라이브러리 생성(WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: 3bac2459044ff910c8085ff56e60d9da6e0ba877
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765934"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a><span data-ttu-id="2fb78-103">데이터 서비스 클라이언트 라이브러리 생성(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="2fb78-103">Generating the Data Service Client Library (WCF Data Services)</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="2fb78-104">OData (Open Data Protocol)를 구현 하는 데이터 서비스는 OData 피드에서 노출 하는 데이터 모델을 설명 하는 서비스 메타 데이터 문서를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb78-104">A data service that implements the Open Data Protocol (OData) can return a service metadata document that describes the data model exposed by the OData feed.</span></span> <span data-ttu-id="2fb78-105">자세한 내용은 [OData: 개요](https://www.odata.org/documentation/odata-version-2-0/overview/) 문서의 서비스 메타 데이터 문서 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2fb78-105">For more information, see the Service Metadata Document section in the [OData: Overview](https://www.odata.org/documentation/odata-version-2-0/overview/) article.</span></span> <span data-ttu-id="2fb78-106">Visual Studio의 **서비스 참조 추가** 대화 상자를 사용 하 여 OData 기반 서비스에 대 한 참조를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb78-106">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to an OData-based service.</span></span> <span data-ttu-id="2fb78-107">이 도구를 사용 하 여 클라이언트 프로젝트의 OData 피드에서 반환 하는 메타 데이터에 대 한 참조를 추가 하는 경우 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb78-107">When you use this tool to add a reference to the metadata returned by an OData feed in a client project, it performs the following actions:</span></span>  
  
- <span data-ttu-id="2fb78-108">데이터 서비스에서 서비스 메타데이터 문서를 요청하고 반환된 메타데이터를 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb78-108">Requests the service metadata document from the data service and interprets the returned metadata.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="2fb78-109">반환된 메타데이터는 클라이언트 프로젝트에 .edmx 파일로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fb78-109">The returned metadata is stored in the client project as an .edmx file.</span></span> <span data-ttu-id="2fb78-110">이 .edmx 파일은 Entity Framework에서 사용되는 .edmx 파일과 동일한 형식을 사용하지 않기 때문에 엔터티 데이터 모델 디자이너를 사용하여 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb78-110">This .edmx file cannot be opened by using the Entity Data Model designer because it does not have the same format an .edmx file used by the Entity Framework.</span></span> <span data-ttu-id="2fb78-111">XML 편집기나 텍스트 편집기를 사용하여 이 메타데이터 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb78-111">You can view this metadata file by using the XML editor or any text editor.</span></span> <span data-ttu-id="2fb78-112">자세한 내용은 [ \[ \] Data Services 패키징 형식에 대 한 MC-EDMX: 엔터티 데이터 모델](/openspecs/windows_protocols/mc-edmx/5dff5e25-56a1-408b-9d44-bff6634c7d16)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2fb78-112">For more information, see [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](/openspecs/windows_protocols/mc-edmx/5dff5e25-56a1-408b-9d44-bff6634c7d16).</span></span>
  
- <span data-ttu-id="2fb78-113"><xref:System.Data.Services.Client.DataServiceContext>에서 상속된 엔터티 컨테이너 클래스로 서비스 표현을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb78-113">Generates a representation of the service as an entity container class that inherits from <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="2fb78-114">생성된 이 엔터티 컨테이너 클래스는 엔터티 데이터 모델 도구에서 생성하는 엔터티 컨테이너와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb78-114">This generated entity container class resembles the entity container that the Entity Data Model tools generate.</span></span> <span data-ttu-id="2fb78-115">자세한 내용은 [개체 서비스 개요(Entity Framework)](/previous-versions/bb386871(v=vs.100))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2fb78-115">For more information, see [Object Services Overview (Entity Framework)](/previous-versions/bb386871(v=vs.100)).</span></span>  
  
- <span data-ttu-id="2fb78-116">서비스 메타데이터에서 검색한 데이터 모델 형식에 대해 데이터 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb78-116">Generates data classes for the data model types that it discovers in the service metadata.</span></span>  
  
- <span data-ttu-id="2fb78-117">프로젝트에 `System.Data.Services.Client` 어셈블리 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb78-117">Adds a reference to the `System.Data.Services.Client` assembly to the project.</span></span>  
  
 <span data-ttu-id="2fb78-118">자세한 내용은 [방법: 데이터 서비스 참조 추가](how-to-add-a-data-service-reference-wcf-data-services.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2fb78-118">For more information, see [How to: Add a Data Service Reference](how-to-add-a-data-service-reference-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="2fb78-119">클라이언트 데이터 서비스 클래스는 명령 프롬프트에서 [DataSvcUtil.exe](wcf-data-service-client-utility-datasvcutil-exe.md) 도구를 사용 하 여 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb78-119">The client data service classes can also be generated by using the [DataSvcUtil.exe](wcf-data-service-client-utility-datasvcutil-exe.md) tool at the command prompt.</span></span> <span data-ttu-id="2fb78-120">자세한 내용은 [방법: 수동으로 클라이언트 데이터 서비스 클래스 생성](how-to-manually-generate-client-data-service-classes-wcf-data-services.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2fb78-120">For more information, see [How to: Manually Generate Client Data Service Classes](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>  
  
## <a name="client-data-type-mapping"></a><span data-ttu-id="2fb78-121">클라이언트 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="2fb78-121">Client Data Type Mapping</span></span>  

 <span data-ttu-id="2fb78-122">Visual Studio 또는 도구에서 **서비스 참조 추가** 대화 상자를 사용 하 여 `DataSvcUtil.exe` OData 피드를 기반으로 하는 클라이언트 데이터 클래스를 생성 하는 경우 .NET Framework 데이터 형식은 다음과 같이 데이터 모델의 기본 형식에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fb78-122">When you use the **Add Service Reference** dialog in Visual Studio or the `DataSvcUtil.exe` tool to generate client data classes that are based on an OData feed, the .NET Framework data types are mapped to the primitive types from the data model as follows:</span></span>  
  
|<span data-ttu-id="2fb78-123">데이터 모델 형식</span><span class="sxs-lookup"><span data-stu-id="2fb78-123">Data model type</span></span>|<span data-ttu-id="2fb78-124">.NET Framework 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="2fb78-124">.NET Framework data type</span></span>|  
|---------------------|------------------------------|  
|`Edm.Binary`|<span data-ttu-id="2fb78-125"><xref:System.Byte> `[]`</span><span class="sxs-lookup"><span data-stu-id="2fb78-125"><xref:System.Byte> `[]`</span></span>|  
|`Edm.Boolean`|<xref:System.Boolean>|  
|`Edm.Byte`|<xref:System.Byte>|  
|`Edm.DateTime`|<xref:System.DateTime>|  
|`Edm.Decimal`|<xref:System.Decimal>|  
|`Edm.Double`|<xref:System.Double>|  
|`Edm.Guid`|<xref:System.Guid>|  
|`Edm.Int16`|<xref:System.Int16>|  
|`Edm.Int32`|<xref:System.Int32>|  
|`Edm.Int64`|<xref:System.Int64>|  
|`Edm.SByte`|<xref:System.SByte>|  
|`Edm.Single`|<xref:System.Single>|  
|`Edm.String`|<xref:System.String>|  
  
 <span data-ttu-id="2fb78-126">자세한 내용은 [OData: Overview](https://www.odata.org/documentation/odata-version-2-0/overview/) 문서에서 기본 데이터 형식 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2fb78-126">For more information, see the Primitive Data Types section in the [OData: Overview](https://www.odata.org/documentation/odata-version-2-0/overview/) article.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2fb78-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2fb78-127">See also</span></span>

- [<span data-ttu-id="2fb78-128">WCF Data Services 클라이언트 라이브러리</span><span class="sxs-lookup"><span data-stu-id="2fb78-128">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)
- [<span data-ttu-id="2fb78-129">빠른 시작</span><span class="sxs-lookup"><span data-stu-id="2fb78-129">Quickstart</span></span>](quickstart-wcf-data-services.md)
