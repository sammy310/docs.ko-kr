---
title: 쿼리 작업의 형식 관계(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variable relationships [LINQ in Visual Basic]
- type information inferred [LINQ in Visual Basic]
- type relationships [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], type relationships
- data sources [LINQ in Visual Basic], type relationships
- LINQ [Visual Basic], type relationships
- inferring type information [LINQ in Visual Basic]
- relationships [LINQ in Visual Basic]
ms.assetid: b5ff4da5-f3fd-4a8e-aaac-1cbf52fa16f6
ms.openlocfilehash: fd2bcfad0ae24288887500ae6286e6ac73fddac5
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822338"
---
# <a name="type-relationships-in-query-operations-visual-basic"></a>쿼리 작업의 형식 관계(Visual Basic)
사용 되는 변수 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] 쿼리 작업은 강력한 형식 이어야 하며 서로 호환 되어야 합니다. 강력한 형식 지정 데이터 원본, 쿼리 자체 및 쿼리 실행에 사용 됩니다. 다음 그림에서는 설명 하는 용어를 식별 하는 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 합니다. 쿼리 부분에 대 한 자세한 내용은 참조 하세요. [기본 쿼리 작업 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md)합니다.  
  
 ![요소가 강조 표시 된 의사 코드 쿼리를 보여주는 스크린샷.](./media/type-relationships-in-query-operations/linq-query-description-terms.png)  
  
 쿼리에서 범위 변수의 형식을 데이터 소스에 있는 요소의 형식과 호환 되어야 합니다. 쿼리 변수의 형식에 정의 된 시퀀스 요소와 호환 되어야 합니다는 `Select` 절. 마지막으로 시퀀스 요소의 형식입니다도 호환 되어야에 사용 되는 루프 제어 변수의 형식을 사용 하 여는 `For Each` 쿼리를 실행 하는 문입니다. 이 강력한 형식화 컴파일 타임 형식 오류 식별을 용이 하 게 합니다.  
  
 Visual Basic 편리 강력한 형식 지정 라고도 지역 형식 유추를 구현 하 여 *암시적 형식 지정*합니다. 기능은 이전 예제에서 사용 됩니다 하 고 표시 될 전체에서 사용 되는 것은 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 샘플 및 설명서입니다. Visual basic에서 지역 형식 유추를 사용 하 여 수행 됩니다는 `Dim` 문 없이 `As` 절. 다음 예에서 `city` 문자열로 강력 하 게 형식화 됩니다.  
  
 [!code-vb[VbLINQTypeRels#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#1)]  
  
> [!NOTE]
>  경우에만 작동 하는 지역 형식 유추 `Option Infer` 로 설정 된 `On`합니다. 자세한 내용은 [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md)합니다.  
  
 그러나 쿼리에서 로컬 형식 유추를 사용 하는 경우에 동일한 형식 관계는 데이터 원본에서 변수, 쿼리 변수 및 쿼리 실행 루프 중입니다. 작성 하는 경우 이러한 형식 관계에 대 한 기본 이해 하는 것이 유용 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 또는 샘플 및 설명서의 코드 예제를 사용 합니다.  
  
 데이터 원본에서 반환 되는 형식과 일치 하지 않는 범위 변수에 명시적 형식을 지정 해야 합니다. 사용 하 여 범위 변수의 형식을 지정할 수 있습니다는 `As` 절. 그러나이 인해 오류로 변환 되는 경우는 [축소 변환을](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) 및 `Option Strict` 로 설정 되어 `On`합니다. 따라서 데이터 원본에서 검색 된 값에서 변환을 수행 하는 것이 좋습니다. 사용 하 여 명시적 범위 변수 형식으로 값을 데이터 원본에서 변환할 수는 <xref:System.Linq.Enumerable.Cast%2A> 메서드. 선택한 값을 캐스트할 수도 있습니다는 `Select` 명시적 형식 범위 변수 형식에서 다른 절. 이러한 요소는 다음 코드에 나와 있습니다.  
  
 [!code-vb[VbLINQTypeRels#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#4)]  
  
## <a name="queries-that-return-entire-elements-of-the-source-data"></a>원본 데이터의 전체 요소를 반환 하는 쿼리  
 다음 예제와 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 원본 데이터에서 선택한 요소의 시퀀스를 반환 하는 작업을 쿼리 합니다. 원본 `names`, 문자열의 배열을 포함 쿼리 출력은 M으로 시작 하는 문자열을 포함 하는 시퀀스입니다.  
  
 [!code-vb[VbLINQTypeRels#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#2)]  
  
 이 다음 코드와 동일 하지만 훨씬 더 간결 하 고 더 쉽게 작성할 수 있습니다. 쿼리에서 지역 형식 유추를 사용 하는 것은 Visual Basic의 기본 스타일입니다.  
  
 [!code-vb[VbLINQTypeRels#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#3)]  
  
 유형은 암시적 또는 명시적으로 결정 됩니다 없이 모두 이전 코드 예제에서는 다음 관계가 있습니다.  
  
1.  데이터 원본에 있는 요소의 형식 `names`, 범위 변수의 형식이 `name`, 쿼리에서 합니다.  
  
2.  현재 선택 된 개체의 형식을 `name`, 쿼리 변수 형식을 결정 `mNames`합니다. 여기 `name` 문자열 이므로 쿼리 변수는 Visual Basic에서 IEnumerable (Of String).  
  
3.  에 정의 된 쿼리 `mNames` 에서 실행 되는 `For Each` 루프입니다. 루프는 쿼리를 실행 한 결과 반복 합니다. 때문에 `mNames`실행 되는 경우 루프 반복 변수, 문자열의 시퀀스를 반환 하는 `nm`, 문자열 이기도 합니다.  
  
## <a name="queries-that-return-one-field-from-selected-elements"></a>선택한 요소에서 하나의 필드를 반환 하는 쿼리  
 다음 예제와 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 데이터 원본에서 선택한 각 요소의 부분만 포함 된 시퀀스를 반환 하는 작업을 쿼리 합니다. 쿼리는 컬렉션 `Customer` 데이터 원본으로 개체를 프로젝트에 해당 합니다 `Name` 결과의 속성입니다. 고객 이름을 문자열 이기 때문에 쿼리 출력으로 문자열 시퀀스를 생성 합니다.  
  
```vb  
' Method GetTable returns a table of Customer objects.  
Dim customers = db.GetTable(Of Customer)()  
Dim custNames = From cust In customers   
                Where cust.City = "London"   
                Select cust.Name  
  
For Each custName In custNames  
    Console.WriteLine(custName)  
Next  
```  
  
 변수 간의 관계는 간단한 예제의 경우와 같습니다.  
  
1.  데이터 원본에 있는 요소의 형식 `customers`, 범위 변수의 형식이 `cust`, 쿼리에서 합니다. 이 예에서 유형이 `Customer`합니다.  
  
2.  `Select` 문 반환 합니다 `Name` 의 각 속성 `Customer` 개체 전체가 아니라 개체입니다. 때문에 `Name` 쿼리 변수를 문자열 `custNames`, 다시 되지 IEnumerable (Of String)의 `Customer`합니다.  
  
3.  때문에 `custNames` 문자열의 시퀀스를 나타냅니다는 `For Each` 루프의 반복 변수도 `custName`, 문자열 이어야 합니다.  
  
 지역 형식 유추를 하지 않고 앞의 예제를 쓰고 다음 예제와 같이 이해 하기에 다소 복잡 해질 것입니다.  
  
```vb  
' Method GetTable returns a table of Customer objects.  
 Dim customers As Table(Of Customer) = db.GetTable(Of Customer)()  
 Dim custNames As IEnumerable(Of String) =  
     From cust As Customer In customers   
     Where cust.City = "London"   
     Select cust.Name  
  
 For Each custName As String In custNames  
     Console.WriteLine(custName)  
 Next  
```  
  
## <a name="queries-that-require-anonymous-types"></a>익명 형식이 필요로 하는 쿼리  
 다음 예제에서는 보다 복잡 한 상황을 보여 줍니다. 이전 예제에서는 모든 변수 형식을 명시적으로 지정 하기에 편리한 없었습니다. 이 예제에서는 불가능 합니다. 전체를 선택 하는 대신 `Customer` 데이터 원본 또는 각 요소에서 단일 필드에서 요소를 `Select` 원래의 두 속성을 반환 하는 절이 쿼리에 `Customer` 개체: `Name` 및 `City`합니다. 에 대 한 응답을 `Select` 절 컴파일러가 해당 두 가지 속성을 포함 하는 익명 형식을 정의 합니다. 실행 결과 `nameCityQuery` 에 `For Each` 루프는 새 익명 형식의 인스턴스 컬렉션입니다. 익명 형식에 사용 가능한 이름이 없으므로, 유형을 지정할 수 없습니다 `nameCityQuery` 또는 `custInfo` 명시적으로 합니다. 즉, 익명 형식, 이름이 없는 형식 대신 사용 하 `String` 에서 `IEnumerable(Of String)`합니다. 자세한 내용은 [무명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하세요.  
  
```vb  
' Method GetTable returns a table of Customer objects.  
Dim customers = db.GetTable(Of Customer)()  
Dim nameCityQuery = From cust In customers   
                    Where cust.City = "London"   
                    Select cust.Name, cust.City  
  
For Each custInfo In nameCityQuery  
    Console.WriteLine(custInfo.Name)  
Next  
```  
  
 이전 예제에서 모든 변수에 대 한 형식을 지정 하려면 가능한 경우에 관계 ֿ ´.  
  
1.  데이터 원본에 있는 요소의 형식은 쿼리에서 범위 변수의 형식을 다시 합니다. 이 예에서 `cust` 의 인스턴스가 `Customer`합니다.  
  
2.  때문에 합니다 `Select` 문에서 쿼리 변수를 무명 형식이 생성 `nameCityQuery`, 익명 형식으로 암시적으로 형식화 해야 합니다. 익명 형식을 사용 가능한 이름이 없으므로 있으며 따라서 명시적으로 지정할 수 없습니다.  
  
3.  반복 변수 형식의 `For Each` 루프에는 2 단계에서 만든 익명 형식입니다. 형식에 사용 가능한 이름이 없으므로, 루프 반복 변수의 형식이 암시적으로 결정 해야 합니다.  
  
## <a name="see-also"></a>참고자료

- [Visual Basic에서 LINQ 시작](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [쿼리](../../../../visual-basic/language-reference/queries/index.md)
