---
title: DataSets, DataTables 및 DataViews
description: 일관 된 관계형 프로그래밍 모델을 제공 하는 데이터의 메모리 상주 ADO.NET 데이터 집합을 사용 하는 여러 가지 방법을 알아봅니다.
ms.date: 03/30/2017
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
ms.openlocfilehash: 4e1c0ea5f1de1715ad8e862e6a3ed7370b53c6ce
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555866"
---
# <a name="datasets-datatables-and-dataviews"></a>DataSets, DataTables 및 DataViews

ADO.NET <xref:System.Data.DataSet>은 포함된 데이터 소스에 관계없이 일관성 있는 관계형 프로그래밍 모델을 제공하는 데이터의 메모리 상주 표현입니다. <xref:System.Data.DataSet>은 데이터를 포함하고 제약하며 데이터의 순서를 지정하는 테이블과 각 테이블 간의 관계를 포함하는 데이터의 완전한 집합을 나타냅니다.  
  
<xref:System.Data.DataSet>을 사용하는 방법은 여러 가지가 있으며, 각 방법은 독립적으로 또는 조합하여 함께 사용할 수 있습니다. 다음과 같습니다.  
  
- <xref:System.Data.DataTable> 내에 프로그래밍 방식으로 <xref:System.Data.DataRelation>, <xref:System.Data.Constraint> 및 <xref:System.Data.DataSet>를 만들고 각 테이블을 데이터로 채웁니다.  
  
- <xref:System.Data.DataSet>를 사용하여 기존 관계형 데이터 소스의 데이터 테이블로 `DataAdapter`을 채웁니다.  
  
- XML을 사용하여 <xref:System.Data.DataSet> 내용을 로드하고 유지합니다. 자세한 내용은 [데이터 세트에서 XML 사용](using-xml-in-a-dataset.md)을 참조하세요.  
  
또한 XML Web services를 사용하여 강력한 형식의 <xref:System.Data.DataSet>을 전송할 수 있습니다. <xref:System.Data.DataSet>의 디자인은 XML Web services를 사용하는 데이터 전송에 가장 적합합니다. XML Web services에 대한 개요는 [XML Web services 개요](/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100))를 참조하세요. XML Web services에서 <xref:System.Data.DataSet>를 사용하는 예제는 [Consuming a DataSet from an XML Web Service](consuming-a-dataset-from-an-xml-web-service.md)(XML Web services에서 데이터 세트 사용)를 참조하세요.  
  
## <a name="in-this-section"></a>섹션 내용

 [보안 지침](security-guidance.md)  
 및에 대 한 보안 지침을 제공 <xref:System.Data.DataSet> <xref:System.Data.DataTable> 합니다.

 [데이터 집합 만들기](creating-a-dataset.md)  
 <xref:System.Data.DataSet>의 인스턴스를 만들기 위한 구문에 대해 설명합니다.  
  
 [데이터 세트에 DataTable 추가](adding-a-datatable-to-a-dataset.md)  
 테이블과 열을 만들어 <xref:System.Data.DataSet>에 추가하는 방법을 설명합니다.  
  
 [DataRelation 추가](adding-datarelations.md)  
 <xref:System.Data.DataSet>에 있는 테이블 사이의 관계를 만드는 방법을 설명합니다.  
  
 [DataRelation 탐색](navigating-datarelations.md)  
 <xref:System.Data.DataSet>에 있는 테이블 사이의 관계를 사용하여 부모-자식 관계의 자식 또는 부모 행을 반환하는 방법을 설명합니다.  
  
 [DataSet 콘텐츠 병합](merging-dataset-contents.md)  
 하나의 <xref:System.Data.DataSet>, <xref:System.Data.DataTable> 또는 <xref:System.Data.DataRow> 배열의 내용을 다른 <xref:System.Data.DataSet>으로 병합하는 방법을 설명합니다.  
  
 [데이터 세트 콘텐츠 복사](copying-dataset-contents.md)  
 스키마 및 지정한 데이터를 포함하는 <xref:System.Data.DataSet>의 복사본을 만드는 방법을 설명합니다.  
  
 [데이터 세트 이벤트 처리](handling-dataset-events.md)  
 <xref:System.Data.DataSet>의 이벤트와 해당 이벤트를 사용하는 방법을 설명합니다.  
  
 [형식화된 데이터 세트](typed-datasets.md)  
 형식화된 <xref:System.Data.DataSet>의 정의와 이를 만들어 사용하는 방법에 대해 설명합니다.  
  
 [DataTables](datatables.md)  
 <xref:System.Data.DataTable>을 만들고 스키마를 정의하며 데이터를 조작하는 방법을 설명합니다.  
  
 [DataTableReader](datatablereaders.md)  
 <xref:System.Data.DataTableReader>를 만들고 사용하는 방법에 대해 설명합니다.  
  
 [데이터 보기](dataviews.md)  
 `DataViews`를 만들고 작업하는 방법과 <xref:System.Data.DataView> 이벤트를 사용하는 방법을 설명합니다.  
  
 [데이터 세트에서 XML 사용](using-xml-in-a-dataset.md)  
 <xref:System.Data.DataSet>의 내용을 로드하여 XML 데이터로 유지하는 것을 포함하여 <xref:System.Data.DataSet>이 데이터 소스로서 XML과 상호 작용하는 방법을 설명합니다.  
  
 [XML Web Service에서 데이터 세트 사용](consuming-a-dataset-from-an-xml-web-service.md)  
 <xref:System.Data.DataSet>을 사용하여 데이터를 전송하는 XML Web services를 만드는 방법에 대해 설명합니다.  
  
## <a name="related-sections"></a>관련 단원

 [ADO.NET의 새로운 기능](../whats-new.md)  
 ADO.NET에 새로 추가된 기능을 소개합니다.  
  
 [ADO.NET 개요](../ado-net-overview.md)  
 ADO.NET의 디자인 및 구성 요소에 대해 소개합니다.  
  
 [DataAdapter에서 DataSet 채우기](../populating-a-dataset-from-a-dataadapter.md)  
 데이터 원본의 데이터가 있는 **데이터 세트**를 로드하는 방법에 대해 설명합니다.  
  
 [DataAdapters로 데이터 원본 업데이트](../updating-data-sources-with-dataadapters.md)  
 **데이터 세트**의 데이터에 대한 변경 사항을 다시 데이터 원본에 적용하는 방법에 대해 설명합니다.  
  
 [데이터 세트에 기존 제약 조건 추가](../adding-existing-constraints-to-a-dataset.md)  
 데이터 원본의 기본 키 정보로 **데이터 세트**를 채우는 방법에 대해 설명합니다.  
  
## <a name="see-also"></a>참조

- [ADO.NET](../index.md)
- [ADO.NET 개요](../ado-net-overview.md)
