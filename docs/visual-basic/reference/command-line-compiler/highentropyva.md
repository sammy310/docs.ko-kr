---
title: -highentropyva (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 16bfea37a5742ac5aaaabfacdcf03a2b5bedb6db
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819283"
---
# <a name="-highentropyva-visual-basic"></a>-highentropyva (Visual Basic)
나타냅니다 64 비트 실행 파일을 또는으로 표시 되는 실행 파일을 [/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) 컴파일러 옵션은 높은 엔트로피 주소 공간 레이아웃 불규칙화 (ASLR)를 지원 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>인수  
 `+` &#124; `-`  
 선택 사항입니다. 옵션은 기본적으로 꺼져 있거나 지정할 경우 `-highentropyva-`합니다. 옵션을 지정 하는 경우에 `-highentropyva` 또는 `-highentropyva+`합니다.  
  
## <a name="remarks"></a>설명  
 이 옵션을 지정 하는 경우에 Windows 커널의 호환 되는 버전 커널 ASLR의 일부로 프로세스의 주소 공간 레이아웃을 소프트웨어 때 높은 수준의 엔트로피에 사용할 수 있습니다. 높은 수준의 엔트로피를 사용 하는 커널 스택 및 힙과 같은 메모리 영역에 더 많은 주소를 할당할 수 있습니다. 따라서 특정 메모리 영역의 위치를 추측하기 어려워집니다.  
  
 옵션에는 대상 실행 파일 및 모든 모듈에서 설정 되는 해당 모듈을 64 비트 프로세스로 실행 하는 경우 4 gb (기가바이트) 보다 큰 포인터 값 처리할 수 있어야 합니다.  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
