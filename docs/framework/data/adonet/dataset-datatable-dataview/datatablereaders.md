---
title: DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 1ff7868b59c6fdc4e6c443be1b831accc84f36a6
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203824"
---
# <a name="datatablereaders"></a>DataTableReader
<xref:System.Data.DataTableReader>는 <xref:System.Data.DataTable> 또는 <xref:System.Data.DataSet>의 내용을 하나 이상의 정방향 읽기 전용 결과 집합 형태로 제공합니다.  
  
 **Datatable**에서 **DataTableReader** 를 만들 때 결과 **DataTableReader** 개체에는로 표시 된 행을 제외 하 고 생성 된 **datatable** 과 동일한 데이터가 포함 된 결과 집합이 하나 포함 됩니다. deleted. 열은 원래 **DataTable**과 동일한 순서로 표시 됩니다.  
  
 을 호출 <xref:System.Data.DataSet.CreateDataReader%2A>하 여 생성 된 경우 DataTableReader에는 여러 개의 결과 집합이 포함 될 수 있습니다. 결과는 **DataSet** 개체의 <xref:System.Data.DataSet.Tables%2A> 컬렉션에 있는 **datatable** 의 순서와 동일 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [DataReader 만들기](creating-a-datareader.md)  
 **DataTableReader** 개체를 만드는 방법을 설명 합니다.  
  
 [DataTable 탐색](navigating-datatables.md)  
 **Read** 메서드를 사용 하 여 **DataTableReader**의 콘텐츠를 이동 하는 방법을 설명 합니다.  
  
## <a name="see-also"></a>참고자료

- [ADO.NET에서 데이터 검색 및 수정](../retrieving-and-modifying-data.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
