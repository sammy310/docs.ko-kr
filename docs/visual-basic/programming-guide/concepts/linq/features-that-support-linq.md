---
title: LINQ를 지 원하는 기능
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
ms.openlocfilehash: e81d0434aa60e0c7b316b72fb78ebfe2a3782cbb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353512"
---
# <a name="visual-basic-features-that-support-linq"></a>LINQ를 지원하는 Visual Basic 기능
이름 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]는 언어에서 직접 쿼리 구문 및 기타 언어 구문을 지 원하는 Visual Basic의 기술을 나타냅니다. [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]를 사용 하면 외부 데이터 원본에 대해 쿼리 하는 새 언어를 배울 필요가 없습니다. Visual Basic를 사용 하 여 관계형 데이터베이스, XML 저장소 또는 개체의 데이터에 대해 쿼리할 수 있습니다. 이러한 쿼리 기능을 언어에 통합 하면 구문 오류 및 형식 안전성에 대 한 컴파일 시간 검사를 수행할 수 있습니다. 또한이 통합은 Visual Basic에서 다양 한 가변 쿼리를 작성 하기 위해 알고 있어야 하는 사항 대부분을 이미 알고 있습니다.  
  
 다음 섹션에서는 소개 문서, 코드 예제 및 예제 응용 프로그램을 읽을 수 있는 충분 한 정보를 제공 하는 언어 구문에 대해 설명 합니다. 또한 링크를 클릭 하 여 언어 기능을 함께 사용 하 여 언어 통합 쿼리를 사용 하는 방법에 대 한 자세한 설명을 찾을 수 있습니다. [연습: Visual Basic에서 쿼리 작성](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)을 시작 하는 것이 좋습니다.  
  
