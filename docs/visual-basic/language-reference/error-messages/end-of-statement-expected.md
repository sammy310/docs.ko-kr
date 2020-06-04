---
title: 문의 끝이 필요합니다.
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: 169f01b02df377ba6cc21ffad53c36f5d4537140
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409649"
---
# <a name="end-of-statement-expected"></a>문의 끝이 필요합니다.
구문이 완전 하지만 문이 완료 된 요소 다음에 추가 프로그래밍 요소가 추가 됩니다. 줄 종결자는 모든 문 끝에 필요 합니다.
  
 줄 종결자는 Visual Basic 소스 파일의 문자를 줄로 나눕니다. 줄 종결자의 예로는 유니코드 캐리지 리턴 문자 (&HD), 유니코드 줄 바꿈 문자 (&HA), 유니코드 캐리지 리턴 문자, 유니코드 줄 바꿈 문자가 차례로 나옵니다. 줄 종결자에 대 한 자세한 내용은 [Visual Basic 언어 사양](~/_vblang/spec/lexical-grammar.md#line-terminators)을 참조 하세요.
  
 **오류 ID:** BC30205
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면
  
1. 서로 다른 두 문이 실수로 같은 줄에 배치 되었는지 확인 하십시오.
  
2. 문을 완료 하는 요소 뒤에 줄 종결자를 삽입 합니다.
  
## <a name="see-also"></a>참고 항목

- [방법: 코드에서 명령문 분리 및 결합](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [문](../../programming-guide/language-features/statements.md)
