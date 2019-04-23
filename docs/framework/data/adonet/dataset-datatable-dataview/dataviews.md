---
title: 데이터 보기
ms.date: 03/30/2017
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
ms.openlocfilehash: aff4d6f648fa091130bfd9951f2a5001947b09a1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215913"
---
# <a name="dataviews"></a>데이터 보기
<xref:System.Data.DataView>는 데이터 바인딩 응용 프로그램에서 자주 사용되는 기능으로, 이 기능을 사용하면 <xref:System.Data.DataTable>에 저장되어 있는 데이터에 대해 서로 다른 뷰를 만들 수 있습니다. 사용 하는 **DataView**, 서로 다른 정렬 순서를 사용 하 여 테이블의 데이터를 노출 시킬 수 있으며 행 상태 또는 필터 식을 기반으로 데이터를 필터링 할 수 있습니다.  
  
 A **DataView** 데이터 원본에 대 한 동적 뷰를 제공 **DataTable**: 콘텐츠, 순서 및 멤버 발생 하는 변경 내용을 반영 합니다. 다르게이 동작 합니다 **선택** 메서드의 **DataTable**를 반환 하는 <xref:System.Data.DataRow> 특정 필터 및/또는 정렬 순서를 기준으로 테이블에서 배열:이 콘텐츠는 변경 내용을 반영를 기본 테이블, 하지만 해당 멤버 및 순서 정적으로 유지 됩니다. 동적 기능은 합니다 **DataView** 데이터 바인딩 응용 프로그램에 적합 합니다.  
  
 A **DataView** 다른 정렬 및 필터링 기준을 적용할 수 있는 데이터베이스 뷰와 마찬가지로 데이터의 단일 집합의 동적 뷰를 제공 합니다. 그러나 데이터베이스 뷰와 달리를 **DataView** 테이블로 처리할 수 없습니다 및 조인 된 테이블의 뷰를 제공할 수 없습니다. 또한 소스 테이블에 있는 열을 제외하거나 계산을 통해 만들어지는 열과 같이 소스 테이블에 없는 열을 추가할 수 없습니다.  
  
 사용할 수는 <xref:System.Data.DataView.DataViewManager%2A> 에 있는 모든 테이블에 대 한 뷰 설정을 관리할 수는 **데이터 집합**합니다. 합니다 **DataViewManager** 각 테이블에 대 한 기본 뷰 설정을 관리할 수 있는 편리한 방법을 제공 합니다. 컨트롤의 둘 이상의 테이블을 바인딩하는 경우는 **데이터 집합**바인딩하는 **DataViewManager** 것이 좋습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [DataView 만들기](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataview.md)  
 만드는 방법을 설명 합니다는 **DataView** 에 **DataTable**합니다.  
  
 [데이터 정렬 및 필터링](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 속성을 설정 하는 방법에 설명 된 **DataView** 특정 필터 조건에 맞는 데이터 행의 하위 집합을 반환 하거나 특정 정렬 순서로 데이터를 반환 합니다.  
  
 [DataRow 및 DataRowView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarows-and-datarowviews.md)  
 제공 하는 데이터에 액세스 하는 방법에 설명 합니다 **DataView**합니다.  
  
 [행 찾기](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)  
 특정 행을 찾는 방법에 설명 된 **DataView**합니다.  
  
 [ChildView 및 관계](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/childviews-and-relations.md)  
 뷰를 사용 하 여 부모-자식 관계를 만드는 방법에 설명 된 **DataView**합니다.  
  
 [데이터 보기 수정](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/modifying-dataviews.md)  
 기본 데이터를 수정 하는 방법에 설명 **DataTable** 를 통해 합니다 **DataView**업데이트 활성화 또는 비활성화 등입니다.  
  
 [DataView 이벤트 처리](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataview-events.md)  
 사용 하는 방법에 설명 합니다 **ListChanged** 이벤트 알림을 받을 수 때 내용 또는 순서가의 **DataView** 업데이트 하는.  
  
 [데이터 보기 관리](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/managing-dataviews.md)  
 사용 하는 방법에 설명 합니다는 **DataViewManager** 관리 하 **DataView** 의 각 테이블에 대 한 설정을 **데이터 집합**합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [ASP.NET 웹 응용 프로그램](https://docs.microsoft.com/previous-versions/655cec97(v=vs.100))  
 ASP.NET 응용 프로그램, Web Forms 및 Web Services를 만들기 위한 개요 및 자세한 단계별 절차를 제공합니다.  
  
 [Windows 응용 프로그램](https://docs.microsoft.com/previous-versions/ms184421(v=vs.100))  
 Windows Forms 및 콘솔 응용 프로그램 작업에 대한 자세한 내용을 제공합니다.  
  
 [DataSet, DataTable 및 DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 에 대해 설명 합니다 **데이터 집합** 개체 및 사용 하 여 응용 프로그램 데이터를 관리 하는 방법을 합니다.  
  
 [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 에 대해 설명 합니다 **DataTable** 개체와 사용 하 여 자체적으로 또는의 일부로 응용 프로그램 데이터를 관리 하는 방법을 **데이터 집합**합니다.  
  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 ADO.NET 아키텍처 및 구성 요소에 대해 설명하고, ADO.NET을 사용하여 기존 데이터 소스에 액세스하고 응용 프로그램 데이터를 관리하는 방법을 설명합니다.  
  
## <a name="see-also"></a>참고자료

- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
