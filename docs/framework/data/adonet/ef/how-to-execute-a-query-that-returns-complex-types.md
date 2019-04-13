---
title: '방법: 복합 형식을 반환하는 쿼리 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: a428f54c3834ccdf6a0c7a5bfce8307172724524
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59322890"
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a>방법: 복합 형식을 반환하는 쿼리 실행
이 항목에서는 복합 형식의 속성이 포함된 엔터티 형식 개체를 반환하는 [!INCLUDE[esql](../../../../../includes/esql-md.md)] 쿼리를 실행하는 방법을 보여 줍니다.  
  
### <a name="to-run-the-code-in-this-example"></a>이 예제의 코드를 실행하려면  
  
1. 추가 합니다 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 프로젝트에 사용 하도록 프로젝트를 구성 하 고는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]합니다. 자세한 내용은 [방법: 엔터티 데이터 모델 마법사를 사용 하 여](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))입니다.  
  
2. 응용 프로그램의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. 모델을 표시 하려면.edmx 파일을 두 번 클릭 합니다 [Model 브라우저 창](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) 엔터티 디자이너입니다. Entity Designer 화면에서 선택 합니다 `Email` 및 `Phone` 의 속성을 `Contact` 엔터티 형식에 다음 마우스 오른쪽 단추로 **새 복합 형식으로 리팩터링**합니다.  
  
4. 선택 된 새 복합 형식이 `Email` 하 고 `Phone` 속성에 추가 됩니다는 **Model 브라우저**합니다. 복합 형식에 기본 이름이 지정 됩니다:으로 형식 이름 바꾸기 `EmailPhone` 에 **속성** 창. 또한 새 `ComplexProperty` 속성이 `Contact` 엔터티 형식에 추가됩니다. 속성 이름 바꾸기 `EmailPhoneComplexType.`  
  
     만들기 및 엔터티 데이터 모델 마법사를 사용 하 여 복합 형식을 수정 하는 방법에 대 한 내용은 [방법: 기존 속성을 복합 형식 속성으로 리팩터링](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) 고 [방법: 복합 형식 만들기 및 수정](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100))합니다.  
  
## <a name="example"></a>예제  
 컬렉션을 반환 하는 쿼리를 실행 하는 다음 예제 `Contact` 개체 및의 두 속성을 표시 합니다 `Contact` 개체: `ContactID` 값과는 `EmailPhoneComplexType` 복합 형식입니다.  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
