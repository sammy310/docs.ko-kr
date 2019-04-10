---
title: '방법: RefType 결과를 반환하는 쿼리 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dbbfbcd-93f5-4546-9dbf-e5fa290b69fa
ms.openlocfilehash: 7a8f08717743971c0378d9130d4fcea0621dae97
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209696"
---
# <a name="how-to-execute-a-query-that-returns-reftype-results"></a>방법: RefType 결과를 반환하는 쿼리 실행
이 항목에서는 <xref:System.Data.EntityClient.EntityCommand> 개체를 사용하여 개념적 모델에 대해 명령을 실행하는 방법과 <xref:System.Data.Metadata.Edm.RefType>를 사용하여 <xref:System.Data.EntityClient.EntityDataReader> 결과를 검색하는 방법을 보여 줍니다.  
  
### <a name="to-run-the-code-in-this-example"></a>이 예제의 코드를 실행하려면  
  
1.  추가 합니다 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 프로젝트에 사용 하도록 프로젝트를 구성 하 고는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]합니다. 자세한 내용은 [방법: 엔터티 데이터 모델 마법사를 사용 하 여](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))입니다.  
  
2.  응용 프로그램의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>예제  
 이 예제에서는 <xref:System.Data.Metadata.Edm.RefType> 결과를 반환하는 쿼리를 실행합니다. 다음 쿼리를 `ExectueRefTypeQuery` 함수에 인수로 전달하면 이 함수는 엔터티에 대한 참조를 반환합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#REF2](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref2)]  
  
 다음과 같은 매개 변수가 있는 쿼리를 전달하는 경우 <xref:System.Data.EntityClient.EntityParameter> 개체를 <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> 개체의 <xref:System.Data.EntityClient.EntityCommand> 속성에 추가합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#REF3](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref3)]  
  
 [!code-csharp[DP EntityServices Concepts#eSQLRefTypes](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#esqlreftypes)]
 [!code-vb[DP EntityServices Concepts#eSQLRefTypes](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#esqlreftypes)]  
  
## <a name="see-also"></a>참고자료

- [엔터티 SQL 참조](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Entity Framework용 EntityClient 공급자](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
