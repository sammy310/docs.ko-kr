---
title: 데이터 보기
ms.date: 03/30/2017
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
ms.openlocfilehash: fe6adac35c157b454f5e33d3526196d4f408fd89
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546870"
---
# <a name="dataviews"></a>데이터 보기
<xref:System.Data.DataView>는 데이터 바인딩 애플리케이션에서 자주 사용되는 기능으로, 이 기능을 사용하면 <xref:System.Data.DataTable>에 저장되어 있는 데이터에 대해 서로 다른 뷰를 만들 수 있습니다. **DataView**를 사용 하 여 테이블의 데이터를 여러 정렬 순서로 노출 시킬 수 있으며 행 상태별 또는 필터 식을 기준으로 데이터를 필터링 할 수 있습니다.

 **DataView** 는 원본 **DataTable**의 데이터에 대 한 동적 뷰를 제공 합니다. 내용, 순서 및 멤버 자격은 변경 내용이 발생 하면이를 반영 합니다. 이 동작은 특정 필터 및/또는 정렬 순서에 따라 테이블에서 배열을 반환 하는 **DataTable**의 **Select** 메서드와는 다릅니다 <xref:System.Data.DataRow> .이 콘텐츠는 기본 테이블에 대 한 변경 내용을 반영 하지만 멤버 자격과 순서는 정적으로 유지 됩니다. **DataView** 의 동적 기능을 통해 데이터 바인딩 응용 프로그램에 적합 합니다.

 **DataView** 는 데이터베이스 뷰와 매우 유사 하 게 단일 데이터 집합에 대 한 동적 뷰를 제공 하 여 다양 한 정렬 및 필터링 기준을 적용할 수 있습니다. 그러나 데이터베이스 뷰와 달리 **DataView** 는 테이블로 처리 될 수 없으며 조인 된 테이블에 대 한 뷰를 제공할 수 없습니다. 또한 원본 테이블에 존재 하는 열을 제외 하거나 계산 열과 같이 원본 테이블에 없는 열을 추가할 수 없습니다.

 을 사용 하 여 <xref:System.Data.DataView.DataViewManager%2A> **데이터 집합**의 모든 테이블에 대 한 뷰 설정을 관리할 수 있습니다. **DataViewManager** 에서는 각 테이블에 대 한 기본 뷰 설정을 편리 하 게 관리할 수 있는 방법을 제공 합니다. 컨트롤을 **데이터 집합**의 둘 이상의 테이블에 바인딩하는 경우 **DataViewManager** 에 대 한 바인딩이 이상적인 선택입니다.

## <a name="in-this-section"></a>섹션 내용
 [DataView 만들기](creating-a-dataview.md) **DataTable**에 대해 **DataView** 를 만드는 방법에 대해 설명 합니다.

 [데이터 정렬 및 필터링](sorting-and-filtering-data.md) 특정 필터 조건을 충족 하는 데이터 행의 하위 집합을 반환 하거나 특정 정렬 순서로 데이터를 반환 하도록 **DataView** 의 속성을 설정 하는 방법을 설명 합니다.

 [Datarow 및 datarowview](datarows-and-datarowviews.md) **DataView**에서 노출 하는 데이터에 액세스 하는 방법을 설명 합니다.

 [행 찾기](finding-rows.md) **DataView**에서 특정 행을 찾는 방법에 대해 설명 합니다.

 [Childviews 및 관계](childviews-and-relations.md) **DataView**를 사용 하 여 부모-자식 관계에서 데이터 뷰를 만드는 방법을 설명 합니다.

 [DataViews 수정](modifying-dataviews.md) 업데이트를 사용 하거나 사용 하지 않도록 설정 하는 등 **DataView**를 통해 기본 **DataTable** 의 데이터를 수정 하는 방법을 설명 합니다.

 [DataView 이벤트 처리](handling-dataview-events.md) **ListChanged** 이벤트를 사용 하 여 **DataView** 의 내용 또는 순서가 업데이트 될 때 알림을 받는 방법에 대해 설명 합니다.

 [DataViews 관리](managing-dataviews.md) **DataViewManager** 를 사용 하 여 **데이터 집합**의 각 테이블에 대 한 **DataView** 설정을 관리 하는 방법을 설명 합니다.

## <a name="related-sections"></a>관련 단원
 [ASP.NET 웹 응용 프로그램](/previous-versions/655cec97(v=vs.100)) ASP.NET 응용 프로그램, Web Forms 및 웹 서비스를 만들기 위한 개요 및 자세한 단계별 절차를 제공 합니다.

 [Windows 응용 프로그램](/previous-versions/ms184421(v=vs.100)) Windows Forms 및 콘솔 응용 프로그램 작업에 대 한 자세한 정보를 제공 합니다.

 [Dataset, datatable 및 DataViews](index.md) **DataSet** 개체와이 개체를 사용 하 여 응용 프로그램 데이터를 관리 하는 방법을 설명 합니다.

 [Datatable](datatables.md) **DataTable** 개체와이 개체를 사용 하 여 자체적으로 또는 **데이터 집합**의 일부로 응용 프로그램 데이터를 관리 하는 방법을 설명 합니다.

 [ADO.NET](../index.md) ADO.NET 아키텍처 및 구성 요소와 ADO.NET를 사용 하 여 기존 데이터 원본에 액세스 하 고 응용 프로그램 데이터를 관리 하는 방법을 설명 합니다.

## <a name="see-also"></a>참조

- [ADO.NET 개요](../ado-net-overview.md)
