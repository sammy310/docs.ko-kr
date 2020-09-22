---
title: 서수가 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 64f56b2ecace0ceafb310a175ea605e6959b7256
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871387"
---
# <a name="ordinal-is-not-valid"></a>서수가 잘못되었습니다.

구문을 사용 하 여 프로시저 이름 대신 숫자를 사용 하는 것으로 표시 된 DLL (동적 연결 라이브러리)에 대 한 호출 `#num` 입니다. 이 오류는 다음과 같은 경우에 발생할 수 있습니다.  
  
- `#num`식을 서 수로 변환 하지 못했습니다.  
  
- `#num`지정 된가 DLL에서 함수를 지정 하지 않는 경우  
  
- 형식 라이브러리의 선언이 잘못 되어 잘못 된 서 수를 내부적으로 사용 합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 식이 유효한 숫자를 나타내는지 확인 하거나 이름을 기준으로 프로시저를 호출 합니다.  
  
2. `#num`DLL에서 올바른 함수를 식별 하는지 확인 합니다.  
  
3. 코드를 주석으로 처리 하 여 문제를 일으킨 프로시저 호출을 분리 합니다. `Declare`프로시저에 대 한 문을 작성 하 고 형식 라이브러리 공급 업체에 문제를 보고 합니다.  
  
## <a name="see-also"></a>참조

- [Declare 문](../statements/declare-statement.md)
