---
title: 쿼리 작성
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: 6a9f229697ce3d6328c6fb09d18d4cc2627eab10
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351025"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a>연습: Visual Basic에서 쿼리 작성

이 연습에서는 Visual Basic 언어 기능을 사용 하 여 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] 쿼리 식을 작성 하는 방법을 보여 줍니다. 이 연습에서는 학생 개체 목록에 대 한 쿼리를 만드는 방법, 쿼리를 실행 하는 방법 및 수정 하는 방법을 보여 줍니다. 이 쿼리는 개체 이니셜라이저, 로컬 형식 유추 및 익명 형식을 비롯 한 여러 기능을 통합 합니다.

이 연습을 완료 한 후 관심 있는 특정 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 공급자의 샘플과 설명서로 이동할 준비가 됩니다. [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 공급자는 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], LINQ to DataSet 및 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]를 포함 합니다.

## <a name="create-a-project"></a>프로젝트 만들기

### <a name="to-create-a-console-application-project"></a>콘솔 응용 프로그램 프로젝트를 만들려면

1. Visual Studio를 시작합니다.

2. **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.

3. **설치 된 템플릿** 목록에서 **Visual Basic**을 클릭 합니다.

4. 프로젝트 형식 목록에서 **콘솔 응용 프로그램**을 클릭 합니다. **이름** 상자에 프로젝트의 이름을 입력 하 고 **확인**을 클릭 합니다.

    프로젝트가 생성 됩니다. 기본적으로이 파일에는 System.object에 대 한 참조가 포함 되어 있습니다. 또한 [프로젝트 디자이너 (Visual Basic)의 참조 페이지](/visualstudio/ide/reference/references-page-project-designer-visual-basic) 에서 **가져온 네임 스페이스** 목록에는 <xref:System.Linq?displayProperty=nameWithType> 네임 스페이스가 포함 됩니다.

5. [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)에서 **옵션 유추** 가 **On**으로 설정 되어 있는지 확인 합니다.

## <a name="add-an-in-memory-data-source"></a>메모리 내 데이터 원본 추가

이 연습에서 쿼리에 대 한 데이터 소스는 `Student` 개체의 목록입니다. 각 `Student` 개체에는 학생 본문의 이름, 성, 클래스 연도 및 교육 등급이 포함 되어 있습니다.

### <a name="to-add-the-data-source"></a>데이터 소스를 추가하려면

- `Student` 클래스를 정의 하 고 클래스의 인스턴스 목록을 만듭니다.

  > [!IMPORTANT]
  > `Student` 클래스를 정의 하 고 연습 예제에 사용 된 목록을 만드는 데 필요한 코드는 [방법: 항목 목록 만들기](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)에서 제공 됩니다. 여기에서 복사 하 여 프로젝트에 붙여 넣을 수 있습니다. 새 코드는 프로젝트를 만들 때 표시 된 코드를 대체 합니다.

### <a name="to-add-a-new-student-to-the-students-list"></a>학생 목록에 새 학생을 추가 하려면

- `getStudents` 메서드의 패턴에 따라 `Student` 클래스의 다른 인스턴스를 목록에 추가 합니다. 학생을 추가 하면 개체 이니셜라이저를 소개 합니다. 자세한 내용은 [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)을 참조 하세요.

## <a name="create-a-query"></a>쿼리 만들기

이 섹션에 추가 된 쿼리는 실행 될 때 교육 등급이 상위 10 개에 배치 하는 학생의 목록을 생성 합니다. 쿼리가 매번 전체 `Student` 개체를 선택 하기 때문에 쿼리 결과의 형식이 `IEnumerable(Of Student)`됩니다. 그러나 일반적으로 쿼리 형식은 쿼리 정의에 지정 되지 않습니다. 대신 컴파일러는 로컬 형식 유추를 사용 하 여 형식을 결정 합니다. 자세한 내용은 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)를 참조 하세요. 쿼리의 범위 변수 `currentStudent`는 소스의 각 `Student` 인스턴스에 대 한 참조 역할을 하며, `students`는 `students`에서 각 개체의 속성에 대 한 액세스를 제공 합니다.

### <a name="to-create-a-simple-query"></a>단순 쿼리를 작성하려면

