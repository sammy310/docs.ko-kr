---
title: Stop 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Stop
helpviewer_keywords:
- breakpoints, Stop statements
- Stop statements [Visual Basic], syntax
- Stop statements [Visual Basic]
- execution [Visual Basic], suspending
- processing, interrupting
- processes, interrupting
- execution [Visual Basic], stopping
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
ms.openlocfilehash: 80d6734945324f3f517b256051486273f6b687ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783854"
---
# <a name="stop-statement-visual-basic"></a>Stop 문(Visual Basic)
실행을 일시 중단 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Stop  
```  
  
## <a name="remarks"></a>설명  
 배치할 수 있습니다 `Stop` 어디서 나 실행을 일시 중단 하는 절차에에서는 문입니다. 사용 하 여 `Stop` 문을 코드에 중단점을 설정 하는 것과 비슷합니다.  
  
 합니다 `Stop` 문을 달리 하지만 실행을 일시 중단 `End`, 파일을 모두 닫고 하거나 컴파일된 실행 파일 (.exe) 파일에 없는 경우 변수를 지우지 않습니다.  
  
> [!NOTE]
>  경우는 `Stop` 통합된 개발 환경 (IDE) 외부에서 실행 되는 코드에서 문이, 디버거가 호출 됩니다. 코드 디버그 또는 정식 버전 모드로 컴파일된 여부에 관계 없이 마찬가지입니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 합니다 `Stop` 각 반복에 대 한 실행을 일시 중단 하는 문을 `For...Next` 루프입니다.  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a>참고자료

- [End 문](../../../visual-basic/language-reference/statements/end-statement.md)
