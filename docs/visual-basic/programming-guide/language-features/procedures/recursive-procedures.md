---
title: 재귀 프로시저(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
ms.openlocfilehash: de9a2af9fc3cd78879b6525245727a6f52d51c63
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832387"
---
# <a name="recursive-procedures-visual-basic"></a>재귀 프로시저(Visual Basic)
A *재귀* 절차는 자신을 호출 하는 것입니다. 일반적으로이 Visual Basic 코드를 작성 하는 가장 효과적인 방법은 없습니다.  
  
 다음 절차는 재귀를 사용 하 여 원래 인수로의 계승을 계산 합니다.  
  
 [!code-vb[VbVbcnProcedures#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#51)]  
  
## <a name="considerations-with-recursive-procedures"></a>재귀 프로시저를 사용 하 여 고려 사항  
 **제한 조건**합니다. 재귀를 종료할 수 있는 하나 이상의 조건에 대해 테스트 하는 재귀 프로시저를 디자인 해야 하 고 적절 한 수의 재귀 호출 내에서 이러한 조건이 충족 되는 있는 경우도 처리 해야 합니다. 오류 없이 충족 될 수 있는 하나 이상의 조건 없이 프로시저 무한 루프로 실행 하는 위험 수준이 높은 실행 합니다.  
  
 **메모리 사용량**. 응용 프로그램에 제한 된 지역 변수의 공간. 프로시저가 자신을 호출할 때마다 사용 공간에 많은 지역 변수의 복사본을 더 합니다. 결과적으로 인해이 프로세스는 무기한 계속 되 면을 <xref:System.StackOverflowException> 오류입니다.  
  
 **효율성**- 거의 항상 재귀 루프를 대체할 수 있습니다. 루프는 전달 인수를 추가 저장소를 초기화 하 고 값을 반환 하는 오버 헤드는 없습니다. 성능 재귀 호출 없이 훨씬 더 나은 수 있습니다.  
  
 **상호 재귀**합니다. 서로 다른 두 프로시저 호출 하는 경우 성능이 매우 저하 또는 무한 루프도 알 수 있습니다. 이러한 설계는 단일 재귀 프로시저와 같은 문제를 표시 하지만 발견 하 여 디버깅 하기가 더 어렵습니다.  
  
 **괄호를 사용 하 여 호출**합니다. 경우는 `Function` 프로시저가 자신을 재귀적으로 호출, 인수 목록이 없는 경우에 프로시저 이름 뒤에 괄호를 따라야 합니다. 함수 이름이 사용 중이 고, 그렇지 함수의 반환 값을 나타내는 것으로 합니다.  
  
 **테스트**합니다. 재귀 프로시저를 작성 하는 경우 일부 제한 조건이 항상 충족 하는지 확인 하려면 매우 신중 하 게 테스트 해야 있습니다. 또한 재귀 호출이 너무 많아서 인해 메모리에서 실행할 수 없음을 확인 해야 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.StackOverflowException>
- [절차](./index.md)
- [Sub 프로시저](./sub-procedures.md)
- [Function 프로시저](./function-procedures.md)
- [속성 프로시저](./property-procedures.md)
- [연산자 프로시저](./operator-procedures.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [프로시저 오버로딩](./procedure-overloading.md)
- [프로시저 문제 해결](./troubleshooting-procedures.md)
- [루프 구조](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
