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
ms.openlocfilehash: e9382ee34842fc3a3b4b23f71848bda602c99780
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583215"
---
# <a name="stop-statement-visual-basic"></a>Stop 문(Visual Basic)
실행을 일시 중단 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Stop  
```  
  
## <a name="remarks"></a>주의  
 프로시저의 아무 곳에 나 `Stop` 문을 추가 하 여 실행을 일시 중단할 수 있습니다. @No__t_0 문을 사용 하는 것은 코드에서 중단점을 설정 하는 것과 비슷합니다.  
  
 @No__t_0 문은 실행을 일시 중단 하지만 `End`와는 달리 컴파일된 실행 파일 (.exe)에서 발생 한 경우를 제외 하 고는 파일을 닫지 않거나 모든 변수를 지웁니다.  
  
> [!NOTE]
> IDE (통합 개발 환경) 외부에서 실행 되는 코드에 `Stop` 문이 있으면 디버거가 호출 됩니다. 이는 코드가 디버그 모드에서 컴파일 되었는지 아니면 소매 모드에서 컴파일 되었는지에 관계 없이 적용 됩니다.  
  
## <a name="example"></a>예제  
 이 예에서는 `Stop` 문을 사용 하 여 `For...Next` 루프를 통해 각 반복에 대 한 실행을 일시 중단 합니다.  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a>참조

- [End 문](../../../visual-basic/language-reference/statements/end-statement.md)
