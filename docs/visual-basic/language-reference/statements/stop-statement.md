---
title: Stop 문
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
ms.openlocfilehash: c9226ccaea9a0709a9d6a49900f69cb9ac9e1dbe
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871747"
---
# <a name="stop-statement-visual-basic"></a>Stop 문(Visual Basic)

실행을 일시 중단 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Stop  
```  
  
## <a name="remarks"></a>설명  

 `Stop`프로시저에 문을 추가 하 여 실행을 일시 중단할 수 있습니다. 문을 사용 하는 `Stop` 것은 코드에서 중단점을 설정 하는 것과 비슷합니다.  
  
 `Stop`문은 실행을 일시 중단 하지만,와는 달리 `End` 컴파일된 실행 파일 (.exe)에서 발생 한 경우를 제외 하 고는 파일을 닫지 않거나 모든 변수를 지우지 않습니다.  
  
> [!NOTE]
> `Stop`IDE (통합 개발 환경) 외부에서 실행 되는 코드에 문이 있으면 디버거가 호출 됩니다. 이는 코드가 디버그 모드에서 컴파일 되었는지 아니면 소매 모드에서 컴파일 되었는지에 관계 없이 적용 됩니다.  
  
## <a name="example"></a>예제  

 이 예제에서는 문을 사용 하 여 `Stop` 루프를 통해 반복할 때마다 실행을 일시 중단 `For...Next` 합니다.  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a>참조

- [End 문](end-statement.md)
