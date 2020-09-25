---
title: '방법: 복합 형식을 반환하는 쿼리 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: e5358e3a1295b180356ed6c127111313b44de277
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198485"
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a>방법: 복합 형식을 반환하는 쿼리 실행

이 항목에서는 복합 형식의 속성이 포함된 엔터티 형식 개체를 반환하는 [!INCLUDE[esql](../../../../../includes/esql-md.md)] 쿼리를 실행하는 방법을 보여 줍니다.  
  
### <a name="to-run-the-code-in-this-example"></a>이 예제의 코드를 실행하려면  
  
1. 프로젝트에 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 을 추가 하 고 Entity Framework를 사용 하도록 프로젝트를 구성 합니다. 자세한 내용은 [방법: 엔터티 데이터 모델 마법사 사용](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))을 참조 하세요.  
  
2. 애플리케이션의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. .Edmx 파일을 두 번 클릭 하 여 Entity Designer의 [모델 브라우저 창](/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) 에 모델을 표시 합니다. Entity Designer 화면에서 `Email` `Phone` 엔터티 형식의 및 속성을 선택 하 `Contact` 고 마우스 오른쪽 단추를 클릭 한 다음 **새 복합 형식으로 리팩터링**을 선택 합니다.  
  
4. 선택한 및 속성을 포함 하는 새 복합 형식이 `Email` `Phone` **모델 브라우저**에 추가 됩니다. 복합 형식에는 기본 이름이 지정 됩니다. `EmailPhone` **속성** 창에서 형식의 이름을으로 바꿉니다. 또한 새 `ComplexProperty` 속성이 `Contact` 엔터티 형식에 추가됩니다. 속성의 이름을 `EmailPhoneComplexType.`으로 바꿉니다.  
  
     엔터티 데이터 모델 마법사를 사용 하 여 복합 형식을 만들고 수정 하는 방법에 대 한 자세한 내용은 [방법: 기존 속성을 복합 형식 속성으로 리팩터링](/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) 및 [방법: 복합 형식 만들기 및 수정](/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100))을 참조 하세요.  
  
## <a name="example"></a>예제  

 다음 예제에서는 개체의 컬렉션을 반환 하 `Contact` 고 개체의 두 속성 `Contact` `ContactID` 및 복합 형식의 값을 표시 하는 쿼리를 실행 합니다 `EmailPhoneComplexType` .  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
