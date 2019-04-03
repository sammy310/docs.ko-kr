---
title: 익명 형식(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousType
helpviewer_keywords:
- anonymous types [Visual Basic], about anonymous types
- anonymous types [Visual Basic]
- types [Visual Basic], anonymous
ms.assetid: 7b87532c-4b3e-4398-8503-6ea9d67574a4
ms.openlocfilehash: 3dc2083e5b4fd06250a1387c32f0eba28e879b30
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58829137"
---
# <a name="anonymous-types-visual-basic"></a>익명 형식(Visual Basic)
Visual Basic 데이터 형식에 대 한 클래스 정의 작성 하지 않고 개체를 만드는 데 사용할 수 있는 익명 형식을 지원 합니다. 대신 컴파일러가 클래스를 생성합니다. 클래스는 사용 가능한 이름이 없으므로에서 직접 상속 <xref:System.Object>, 개체를 선언할 때 지정 하는 속성을 포함 합니다. 데이터 형식의 이름을 지정 하지 않으면 때문 이라고 하는 *무명 형식*합니다.  
  
 다음 예제에서는 선언 하 고 변수를 만듭니다 `product` 두 속성이 있는 익명 형식의 인스턴스로 `Name` 고 `Price`입니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#1)]  
  
 A *쿼리 식* 쿼리에서 선택한 데이터 열을 결합 무명 형식을 사용 합니다. 특정 쿼리를 선택할 수 있는 열을 예측할 수 없으므로 형식의 결과 미리 정의할 수 없습니다. 익명 형식을 사용 순서에 관계 없이 임의 개수의 열을 선택 하는 쿼리를 작성할 수 있습니다. 컴파일러는 지정된 된 속성 및 지정된 된 순서 대로 일치 하는 데이터 형식을 만듭니다.  
  
 다음 예제에서는 `products` 많은 속성이 있으며 각 제품 개체의 목록입니다. 가변 `namePriceQuery` 실행 되 면 두 속성이 있는 익명 형식의 인스턴스 컬렉션을 반환 하는 쿼리 정의 보유 `Name` 고 `Price`입니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#2)]  
  
 가변 `nameQuantityQuery` 실행 되 면 두 속성이 있는 익명 형식의 인스턴스 컬렉션을 반환 하는 쿼리 정의 보유 `Name` 고 `OnHand`입니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#3)]  
  
 익명 형식에 대 한 컴파일러에서 만든 코드에 대 한 자세한 내용은 참조 하세요. [익명 형식 정의](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)합니다.  
  
> [!CAUTION]
>  익명 형식의 이름은 컴파일러에서 생성 되며 컴파일할 다를 수 있습니다. 코드 사용 하거나 프로젝트를 다시 컴파일할 때 이름이 변경 될 수 있으므로 무명 형식의 이름을 사용 해야 합니다.  
  
## <a name="declaring-an-anonymous-type"></a>익명 형식 선언  
 무명 형식의 인스턴스 선언 형식의 속성을 지정 하려면 이니셜라이저 목록을 사용 합니다. 익명 형식, 메서드 또는 이벤트와 같은 다른 클래스 요소가 없습니다 선언할 때만 속성을 지정할 수 있습니다. 다음 예에서 `product1` 두 속성이 있는 익명 형식의 인스턴스는: `Name` 고 `Price`입니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#4)]  
  
 키 속성으로 속성을 지정 하는 경우에 무명 형식을 두 인스턴스가 같은지를 비교 하려면 사용할 수 있습니다. 그러나 키 속성의 값을 변경할 수 없습니다. 자세한 내용은이 항목 뒷부분의 키 속성을 참조 하세요.  
  
 무명 형식의 인스턴스를 선언 하는 개체 이니셜라이저를 사용 하 여 명명 된 형식의 인스턴스를 선언 하는 알림:  
  
 [!code-vb[VbVbalrAnonymousTypes#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#5)]  
  
 무명 형식 속성을 지정 하는 다른 방법에 대 한 자세한 내용은 참조 하세요. [방법: 무명 형식 선언에서 속성 이름 및 형식 유추](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)합니다.  
  
## <a name="key-properties"></a>키 속성  
 키 속성 키가 아닌 속성에서 몇 가지 근본적인 방식은 다릅니다.  
  
-   두 인스턴스가 같은지 여부를 확인 하기 위해 키 속성의 값만 비교 됩니다.  
  
-   키 속성의 값을 읽기 전용 이며 변경할 수 없습니다.  
  
-   만 키 속성 값은 익명 형식에 대 한 컴파일러에서 생성 된 해시 코드 알고리즘에 포함 됩니다.  
  
### <a name="equality"></a>같음  
 무명 형식의 인스턴스는 동일한 익명 형식의 인스턴스인 경우에 같을 수 있습니다. 컴파일러는 다음 조건을 충족 하는 경우 두 인스턴스가 동일한 형식의 인스턴스로 처리:  
  
-   동일한 어셈블리에 선언 됩니다.  
  
-   해당 속성 이름과 동일한 유추 된 형식을 있고 동일한 순서로 선언 됩니다. 이름 비교는 대/소문자 구분 하지 않습니다.  
  
-   각각의 동일한 속성은 키 속성으로 표시 됩니다.  
  
-   각 선언에서 하나 이상의 속성이 키 속성이입니다.  
  
 키 속성이 없는 익명 형식의 인스턴스 자체에 같습니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#6)]  
  
 해당 키 속성의 값이 같으면 두 인스턴스가 동일한 익명 형식의 같습니다. 다음 예제에서는 같음 테스트 하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#7)]  
  
### <a name="read-only-values"></a>읽기 전용 값  
 키 속성의 값을 변경할 수 없습니다. 예를 들어 `prod8` 이전 예에서 합니다 `Name` 및 `Price` 필드는 `read-only`, 하지만 `OnHand` 변경할 수 있습니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#8)]  
  
## <a name="anonymous-types-from-query-expressions"></a>쿼리 식에서 무명 형식  
 쿼리 식에서는 무명 형식 만들 항상 필요 하지 않습니다. 가능한 경우 열 데이터를 저장할 기존 형식을 사용 합니다. 이 쿼리가 데이터 원본 또는 각 레코드의 필드 하나에에서 전체 레코드 중 하나를 반환할 때 발생 합니다. 다음 코드 예에서 `customers` 은 개체의 컬렉션을 `Customer` 클래스. 클래스에는 여러 속성이 및 순서에 관계 없이 쿼리 결과 하나 이상의 포함할 수 있습니다. 처음 두 예제에서는 익명 형식이 없습니다이 명명 된 형식의 요소를 선택 하는 쿼리 때문에 필요 합니다.  
  
-   `custs1` 때문에 문자열의 컬렉션을 포함 `cust.Name` 는 문자열입니다.  
  
     [!code-vb[VbVbalrAnonymousTypes#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#30)]  
  
-   `custs2` 컬렉션을 포함 `Customer` 때문에 개체의 각 요소 `customers` 는 `Customer` 개체 및 전체 요소는 쿼리에서 선택 합니다.  
  
     [!code-vb[VbVbalrAnonymousTypes#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#31)]  
  
 그러나 적절 한 명명 된 형식을 항상 사용 가능한 것은 아닙니다. 고객 이름 및 다른 경우, 고객 ID 번호와 다른 위치에 대 한 주소 및 고객 이름, 주소 및 세 번째 주문 기록을 선택 하려는 합니다. 익명 형식을 사용 첫 번째 결과를 보유할 새 명명 된 형식을 선언 하지 않고 순서에 관계 없이 속성의 조합을 선택할 수 있습니다. 대신 컴파일러는 각 컴파일 속성에 대 한 익명 형식을 만듭니다. 각 고객의 이름과 ID 번호를 선택 하는 다음 쿼리 `Customer` 개체의 `customers`합니다. 따라서 컴파일러는 이러한 두 속성만 포함 된 무명 형식을 만듭니다.  
  
 [!code-vb[VbVbalrAnonymousTYpes#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#32)]  
  
 이름과 무명 형식에서 속성의 데이터 형식 모두에 대 한 인수에서 가져온 `Select`, `cust.Name` 및 `cust.ID`합니다. 쿼리에서 만든 익명 형식에서 속성은 항상 키 속성입니다. 때 `custs3` 다음에서 실행 됩니다 `For Each` 루프, 결과 두 가지 주요 속성을 사용 하 여 무명 형식의 인스턴스 컬렉션 `Name` 고 `ID`입니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#33)]  
  
 표시 되는 컬렉션의 요소 `custs3` 강력한 형식의 사용 가능한 속성을 탐색 하 고 해당 형식을 확인할 IntelliSense를 사용할 수 있습니다.  
  
 자세한 내용은 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)합니다.  
  
## <a name="deciding-whether-to-use-anonymous-types"></a>익명 형식을 사용 하 여 여부 결정  
 익명 클래스의 인스턴스로 개체를 만들기 전에 가장 적합 한 옵션 인지 하는 것이 좋습니다. 예를 들어, 관련된 데이터를 포함 하도록 임시 개체를 만들려는 경우 완전 한 클래스가 포함 될 수 있는 메서드와 기타 필드에 대 한 필요가 없는 경우 무명 형식을 좋은 솔루션입니다. 익명 형식은 또한 편리한 각 선언에 대 한 속성의 다른 항목을 선택 하려는 경우 또는 속성의 순서를 변경 하려는 경우입니다. 그러나 프로젝트가 순서가 고정 된 동일한 속성에 있는 여러 개체를 포함 하는 경우 선언할 수 있습니다 이러한 쉽게 클래스 생성자를 사용 하 여 명명 된 형식을 사용 하 여. 예를 들어 적절 한 생성자를 사용 하 여 쉽습니다의 여러 인스턴스를 선언 하는 `Product` 무명 형식의 여러 인스턴스를 선언 하는 것 보다 클래스입니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#9)]  
  
 다른 명명 된 형식의 장점은 컴파일러 속성 이름의 실수로 잘못 입력을 catch 할 수 있습니다. 이전 예에서 `firstProd2`, `secondProd2`, 및 `thirdProd2` 동일한 익명 형식의 인스턴스 수입니다. 그러나 실수로 선언할 `thirdProd2` 다음 방법 중 하나에 해당 됩니다 다르다는 점을 `firstProd2` 및 `secondProd2`합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#10)]  
  
 무엇 보다도 명명 된 형식의 인스턴스에 적용 되지 않는 익명 형식의 사용에 제한이 있습니다. `firstProd2`를 `secondProd2`, 및 `thirdProd2` 동일한 익명 형식의 인스턴스입니다. 그러나 공유 익명 형식에 대 한 이름을 사용할 수 없게 되며 코드에서 형식 이름이 필요한 경우에 나타날 수 없습니다. 예를 들어, 변수, 필드 또는 모든 형식 선언을 다른 선언 하는 메서드 시그니처를 정의 하는 익명 형식을 사용할 수 없습니다. 결과적으로, 메서드 간에 정보를 공유 해야 하는 경우 익명 형식은 적합 하지 않습니다.  
  
## <a name="an-anonymous-type-definition"></a>익명 형식 정의  
 무명 형식의 인스턴스 선언에 대 한 응답, 컴파일러는 지정된 된 속성을 포함 하는 새 클래스 정을 만듭니다.  
  
 무명 형식은 하나 이상의 키 속성이 포함 된 경우 정의에서 상속 된 세 가지 멤버를 재정의 하는 <xref:System.Object>: <xref:System.Object.Equals%2A>하십시오 <xref:System.Object.GetHashCode%2A>, 및 <xref:System.Object.ToString%2A>합니다. 같음 테스트 및 해시 코드 값을 키 속성만 고려 결정에 대 한 코드 생성 합니다. 무명 형식은 키 속성이 없으면만 있으면 <xref:System.Object.ToString%2A> 재정의 됩니다. 익명 형식의 명시적으로 명명 된 속성은 이러한 생성 된 메서드와 충돌 하지 않습니다. 즉, 사용할 수 없습니다 `.Equals`, `.GetHashCode`, 또는 `.ToString` 속성 이름을 지정 합니다.  
  
 익명 형식 정의 하나 이상의 키 속성이 구현 합니다 <xref:System.IEquatable%601?displayProperty=nameWithType> 인터페이스를 여기서 `T` 무명 형식의 형식입니다.  
  
 재정의 된 메서드의 기능과 컴파일러에서 만든 코드에 대 한 자세한 내용은 참조 하세요. [익명 형식 정의](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [방법: 무명 형식 선언에서 속성 이름 및 형식 유추](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [익명 형식 정의](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [키](../../../../visual-basic/language-reference/modifiers/key.md)
