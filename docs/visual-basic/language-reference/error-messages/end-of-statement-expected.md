---
description: '다음에 대해 자세히 알아보세요. BC30205: 문의 끝이 필요 합니다.'
title: 문의 끝이 필요합니다.
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: a3f309a4674f6de34c0be8abfef31e293a10dec5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796550"
---
# <a name="bc30205-end-of-statement-expected"></a>BC30205: 문의 끝이 필요 합니다.

구문이 완전 하지만 문이 완료 된 요소 다음에 추가 프로그래밍 요소가 추가 됩니다. 줄 종결자는 모든 문 끝에 필요 합니다.

 줄 종결자는 Visual Basic 소스 파일의 문자를 줄로 나눕니다. 줄 종결자의 예로는 유니코드 캐리지 리턴 문자 (&HD), 유니코드 줄 바꿈 문자 (&HA), 유니코드 캐리지 리턴 문자, 유니코드 줄 바꿈 문자가 차례로 나옵니다. 줄 종결자에 대 한 자세한 내용은 [Visual Basic 언어 사양](~/_vblang/spec/lexical-grammar.md#line-terminators)을 참조 하세요.

 **오류 ID:** BC30205

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 서로 다른 두 문이 실수로 같은 줄에 배치 되었는지 확인 하십시오.

2. 문을 완료 하는 요소 뒤에 줄 종결자를 삽입 합니다.

## <a name="see-also"></a>참고 항목

- [방법: 코드에서 명령문 분리 및 결합](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [문](../../programming-guide/language-features/statements.md)
