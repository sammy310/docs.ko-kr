---
title: 메서드(multiline lambda) 내에서 명령문을 사용할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: f3c43d640259d5e1af545e2610088aab5d70453d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396248"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a>메서드 내부에는 문을 사용할 수 없습니다./multiline lambda
`Sub`, `Function` , 속성 `Get` 또는 속성 프로시저 내에서 문을 사용할 수 없습니다 `Set` . 일부 문은 모듈 또는 클래스 수준에 배치할 수 있습니다. 등의 다른 항목은 `Option Strict` 네임 스페이스 수준에 있어야 하 고 다른 모든 선언 앞에와 야 합니다.  
  
 **오류 ID:** BC30024  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 프로시저에서 문을 제거 합니다.  
  
## <a name="see-also"></a>참고 항목

- [Sub 문](../statements/sub-statement.md)
- [Function 문](../statements/function-statement.md)
- [Get 문](../statements/get-statement.md)
- [Set 문](../statements/set-statement.md)
