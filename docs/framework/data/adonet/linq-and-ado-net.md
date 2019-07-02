---
title: LINQ 및 ADO.NET
ms.date: 03/30/2017
ms.assetid: bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec
ms.openlocfilehash: 16b06549573bc79378539cf7f5ccdcb60c812e81
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504460"
---
# <a name="linq-and-adonet"></a>LINQ 및 ADO.NET
오늘날 많은 비즈니스 개발자 두 개 (이상) 프로그래밍 언어를 사용 해야 합니다: 비즈니스 논리와 프레젠테이션 계층에 대 한 상위 수준 언어 (시각적 개체와 같은 C# 또는 Visual Basic), 고 (예: Transact SQL) 데이터베이스와 상호 작용 하는 쿼리 언어 . 따라서 효과적으로 작업을 수행하려면 여러 언어에 능숙해야 하며 개발 환경에서 언어 불일치 문제도 발생하게 됩니다. 예를 들어, 데이터 액세스 API를 사용하여 데이터베이스에 대한 쿼리를 실행하는 응용 프로그램에서는 따옴표를 사용하여 쿼리를 문자열 리터럴로 지정합니다. 이 쿼리 문자열은 컴파일러에서 인식되지 않으므로 잘못된 구문, 참조되는 열이나 행이 실제로 있는지 여부 등의 오류가 검사되지 않습니다. 쿼리 매개 변수에 대한 형식 검사뿐 아니라 `IntelliSense` 지원도 제공되지 않습니다.  
  
 [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]에서는 별도의 쿼리 언어를 사용하지 않고도 응용 프로그램 코드에서 집합 기반 쿼리를 작성할 수 있습니다. 메모리 내 데이터 구조체, XML 문서, SQL 데이터베이스 및 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 개체와 같은 다양한 열거 가능 데이터 소스(<xref:System.Collections.IEnumerable> 인터페이스를 구현한 데이터 소스)에 대한 <xref:System.Data.DataSet> 쿼리를 작성할 수 있습니다. 열거 가능한 데이터 소스가 다양한 방법으로 구현되기는 하지만 이러한 데이터 소스는 모두 동일한 구문 및 언어 구문을 노출합니다. 프로그래밍 언어 자체에서 쿼리를 작성할 수 있으므로 컴파일러에서 인식하거나 확인할 수 없는 문자열 리터럴로 포함되는 다른 쿼리 언어를 사용하지 않아도 됩니다. Visual Studio 프로그래머는 컴파일 시간 형식 및 구문 검사를 함으로써 생산성을 높일 수 있습니다 프로그래밍 언어로 쿼리를 통합 하 고 `IntelliSense`입니다. 이러한 기능은 쿼리 디버깅 및 오류 수정에 소요되는 시간을 줄여 줍니다.  
  
 SQL 테이블의 데이터를 메모리에 있는 개체로 전송하는 작업은 번거롭고 오류가 발생하기 쉽습니다. 합니다 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] LINQ to DataSet에 의해 구현 되는 공급자 및 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] 원본 데이터를 변환 <xref:System.Collections.IEnumerable>-개체 컬렉션을 기반으로 합니다. 프로그래머는 쿼리하거나 업데이트할 때 데이터를 항상 <xref:System.Collections.IEnumerable> 컬렉션으로 봅니다. 이러한 컬렉션에 대한 쿼리 작성을 위해 완전한 `IntelliSense` 지원이 제공됩니다.  
  
 세 가지 별도 ADO.NET 가지 [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] 기술: LINQ to DataSet [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)], 및 [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)]합니다. LINQ to DataSet 통해 보다 풍부 하 고 최적화 된 쿼리를 제공 합니다 <xref:System.Data.DataSet> 하 고 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] SQL Server 데이터베이스 스키마를 직접 쿼리할 수 있습니다 및 [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)] 엔터티 데이터 모델을 쿼리할 수 있습니다.  
  
 다음 다이어그램에서는 ADO.NET LINQ 기술과 고급 프로그래밍 언어 및 LINQ 사용 데이터 소스의 관계에 대해 간략하게 설명합니다.  
  
 ![LINQ to ADO.NET 개요](../../../../docs/framework/data/adonet/media/dpue-linqtoadonetoverview-bpuedev11.gif "DPUE_LinqToAdoNetOverview_bpuedev11")  
  
 LINQ에 대 한 자세한 내용은 참조 하세요. [언어 통합 쿼리 (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md)합니다.
  
 다음 섹션에서는 데이터 집합으로, LINQ에 대 한 자세한 정보를 제공 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)], 및 [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)]합니다.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet> ADO.NET 기반이 되 고 널리 사용 되는 연결 되지 않은 프로그래밍 모델의 핵심 요소입니다. LINQ to DataSet에는 개발자가 다양 한 쿼리 기능을 만들 수 <xref:System.Data.DataSet> 다른 많은 데이터 소스에 사용할 수 있는 동일한 쿼리 구성 메커니즘을 사용 하 여 합니다. 자세한 내용은 [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md)을 참조하세요.  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]은 개념적 모델에 매핑할 필요가 없는 개발자에게 유용한 도구입니다. [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]을 사용하면 기존 데이터베이스 스키마에 대해 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 프로그래밍 모델을 직접 사용할 수 있습니다. [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] 개발자가 데이터를 나타내는.NET Framework 클래스를 생성할 수 있습니다. 이렇게 생성된 클래스는 개념적 데이터 모델에 매핑되는 대신 데이터베이스 테이블, 뷰, 저장 프로시저 및 사용자 정의 함수에 직접 매핑됩니다.  
  
 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]을 사용하는 개발자는 XML과 같은 다른 데이터 소스뿐 아니라 메모리 내 컬렉션 및 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]과 동일한 <xref:System.Data.DataSet> 프로그래밍 패턴을 사용하는 저장소 스키마에 대해 코드를 직접 작성할 수 있습니다. 자세한 내용은 [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)을 참조하세요.  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 현재 대부분의 응용 프로그램은 관계형 데이터베이스를 기반으로 작성됩니다. 이러한 응용 프로그램은 특정 시점에 관계형 형식으로 표현된 데이터와 상호 작용해야 합니다. 데이터베이스 스키마가 응용 프로그램 작성에 항상 이상적인 것은 아니며 응용 프로그램의 개념적 모델은 데이터베이스의 논리적 모델과 다릅니다. 엔터티 데이터 모델은 응용 프로그램 데이터를 개체로 조작할 수 있도록 특정 도메인의 데이터를 모델링에 사용할 수 있는 개념적 데이터 모델입니다. 참조 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 자세한 내용은 합니다.  
  
 엔터티 데이터 모델을 통해 관계형 데이터는.NET 환경에서 개체로 제공 됩니다. 이를 통해 개체 계층은 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 지원을 위한 이상적인 대상이 되므로 개발자는 비즈니스 논리를 개발할 때 사용한 언어로 데이터베이스에 대한 쿼리를 작성할 수 있습니다. 이러한 기능은 [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)]로 알려져 있습니다. 자세한 내용은 [LINQ to Entities](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)를 참조하세요.  
  
## <a name="see-also"></a>참고자료

- [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md)
- [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)
- [LINQ to Entities](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)
- [LINQ(Language-Integrated Query)](../../../csharp/programming-guide/concepts/linq/index.md)
- [ADO.NET 개요](ado-net-overview.md)
