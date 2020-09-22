---
title: Select 절
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySelect
helpviewer_keywords:
- Select statement [Visual Basic]
- Select clause [Visual Basic]
- queries [Visual Basic], Select
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
ms.openlocfilehash: d96423efbee075a7ad257df72471c71e38e09b63
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875749"
---
# <a name="select-clause-visual-basic"></a>Select 절 (Visual Basic)

쿼리 결과를 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a>부분  

 `var1`  
 선택 사항입니다. 열 식의 결과를 참조 하는 데 사용할 수 있는 별칭입니다.  
  
 `fieldName1`  
 필수 사항입니다. 쿼리 결과에 반환할 필드의 이름입니다.  
  
## <a name="remarks"></a>설명  

 절을 사용 `Select` 하 여 쿼리에서 반환 되는 결과를 정의할 수 있습니다. 이렇게 하면 쿼리로 생성 된 새 익명 형식의 멤버를 정의 하거나 쿼리에서 반환 되는 명명 된 형식의 멤버를 대상으로 지정할 수 있습니다. `Select`쿼리에는 절이 필요 하지 않습니다. 절을 `Select` 지정 하지 않으면 쿼리는 현재 범위에 대해 식별 된 범위 변수의 모든 멤버를 기반으로 하는 형식을 반환 합니다. 자세한 내용은 [무명 형식](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하세요. 쿼리에서 명명 된 형식을 만들면 형식의 결과가 반환 됩니다 <xref:System.Collections.Generic.IEnumerable%601> `T` . 여기서는 생성 된 형식입니다.  
  
 `Select`절은 현재 범위에 있는 모든 변수를 참조할 수 있습니다. 여기에는 절 또는 절에서 식별 된 범위 변수가 포함 됩니다 `From` `From` . 또한,, 또는 절을 사용 하 여 별칭으로 만든 새 변수 `Aggregate` `Let` `Group By` `Group Join` 또는 `Select` 쿼리 식에 있는 이전 절의 변수를 포함 합니다. 절에는 `Select` 정적 값이 포함 될 수도 있습니다. 예를 들어 다음 코드 예제에서는 `Select` 절이 쿼리 결과를 4 개의 멤버 `ProductName` ,, `Price` `Discount` 및로 정의 하는 새 무명 형식으로 정의 하는 쿼리 식을 보여 `DiscountedPrice` 줍니다. `ProductName`및 `Price` 멤버 값은 절에 정의 된 product range 변수에서 가져옵니다 `From` . `DiscountedPrice`멤버 값은 절에서 계산 됩니다 `Let` . `Discount`멤버가 정적 값입니다.  
  
 [!code-vb[VbSimpleQuerySamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#27)]  
  
 `Select`절은 후속 쿼리 절에 대해 새로운 범위 변수 집합을 도입 하 고 이전 범위 변수는 더 이상 범위에 있지 않습니다. `Select`쿼리 식의 마지막 절은 쿼리의 반환 값을 결정 합니다. 예를 들어 다음 쿼리는 합계가 500를 초과 하는 모든 고객 주문에 대 한 회사 이름 및 주문 ID를 반환 합니다. 첫 번째 `Select` 절은 `Where` 절과 두 번째 절에 대 한 범위 변수를 식별 합니다 `Select` . 두 번째 `Select` 절은 쿼리에서 반환 되는 값을 새 익명 형식으로 식별 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#28)]  
  
 절이 `Select` 반환할 단일 항목을 식별 하는 경우 쿼리 식은 해당 단일 항목 형식의 컬렉션을 반환 합니다. 절이 `Select` 반환할 여러 항목을 식별 하는 경우 쿼리 식은 선택한 항목을 기반으로 새 익명 형식의 컬렉션을 반환 합니다. 예를 들어 다음 두 쿼리는 절을 기반으로 서로 다른 두 형식의 컬렉션을 반환 합니다 `Select` . 첫 번째 쿼리는 회사 이름 컬렉션을 문자열로 반환 합니다. 두 번째 쿼리는 `Customer` 회사 이름 및 주소 정보로 채워진 개체의 컬렉션을 반환 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#29)]  
  
## <a name="example"></a>예제  

 다음 쿼리 식에서는 절을 사용 하 여 `From` `cust` 컬렉션에 대 한 범위 변수를 선언 합니다 `customers` . `Select`절은 고객 이름 및 ID 값을 선택 하 고 `CompanyName` `CustomerID` 새 범위 변수의 및 열을 채웁니다. `For Each`문은 반환 된 각 개체를 반복 하 고 `CompanyName` `CustomerID` 각 레코드의 및 열을 표시 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#30)]  
  
## <a name="see-also"></a>참조

- [Visual Basic의 LINQ 소개](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [쿼리](index.md)
- [From 절](from-clause.md)
- [Where 절](where-clause.md)
- [Order By 절](order-by-clause.md)
- [익명 형식](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
