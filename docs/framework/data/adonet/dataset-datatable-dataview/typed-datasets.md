---
description: '자세히 알아보기: 형식화 된 데이터 집합'
title: 형식화된 데이터 세트
ms.date: 03/30/2017
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
ms.openlocfilehash: 698efbe52e960afe00ca337445df919545d8437e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651498"
---
# <a name="typed-datasets"></a>형식화된 데이터 세트

<xref:System.Data.DataSet>에서는 약한 형식의 변수를 통해 런타임에 바인딩하여 값에 액세스할 수도 있고 강력한 형식의 메타포를 통해 데이터에 액세스할 수도 있습니다. **데이터 집합** 의 일부인 테이블과 열은 사용자에 게 친숙 한 이름 및 강력한 형식의 변수를 사용 하 여 액세스할 수 있습니다.  
  
 형식화 된 **데이터 집합** 은 **데이터 집합** 에서 파생 되는 클래스입니다. 따라서 **데이터 집합** 의 모든 메서드, 이벤트 및 속성을 상속 합니다. 또한 형식화 된 **데이터 집합** 은 강력한 형식의 메서드, 이벤트 및 속성을 제공 합니다. 즉, 컬렉션 기반의 메서드 대신 이름을 사용하여 테이블과 열에 액세스할 수 있습니다. 코드의 가독성이 향상 되는 것 외에도 형식화 된 **데이터 집합** 을 사용 하면 Visual Studio .net 코드 편집기에서 사용자가 입력할 때 자동으로 줄을 완성할 수 있습니다.  
  
 또한 강력한 형식의 **데이터 집합** 은 컴파일 시간에 올바른 형식으로 값에 대 한 액세스를 제공 합니다. 강력한 형식의 **데이터 집합** 을 사용 하는 경우 런타임에 코드가 컴파일될 때 형식 불일치 오류가 catch 됩니다.  
  
## <a name="in-this-section"></a>섹션 내용  

 [강력한 형식의 DataSets 생성](generating-strongly-typed-datasets.md)  
 강력한 형식의 **데이터 집합** 을 만들고 사용 하는 방법을 설명 합니다.  
  
 [형식화된 데이터 세트에 주석 지정](annotating-typed-datasets.md)  
 강력한 형식의 **데이터 집합** 을 생성 하는 데 사용 된 XSD (XML 스키마 정의 언어) 스키마에 주석을 추가 하 여 기본 스키마를 변경 하지 않고 **데이터 집합** 요소에 이름을 지정 하는 방법을 설명 합니다.  
  
## <a name="see-also"></a>참고 항목

- [DataSets, DataTables 및 DataViews](index.md)
- [ADO.NET 개요](../ado-net-overview.md)
