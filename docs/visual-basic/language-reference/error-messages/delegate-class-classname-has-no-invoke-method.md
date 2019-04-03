---
title: "'<classname>' 대리자 클래스에는 Invoke 메서드가 없으므로 이러한 형식의 식은 프로시저 호출의 대상일 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 463b4f50e8c431bbbc113509e5fd9dd1756b5928
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822520"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>대리자 클래스\<응용 프로그램 이름 >'에 Invoke 메서드가 하므로이 형식의 식은 메서드 호출의 대상일 수 없습니다
에 대 한 호출 `Invoke` 때문에 실패 했습니다 대리자를 통해 `Invoke` 대리자 클래스에서 구현 되지 않았습니다.  
  
 **오류 ID:** BC30220  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  대리자 클래스의 인스턴스를 사용 하 여 만들어졌는지 확인 한 `Dim` 문과 프로시저를 사용 하 여 대리자 인스턴스를 할당할지를 `AddressOf` 연산자.  
  
2.  대리자 클래스를 구현 하는 코드를 찾아를 구현 합니다는 `Invoke` 프로시저입니다.  
  
## <a name="see-also"></a>참고자료

- [대리자](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [AddressOf 연산자](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)