## <a name="query-expressions"></a>쿼리 식  
 Visual Basic의 쿼리 식은 SQL 또는 XQuery와 유사한 선언적 구문으로 표현 될 수 있습니다. 컴파일 시간에 쿼리 구문은 표준 쿼리 연산자 확장 메서드의 LINQ 공급자 구현에 대 한 메서드 호출로 변환 됩니다. 응용 프로그램은 `Imports` 문으로 적절 한 네임 스페이스를 지정 하 여 범위 내에 있는 표준 쿼리 연산자를 제어 합니다. Visual Basic 쿼리 식의 구문은 다음과 같습니다.  
  
 [!code-vb[VbLINQVbFeatures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#1)]  
  
 자세한 내용은 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)를 참조 하세요.  
  
## <a name="implicitly-typed-variables"></a>암시적으로 형식화 된 변수  
 변수를 선언 하 고 초기화할 때 형식을 명시적으로 지정 하는 대신 컴파일러가 형식을 유추 하 고 할당 하도록 할 수 있습니다. 이를 *로컬 형식 유추*라고 합니다.  
  
 형식을 명시적으로 지정 하는 변수와 마찬가지로 형식이 유추 되는 변수가 강력한 형식입니다. 지역 형식 유추는 메서드 본문 내에서 지역 변수를 정의 하는 경우에만 작동 합니다. 자세한 내용은 [Option 유추 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md) 및 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)를 참조 하세요.  
  
 다음 예제에서는 로컬 형식 유추를 보여 줍니다. 이 예를 사용 하려면 `Option Infer`를 `On`으로 설정 해야 합니다.  
  
 [!code-vb[VbLINQVbFeatures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#2)]  
  
 로컬 형식 유추를 사용 하 여 익명 형식을 만들 수도 있습니다 .이는이 단원의 뒷부분에 설명 되어 있으며 LINQ 쿼리에 필요 합니다.  
  
 다음 LINQ 예제에서는 `Option Infer` `On` 또는 `Off`경우 형식 유추가 발생 합니다. `Option Infer` `Off` 하 고 `Option Strict`를 `On`하면 컴파일 시간 오류가 발생 합니다.  
  
 [!code-vb[VbLINQVbFeatures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#3)]  
  
## <a name="object-initializers"></a>개체 이니셜라이저  
 쿼리 결과를 저장 하는 무명 형식을 만들어야 하는 경우에는 쿼리 식에 개체 이니셜라이저가 사용 됩니다. 또한 쿼리 외부의 명명 된 형식의 개체를 초기화 하는 데 사용할 수 있습니다. 개체 이니셜라이저를 사용 하면 명시적으로 생성자를 호출 하지 않고 단일 줄로 개체를 초기화할 수 있습니다. 다른 속성과 함께 공용 `Name` 및 `Phone` 속성을 가진 `Customer` 라는 클래스가 있다고 가정 하면 다음과 같은 방식으로 개체 이니셜라이저를 사용할 수 있습니다.  
  
 [!code-vb[VbLINQVbFeatures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#4)]  
  
 자세한 내용은 [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)을 참조 하세요.  
  
## <a name="anonymous-types"></a>익명 형식  
 익명 형식은 속성 집합을 쿼리 결과에 포함 하려는 요소로 일시적으로 그룹화 하는 편리한 방법을 제공 합니다. 이렇게 하면 요소에 대 한 명명 된 데이터 형식을 정의 하지 않고 쿼리에서 사용 가능한 필드의 조합을 임의의 순서로 선택할 수 있습니다.  
  
 *익명 형식은* 컴파일러에 의해 동적으로 생성 됩니다. 형식 이름은 컴파일러에 의해 할당 되며, 각각의 새 컴파일에서 변경 될 수 있습니다. 따라서 이름을 직접 사용할 수 없습니다. 익명 형식은 다음과 같은 방식으로 초기화 됩니다.  
  
 [!code-vb[VbLINQVbFeatures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#5)]  
  
 자세한 내용은 [무명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하세요.  
  
## <a name="extension-methods"></a>확장 메서드  
 확장 메서드를 사용 하면 정의 외부에서 데이터 형식 또는 인터페이스에 메서드를 추가할 수 있습니다. 이 기능을 사용 하면 실제로 형식을 수정 하지 않고도 기존 형식에 새 메서드를 추가할 수 있습니다. 표준 쿼리 연산자는 <xref:System.Collections.Generic.IEnumerable%601>를 구현 하는 모든 형식에 대해 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 기능을 제공 하는 확장 메서드 집합입니다. <xref:System.Collections.Generic.IEnumerable%601>에 대 한 다른 확장에는 <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A>및 <xref:System.Linq.Enumerable.Intersect%2A>포함 됩니다.  
  
 다음 확장 메서드는 인쇄 메서드를 <xref:System.String> 클래스에 추가 합니다.  
  
 [!code-vb[VbLINQVbFeatures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#6)]  
  
 메서드는 <xref:System.String>의 일반 인스턴스 메서드와 같이 호출 됩니다.  
  
 [!code-vb[VbLINQVbFeatures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#7)]  
  
 자세한 내용은 [확장 메서드](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)를 참조하세요.  
  
## <a name="lambda-expressions"></a>람다 식  
 람다 식은 단일 값을 계산 하 고 반환 하는 이름이 없는 함수입니다. 명명 된 함수와 달리 람다 식을 동시에 정의 하 고 실행할 수 있습니다. 다음 예에서는 4를 표시 합니다.  
  
 [!code-vb[VbLINQVbFeatures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#8)]  
  
 람다 식 정의를 변수 이름에 할당 한 다음 이름을 사용 하 여 함수를 호출할 수 있습니다. 또한 다음 예제에서는 4를 표시 합니다.  
  
 [!code-vb[VbLINQVbFeatures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#12)]  
  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]에서 람다 식은 많은 표준 쿼리 연산자의 기반이 됩니다. 컴파일러는 `Where`, `Select`, `Order By`, `Take While`등의 기본 쿼리 메서드에 정의 된 계산을 캡처하기 위해 람다 식을 만듭니다.  
  
 예를 들어 다음 코드는 학생 목록에서 모든 선임 학생을 반환 하는 쿼리를 정의 합니다.  
  
 [!code-vb[VbLINQVbFeatures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#9)]  
  
 쿼리 정의는 `Where` 및 `Select`에 대 한 인수를 지정 하는 두 개의 람다 식을 사용 하는 다음 예제와 유사한 코드로 컴파일됩니다.  
  
 [!code-vb[VbLINQVbFeatures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#10)]  
  
 두 버전 모두 `For Each` 루프를 사용 하 여 실행할 수 있습니다.  
  
 [!code-vb[VbLINQVbFeatures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#11)]  
  
 자세한 내용은 [람다 식](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- [LINQ(Language-Integrated Query)(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
- [Visual Basic에서 LINQ 시작](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [LINQ 및 문자열 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
- [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
