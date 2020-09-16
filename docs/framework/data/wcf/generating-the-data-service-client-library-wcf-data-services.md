---
title: 데이터 서비스 클라이언트 라이브러리 생성(WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: a6a388f837d00d63a39212843c3fa88b28482b26
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545809"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a>데이터 서비스 클라이언트 라이브러리 생성(WCF Data Services)
OData (Open Data Protocol)를 구현 하는 데이터 서비스는 OData 피드에서 노출 하는 데이터 모델을 설명 하는 서비스 메타 데이터 문서를 반환할 수 있습니다. 자세한 내용은 [OData: 개요](https://www.odata.org/documentation/odata-version-2-0/overview/) 문서의 서비스 메타 데이터 문서 섹션을 참조 하세요. Visual Studio의 **서비스 참조 추가** 대화 상자를 사용 하 여 OData 기반 서비스에 대 한 참조를 추가할 수 있습니다. 이 도구를 사용 하 여 클라이언트 프로젝트의 OData 피드에서 반환 하는 메타 데이터에 대 한 참조를 추가 하는 경우 다음 작업을 수행 합니다.  
  
- 데이터 서비스에서 서비스 메타데이터 문서를 요청하고 반환된 메타데이터를 해석합니다.  
  
    > [!NOTE]
    > 반환된 메타데이터는 클라이언트 프로젝트에 .edmx 파일로 저장됩니다. 이 .edmx 파일은 Entity Framework에서 사용되는 .edmx 파일과 동일한 형식을 사용하지 않기 때문에 엔터티 데이터 모델 디자이너를 사용하여 열 수 없습니다. XML 편집기나 텍스트 편집기를 사용하여 이 메타데이터 파일을 볼 수 있습니다. 자세한 내용은 [ \[ \] Data Services 패키징 형식에 대 한 MC-EDMX: 엔터티 데이터 모델](/openspecs/windows_protocols/mc-edmx/5dff5e25-56a1-408b-9d44-bff6634c7d16)를 참조 하세요.
  
- <xref:System.Data.Services.Client.DataServiceContext>에서 상속된 엔터티 컨테이너 클래스로 서비스 표현을 생성합니다. 생성된 이 엔터티 컨테이너 클래스는 엔터티 데이터 모델 도구에서 생성하는 엔터티 컨테이너와 유사합니다. 자세한 내용은 [개체 서비스 개요(Entity Framework)](/previous-versions/bb386871(v=vs.100))를 참조하세요.  
  
- 서비스 메타데이터에서 검색한 데이터 모델 형식에 대해 데이터 클래스를 생성합니다.  
  
- 프로젝트에 `System.Data.Services.Client` 어셈블리 참조를 추가합니다.  
  
 자세한 내용은 [방법: 데이터 서비스 참조 추가](how-to-add-a-data-service-reference-wcf-data-services.md)를 참조 하세요.  
  
 클라이언트 데이터 서비스 클래스는 명령 프롬프트에서 [DataSvcUtil.exe](wcf-data-service-client-utility-datasvcutil-exe.md) 도구를 사용 하 여 생성할 수도 있습니다. 자세한 내용은 [방법: 수동으로 클라이언트 데이터 서비스 클래스 생성](how-to-manually-generate-client-data-service-classes-wcf-data-services.md)을 참조 하세요.  
  
## <a name="client-data-type-mapping"></a>클라이언트 데이터 형식 매핑  
 Visual Studio 또는 도구에서 **서비스 참조 추가** 대화 상자를 사용 하 여 `DataSvcUtil.exe` OData 피드를 기반으로 하는 클라이언트 데이터 클래스를 생성 하는 경우 .NET Framework 데이터 형식은 다음과 같이 데이터 모델의 기본 형식에 매핑됩니다.  
  
|데이터 모델 형식|.NET Framework 데이터 형식|  
|---------------------|------------------------------|  
|`Edm.Binary`|<xref:System.Byte> `[]`|  
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
  
 자세한 내용은 [OData: Overview](https://www.odata.org/documentation/odata-version-2-0/overview/) 문서에서 기본 데이터 형식 섹션을 참조 하세요.
  
## <a name="see-also"></a>참조

- [WCF Data Services 클라이언트 라이브러리](wcf-data-services-client-library.md)
- [빠른 시작](quickstart-wcf-data-services.md)
