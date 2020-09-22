---
title: 오류 없이 계속됩니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 6dd6805151de52a5e0cf51c520485c0e8558e0a7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870833"
---
# <a name="resume-without-error"></a>오류 없이 계속됩니다.

`Resume`문이 오류 처리 코드 외부에 표시 되었거나 오류가 없는 경우에도 코드를 오류 처리기로 건너뛰었습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. `Resume`문을 오류 처리기로 이동 하거나 삭제 합니다.  
  
2. 여러 프로시저에서 레이블로의 점프를 수행할 수 없으므로 오류 처리기를 식별 하는 레이블에 대해 프로시저를 검색 합니다. 문이 아닌 문의 대상으로 지정 된 중복 된 레이블을 찾은 경우 `GoTo` `On Error GoTo` 해당 대상에 동의 하도록 줄 레이블을 변경 합니다.  
  
## <a name="see-also"></a>참조

- [Resume 문](../statements/resume-statement.md)
- [On Error 문](../statements/on-error-statement.md)
