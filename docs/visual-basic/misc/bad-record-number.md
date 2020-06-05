---
title: 레코드 개수가 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: 44a11d95d33041de9d637684f41cb003dcc36b97
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84367544"
---
# <a name="bad-record-number"></a>레코드 개수가 잘못되었습니다.
`a FileGet`, `FilePut`, `FileGetObject`또는 `FilePutObject` 문의 레코드 번호가 0보다 작거나 같습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 레코드 번호를 생성하는 데 사용한 계산을 확인합니다. 레코드 번호를 계산하는 데 사용한 변수 또는 레코드 번호가 포함된 변수의 철자를 확인합니다. 모듈에서 `Option Explicit On` 을 사용하지 않으면 철자가 잘못된 변수 이름이 암시적으로 선언되고 0으로 초기화됩니다.  
  
## <a name="see-also"></a>참고 항목

- [Option Explicit 문](../language-reference/statements/option-explicit-statement.md)
