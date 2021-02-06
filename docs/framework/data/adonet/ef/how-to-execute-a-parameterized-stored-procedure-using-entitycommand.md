---
description: '자세한 정보: 방법: EntityCommand를 사용 하 여 매개 변수가 있는 저장 프로시저 실행'
title: '방법: EntityCommand를 사용하여 매개 변수 있는 저장 프로시저 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4f5639bf-bb7f-4982-bb1d-c7caa4348888
ms.openlocfilehash: a45c9a276cc33037a4d353e05d1174c9748aab82
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650692"
---
# <a name="how-to-execute-a-parameterized-stored-procedure-using-entitycommand"></a>방법: EntityCommand를 사용하여 매개 변수 있는 저장 프로시저 실행

이 항목에서는 <xref:System.Data.EntityClient.EntityCommand> 클래스를 사용하여 매개 변수가 있는 저장 프로시저를 실행하는 방법을 보여 줍니다.  
  
### <a name="to-run-the-code-in-this-example"></a>이 예제의 코드를 실행하려면  
  
1. 프로젝트에 [School 모델](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) 을 추가 하 고 Entity Framework를 사용 하도록 프로젝트를 구성 합니다. 자세한 내용은 [방법: 엔터티 데이터 모델 마법사 사용](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))을 참조 하세요.  
  
2. 애플리케이션의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. `GetStudentGrades` 저장 프로시저를 가져오고 `CourseGrade` 엔터티를 반환 형식으로 지정합니다. 저장 프로시저를 가져오는 방법에 대 한 자세한 내용은 [방법: 저장 프로시저 가져오기](/previous-versions/dotnet/netframework-4.0/bb896231(v=vs.100))를 참조 하세요.  
  
## <a name="example"></a>예제  

 다음 코드에서는 `GetStudentGrades`가 필수 매개 변수인 `StudentId` 저장 프로시저를 실행합니다. 그런 다음 <xref:System.Data.EntityClient.EntityDataReader>에서 결과를 읽습니다.  
  
 [!code-csharp[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#storedprocwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#storedprocwithentitycommand)]  
  
## <a name="see-also"></a>참고 항목

- [Entity Framework용 EntityClient 공급자](entityclient-provider-for-the-entity-framework.md)
