---
title: 데이터 정의 언어로 작업
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec50083d-44f4-4093-9b23-5eacd601f96e
ms.openlocfilehash: c30cbbc1eae6d4cbcadb9bfe8d267fb428764971
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200890"
---
# <a name="working-with-data-definition-language"></a>데이터 정의 언어로 작업

.NET Framework 버전 4부터 Entity Framework은 DDL (데이터 정의 언어)을 지원 합니다. 이렇게 하면 연결 문자열 및 스토리지(SSDL) 모델의 메타데이터를 기반으로 데이터베이스 인스턴스를 만들거나 삭제할 수 있습니다.  
  
 <xref:System.Data.Objects.ObjectContext>의 다음 메서드는 연결 문자열과 SSDL 콘텐츠를 사용하여 데이터베이스를 만들거나 삭제하고, 데이터베이스가 있는지 확인하며, 생성된 DDL 스크립트를 확인합니다.  
  
- <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A>  
  
- <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>  
  
- <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>  
  
- <xref:System.Data.Objects.ObjectContext.CreateDatabaseScript%2A>  
  
> [!NOTE]
> DDL 명령을 실행하려면 충분한 권한이 있어야 합니다.  
  
 위에 나열된 메서드는 대부분의 작업을 기본 ADO.NET 데이터 공급자에 위임합니다. 데이터베이스 개체를 생성하는 데 사용되는 명명 규칙이 쿼리 및 업데이트에 사용되는 규칙과 일치하는지 확인하는 것은 공급자의 책임입니다.  
  
 다음 예제에서는 기존 모델을 기반으로 데이터베이스를 생성하는 방법을 보여 줍니다. 또한 새 엔터티 개체를 개체 컨텍스트에 추가한 다음 데이터베이스에 저장합니다.  
  
## <a name="procedures"></a>프로시저  
  
### <a name="to-define-a-database-based-on-the-existing-model"></a>기존 모델을 기반으로 데이터베이스를 정의하려면  
  
1. 콘솔 애플리케이션을 만듭니다.  
  
2. 애플리케이션에 기존 모델을 추가합니다.  
  
    1. 이라는 빈 모델을 추가 `SchoolModel` 합니다. 빈 모델을 만들려면 [방법: 새 .Edmx 파일 만들기](/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100)) 항목을 참조 하세요.  
  
     SchoolModel.edmx 파일이 프로젝트에 추가됩니다.  
  
    1. [School](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) 모델 토픽에서 school 모델에 대 한 개념, 저장소 및 매핑 콘텐츠를 복사 합니다.  
  
    2. SchoolModel.edmx 파일을 열고 콘텐츠를 `edmx:Runtime` 태그 안에 붙여 넣습니다.  
  
3. 다음 코드를 main 함수에 추가합니다. 이 코드에서는 데이터베이스 서버에 대한 연결 문자열을 초기화하고 DDL 스크립트를 확인하며, 데이터베이스를 만들고 새 엔터티를 컨텍스트에 추가한 다음 변경 내용을 데이터베이스에 저장합니다.  
  
     [!code-csharp[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/csharp/VS_Snippets_Data/DP ObjectServices Concepts/CS/Source.cs#ddl)]
     [!code-vb[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP ObjectServices Concepts/VB/Source.vb#ddl)]
