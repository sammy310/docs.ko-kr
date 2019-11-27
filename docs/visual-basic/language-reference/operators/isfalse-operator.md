---
title: IsFalse 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 51b7bfb2cf5301a39818e6566b408ee0677689f2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349525"
---
# <a name="isfalse-operator-visual-basic"></a>IsFalse 연산자(Visual Basic)
식이 `False`되는지 여부를 확인 합니다.  
  
 `IsFalse`는 코드에서 명시적으로 호출할 수 없지만 Visual Basic 컴파일러는이를 사용 하 여 `AndAlso` 절에서 코드를 생성할 수 있습니다. 클래스 또는 구조체를 정의 하 고 `AndAlso` 절에서 해당 형식의 변수를 사용 하는 경우 해당 클래스 또는 구조체에서 `IsFalse`를 정의 해야 합니다.  
  
 컴파일러는 `IsFalse` 및 `IsTrue` 연산자를 일치 하는 *쌍*으로 간주 합니다. 즉, 이러한 항목 중 하나를 정의 하는 경우 다른 항목을 정의 해야 합니다.  
  
> [!NOTE]
> `IsFalse` 연산자는 *오버 로드*될 수 있습니다. 즉, 클래스 또는 구조체의 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 재정의할 수 있습니다. 코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `IsFalse` 및 `IsTrue` 연산자에 대 한 정의를 포함 하는 구조체의 개요를 정의 합니다.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>참고 항목

- [IsTrue 연산자](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [방법: 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [AndAlso 연산자](../../../visual-basic/language-reference/operators/andalso-operator.md)
