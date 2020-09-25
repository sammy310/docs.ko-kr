---
title: DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 911a45dad3d5d82ab5e5752b1c12f7d8a6ab1563
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202320"
---
# <a name="datatablereaders"></a>DataTableReader

<xref:System.Data.DataTableReader>는 <xref:System.Data.DataTable> 또는 <xref:System.Data.DataSet>의 내용을 하나 이상의 정방향 읽기 전용 결과 집합 형태로 제공합니다.  
  
 **Datatable**에서 **DataTableReader** 을 만드는 경우 결과 **DataTableReader** 개체는 삭제 된 것으로 표시 된 행을 제외 하 고 생성 된 **datatable** 과 동일한 데이터를 포함 하는 하나의 결과 집합을 포함 합니다. 열은 원래 **DataTable**과 동일한 순서로 표시 됩니다.  
  
 을 호출 하 여 생성 된 경우 **DataTableReader** 에는 여러 개의 결과 집합이 포함 될 수 있습니다 <xref:System.Data.DataSet.CreateDataReader%2A> . 결과는 **DataSet** 개체의 컬렉션에 있는 **datatable** 의 순서와 동일 합니다 <xref:System.Data.DataSet.Tables%2A> .  
  
## <a name="in-this-section"></a>섹션 내용  

 [DataReader 만들기](creating-a-datareader.md)  
 **DataTableReader** 개체를 만드는 방법을 설명 합니다.  
  
 [DataTable 탐색](navigating-datatables.md)  
 **Read** 메서드를 사용 하 여 **DataTableReader**의 콘텐츠를 이동 하는 방법을 설명 합니다.  
  
## <a name="see-also"></a>참고 항목

- [ADO.NET에서 데이터 검색 및 수정](../retrieving-and-modifying-data.md)
- [ADO.NET 개요](../ado-net-overview.md)
