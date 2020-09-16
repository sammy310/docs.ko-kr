---
title: '방법: EntityConnection 연결 문자열 빌드'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5bd1a748-3df7-4d0a-a607-14f25e3175e9
ms.openlocfilehash: 86ba3956797ff603dd944bfc8df1990df8f23001
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556436"
---
# <a name="how-to-build-an-entityconnection-connection-string"></a>방법: EntityConnection 연결 문자열 빌드
이 항목에서는 <xref:System.Data.EntityClient.EntityConnection>을 작성하는 방법에 대한 예제를 제공합니다.  
  
### <a name="to-run-the-code-in-this-example"></a>이 예제의 코드를 실행하려면  
  
1. 프로젝트에 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 을 추가 하 고 Entity Framework를 사용 하도록 프로젝트를 구성 합니다. 자세한 내용은 [방법: 엔터티 데이터 모델 마법사 사용](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))을 참조 하세요.  
  
2. 애플리케이션의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 기본 공급자에 대한 <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType>를 초기화한 다음 <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType> 개체를 초기화하고 이 개체를 <xref:System.Data.EntityClient.EntityConnection>의 생성자에 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#buildingconnectionstringwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#buildingconnectionstringwithentitycommand)]  
  
## <a name="see-also"></a>참조

- [방법: 개체 컨텍스트로 EntityConnection 사용](/previous-versions/dotnet/netframework-4.0/bb738461(v=vs.100))
- [Entity Framework용 EntityClient 공급자](entityclient-provider-for-the-entity-framework.md)
