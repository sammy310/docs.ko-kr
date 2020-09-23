---
title: '방법: 조인을 사용하여 LINQ와 데이터 결합'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
ms.openlocfilehash: ebda8d3b7fa2e712c337ed2c1fadc580bed7fe61
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075072"
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a>방법: 조인을 사용하여 데이터와 LINQ 결합(Visual Basic)

Visual Basic는 `Join` 및 `Group Join` 쿼리 절을 제공 하 여 컬렉션 간의 공통 값을 기준으로 여러 컬렉션의 내용을 결합할 수 있습니다. 이러한 값을 *키* 값 이라고 합니다. 관계형 데이터베이스 개념에 익숙한 개발자는 절을 `Join` 내부 조인으로 인식 하 고 `Group Join` 절을 효과적으로 왼쪽 우선 외부 조인으로 인식 합니다.  
  
 이 항목의 예제에서는 `Join` 및 쿼리 절을 사용 하 여 데이터를 결합 하는 몇 가지 방법을 보여 줍니다 `Group Join` .  
  
## <a name="create-a-project-and-add-sample-data"></a>프로젝트 만들기 및 샘플 데이터 추가  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a>샘플 데이터 및 형식을 포함 하는 프로젝트를 만들려면  
  
1. 이 항목의 예제를 실행 하려면 Visual Studio를 열고 새 Visual Basic 콘솔 응용 프로그램 프로젝트를 추가 합니다. Visual Basic에서 만든 module1.vb 파일을 두 번 클릭 합니다.  
  
2. 이 항목의 샘플에서는 `Person` `Pet` 다음 코드 예제의 및 형식과 데이터를 사용 합니다. Visual Basic에서 만든 기본 모듈에이 코드를 복사 `Module1` 합니다.  
  
     [!code-vb[VbLINQHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#1)]  
    [!code-vb[VbLINQHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#2)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a>Join 절을 사용 하 여 내부 조인 수행  

 내부 조인은 두 컬렉션의 데이터를 결합 합니다. 지정 된 키 값이 일치 하는 항목이 포함 됩니다. 다른 컬렉션에 일치 하는 항목이 없는 컬렉션 중 하나의 항목은 제외 됩니다.  
  
 Visual Basic에서 LINQ는 내부 조인을 수행 하기 위한 두 가지 옵션, 즉 암시적 조인과 명시적 조인을 제공 합니다.  
  
 암시적 조인은 절에서 조인할 컬렉션을 지정 하 `From` 고 절에서 일치 하는 키 필드를 식별 합니다 `Where` . Visual Basic는 지정 된 키 필드에 따라 두 컬렉션을 암시적으로 조인 합니다.  
  
 `Join`조인에서 사용할 키 필드에 대해 구체적으로 지정 하려는 경우 절을 사용 하 여 명시적 조인을 지정할 수 있습니다. 이 경우에 `Where` 도 절을 사용 하 여 쿼리 결과를 필터링 할 수 있습니다.  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a>Join 절을 사용 하 여 내부 조인을 수행 하려면  
  
1. 프로젝트의 모듈에 다음 코드를 추가 `Module1` 하 여 암시적 및 명시적 내부 조인의 예제를 확인 합니다.  
  
     [!code-vb[VbLINQHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#4)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a>Group Join 절을 사용 하 여 왼쪽 우선 외부 조인을 수행 합니다.  

 왼쪽 우선 외부 조인은 조인의 왼쪽 컬렉션에 있는 모든 항목을 포함 하 고 조인의 오른쪽 컬렉션에서 일치 하는 값만 포함 합니다. 왼쪽 컬렉션에 일치 하는 항목이 없는 조인의 오른쪽 컬렉션에 있는 항목은 쿼리 결과에서 제외 됩니다.  
  
 `Group Join`절은 왼쪽 우선 외부 조인을 적용 합니다. 일반적으로 왼쪽 우선 외부 조인 이라고 하는 것과 절이 반환 하는 작업의 차이는 `Group Join` `Group Join` 절이 왼쪽 컬렉션에 있는 각 항목에 대 한 조인의 오른쪽 컬렉션에서 결과를 그룹화 한다는 것입니다. 관계형 데이터베이스에서 왼쪽 우선 외부 조인은 쿼리 결과의 각 항목이 조인에 있는 두 컬렉션의 일치 하는 항목을 포함 하는 그룹화 되지 않은 결과를 반환 합니다. 이 경우 조인의 왼쪽 컬렉션의 항목이 오른쪽 컬렉션에서 일치 하는 각 항목에 대해 반복 됩니다. 다음 절차를 완료 하면이 모양이 표시 됩니다.  
  
 `Group Join`그룹화 된 각 쿼리 결과에 대 한 항목을 반환 하도록 쿼리를 확장 하 여 쿼리 결과를 그룹화 되지 않은 결과로 검색할 수 있습니다. 이렇게 하려면 `DefaultIfEmpty` 그룹화 된 컬렉션의 메서드를 쿼리해야 합니다. 이렇게 하면 조인의 왼쪽 컬렉션의 항목이 오른쪽 컬렉션에서 일치 하는 결과가 없더라도 쿼리 결과에 계속 포함 됩니다. 조인의 오른쪽 컬렉션에서 일치 하는 값이 없는 경우 기본 결과 값을 제공 하기 위해 쿼리에 코드를 추가할 수 있습니다.  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a>Group Join 절을 사용 하 여 왼쪽 우선 외부 조인을 수행 하려면  
  
1. 프로젝트의 모듈에 다음 코드를 추가 `Module1` 하 여 그룹화 된 왼쪽 우선 외부 조인과 그룹화 되지 않은 왼쪽 우선 외부 조인의 예를 확인 합니다.  
  
     [!code-vb[VbLINQHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#3)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a>복합 키를 사용 하 여 조인 수행  

 `And`또는 절에서 키워드를 사용 하 `Join` 여 `Group Join` 조인 되는 컬렉션의 값을 일치 시킬 때 사용할 여러 키 필드를 식별할 수 있습니다. `And`키워드는 지정 된 모든 키 필드가 조인할 항목에 대해 일치 해야 함을 지정 합니다.  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a>복합 키를 사용 하 여 조인을 수행 하려면  
  
1. 프로젝트의 모듈에 다음 코드를 추가 `Module1` 하 여 복합 키를 사용 하는 조인의 예를 확인 합니다.  
  
     [!code-vb[VbLINQHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#5)]  
  
## <a name="run-the-code"></a>코드 실행  
  
#### <a name="to-add-code-to-run-the-examples"></a>예제를 실행 하는 코드를 추가 하려면  
  
1. `Sub Main` `Module1` 이 항목의 예제를 실행 하려면 프로젝트의 모듈에서를 다음 코드로 바꿉니다.  
  
     [!code-vb[VbLINQHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#6)]  
  
2. F5 키를 눌러 예제를 실행 합니다.  
  
## <a name="see-also"></a>참조

- [LINQ](index.md)
- [Visual Basic의 LINQ 소개](introduction-to-linq.md)
- [Join 절](../../../language-reference/queries/join-clause.md)
- [Group Join 절](../../../language-reference/queries/group-join-clause.md)
- [From 절](../../../language-reference/queries/from-clause.md)
- [Where 절](../../../language-reference/queries/where-clause.md)
- [쿼리](../../../language-reference/queries/index.md)
- [LINQ를 통한 데이터 변환(C#)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)