1. 프로젝트의 `Main` 메서드에서 다음과 같이 표시 되는 위치를 찾습니다.

    [!code-vb[VbLINQWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#1)]

    다음 코드를 복사 하 여에 붙여넣습니다.

    [!code-vb[VbLINQWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#2)]

2. 코드의 `studentQuery` 위로 마우스 포인터를 가져가면 컴파일러 할당 형식이 `IEnumerable(Of Student)`되었는지 확인 합니다.

## <a name="run-the-query"></a>쿼리 실행

쿼리 실행 결과가 아닌 쿼리 정의를 포함 하 `studentQuery` 변수입니다. 쿼리를 실행 하는 일반적인 메커니즘은 `For Each` 루프입니다. 반환 된 시퀀스의 각 요소는 루프 반복 변수를 통해 액세스 됩니다. 쿼리 실행에 대 한 자세한 내용은 [첫 번째 LINQ 쿼리 작성](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)을 참조 하세요.

### <a name="to-run-the-query"></a>쿼리를 실행 하려면

1. 프로젝트의 쿼리 아래에 다음 `For Each` 루프를 추가 합니다.

    [!code-vb[VbLINQWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#3)]

2. 루프 제어 변수 위에 마우스 포인터를 올려 `studentRecord` 데이터 형식을 확인 합니다. `studentQuery` `Student` 인스턴스의 컬렉션을 반환 하기 때문에 `studentRecord` 형식은 `Student`유추 됩니다.

3. CTRL + F5 키를 눌러 응용 프로그램을 빌드하고 실행 합니다. 콘솔 창에서 결과를 확인 합니다.

## <a name="modify-the-query"></a>쿼리 수정

쿼리 결과가 지정 된 순서로 검색 되는 것이 더 쉽습니다. 사용 가능한 필드에 따라 반환 된 시퀀스를 정렬할 수 있습니다.

### <a name="to-order-the-results"></a>결과를 정렬하려면

1. 쿼리의 `Where` 문과 `Select` 문 사이에 다음 `Order By` 절을 추가 합니다. `Order By` 절은 각 학생의 성에 따라 오름차순으로 결과를 정렬 합니다.

    ```vb
    Order By currentStudent.Last Ascending
    ```

2. 성을 기준으로 정렬 한 다음 이름을 기준으로 정렬 하려면 두 필드를 모두 쿼리에 추가 합니다.

    ```vb
    Order By currentStudent.Last Ascending, currentStudent.First Ascending
    ```

    `Descending`를 Z에서 A로 정렬 하도록 지정할 수도 있습니다.

3. CTRL + F5 키를 눌러 응용 프로그램을 빌드하고 실행 합니다. 콘솔 창에서 결과를 확인 합니다.

### <a name="to-introduce-a-local-identifier"></a>로컬 식별자를 도입 하려면

1. 이 섹션의 코드를 추가 하 여 쿼리 식의 로컬 식별자를 소개 합니다. 로컬 식별자에는 중간 결과가 포함 됩니다. 다음 예제에서 `name`는 학생의 성과 이름에 대 한 연결을 포함 하는 식별자입니다. 로컬 식별자를 편리 하 게 사용 하거나 여러 번 계산 되는 식의 결과를 저장 하 여 성능을 향상 시킬 수 있습니다.

    [!code-vb[VbLINQWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#4)]

2. CTRL + F5 키를 눌러 응용 프로그램을 빌드하고 실행 합니다. 콘솔 창에서 결과를 확인 합니다.

### <a name="to-project-one-field-in-the-select-clause"></a>Select 절에서 하나의 필드를 프로젝션 하려면

1. 이 섹션에서 쿼리 및 `For Each` 루프를 추가 하 여 요소가 소스의 요소와 다른 시퀀스를 생성 하는 쿼리를 만듭니다. 다음 예제에서 원본은 `Student` 개체의 컬렉션 이지만 각 개체의 한 멤버만 반환 됩니다. 성이 가르시아 섬 인 학생의 첫 번째 이름입니다. `currentStudent.First`는 문자열 이기 때문에 `studentQuery3`에서 반환 된 시퀀스의 데이터 형식은 문자열 시퀀스인 `IEnumerable(Of String)`됩니다. 이전 예제에서와 같이 `studentQuery3`에 대 한 데이터 형식의 할당은 컴파일러가 지역 형식 유추를 사용 하 여 확인할 수 있도록 남아 있습니다.

    [!code-vb[VbLINQWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#5)]

2. 코드의 `studentQuery3` 위로 마우스 포인터를 가져가면 할당 된 형식이 `IEnumerable(Of String)`되었는지 확인 합니다.

3. CTRL + F5 키를 눌러 응용 프로그램을 빌드하고 실행 합니다. 콘솔 창에서 결과를 확인 합니다.

### <a name="to-create-an-anonymous-type-in-the-select-clause"></a>Select 절에서 익명 형식을 만들려면

1. 쿼리에서 익명 형식이 사용 되는 방법을 보려면이 섹션의 코드를 추가 합니다. 전체 레코드 (이전 예제에서는`currentStudent` 레코드) 또는 단일 필드 (이전 섹션의`First`)가 아니라 데이터 원본에서 여러 필드를 반환 하려는 경우 쿼리에서이를 사용 합니다. 결과에 포함할 필드를 포함 하는 새 명명 된 형식을 정의 하는 대신 `Select` 절에서 필드를 지정 하면 컴파일러에서 해당 필드를 속성으로 사용 하 여 익명 형식을 만듭니다. 자세한 내용은 [무명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하세요.

    다음 예에서는 교육용 순위를 1에서 10 사이에 있는 seniors의 이름과 순위를 반환 하는 쿼리를 만듭니다. 이 예제에서는 `Select` 절이 무명 형식의 인스턴스를 반환 하 고 익명 형식에 사용할 수 있는 이름이 없기 때문에 `studentQuery4` 형식을 유추 해야 합니다.

    [!code-vb[VbLINQWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#6)]

2. CTRL + F5 키를 눌러 응용 프로그램을 빌드하고 실행 합니다. 콘솔 창에서 결과를 확인 합니다.

## <a name="additional-examples"></a>추가 예

기본 사항을 이해 했으므로 다음은 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리의 유연성과 성능을 보여 주는 추가 예제 목록입니다. 각 예제 앞에는 수행 되는 작업에 대 한 간략 한 설명이 나와 있습니다. 각 쿼리에 대 한 쿼리 결과 변수 위로 마우스 포인터를 가져가면 유추 된 형식을 볼 수 있습니다. `For Each` 루프를 사용 하 여 결과를 생성 합니다.

[!code-vb[VbLINQWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#7)]

## <a name="additional-information"></a>추가 정보

쿼리 작업의 기본 개념을 잘 알고 있으면 관심 있는 특정 형식의 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 공급자에 대 한 설명서와 예제를 읽을 준비가 된 것입니다.

- [LINQ to Objects](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)

- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)

- [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)

- [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)

## <a name="see-also"></a>참고 항목

- [LINQ(Language-Integrated Query)(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
- [Visual Basic에서 LINQ 시작](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [개체 이니셜라이저: 명명된 형식과 익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [쿼리](../../../../visual-basic/language-reference/queries/index.md)
