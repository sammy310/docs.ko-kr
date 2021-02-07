---
description: '자세히 알아보기: 방법: Navigate 연산자를 사용 하 여 관계 탐색'
title: '방법: 탐색 연산자로 관계 탐색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79996d2d-9b03-4a9d-82cc-7c5e7c2ad93d
ms.openlocfilehash: ff419a959c2ec895a238d37caeedcf1f06812050
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697532"
---
# <a name="how-to-navigate-relationships-with-the-navigate-operator"></a>방법: 탐색 연산자로 관계 탐색

이 항목에서는 <xref:System.Data.EntityClient.EntityCommand> 개체를 사용하여 개념적 모델에 대해 명령을 실행하는 방법과 <xref:System.Data.Metadata.Edm.RefType>를 사용하여 <xref:System.Data.EntityClient.EntityDataReader> 결과를 검색하는 방법을 보여 줍니다.  
  
### <a name="to-run-the-code-in-this-example"></a>이 예제의 코드를 실행하려면  
  
1. 프로젝트에 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 을 추가 하 고 Entity Framework를 사용 하도록 프로젝트를 구성 합니다. 자세한 내용은 [방법: 엔터티 데이터 모델 마법사 사용](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))을 참조 하세요.  
  
2. 애플리케이션의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>예제  

 다음 예에서는 Navigate 연산자를 사용 하 여에서 관계를 탐색 하는 방법을 보여 줍니다 [!INCLUDE[esql](../../../../../includes/esql-md.md)] . [](./language-reference/navigate-entity-sql.md) `Navigate`연산자는 엔터티 인스턴스, 관계 형식, 관계 끝 및 관계 시작과 같은 매개 변수를 사용 합니다. 필요에 따라 엔터티의 인스턴스와 관계 유형만 연산자에 전달할 수 있습니다 `Navigate` .  
  
 [!code-csharp[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#navigatewithnavoperatorwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#navigatewithnavoperatorwithentitycommand)]  
  
## <a name="see-also"></a>참고 항목

- [Entity Framework용 EntityClient 공급자](entityclient-provider-for-the-entity-framework.md)
- [Entity SQL 언어](./language-reference/entity-sql-language.md)
