---
title: -highentropyva
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 9501ea46eb13baa171208e20d0c9645d118c4301
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408623"
---
# <a name="-highentropyva-visual-basic"></a>-highentropyva(Visual Basic)
[-platform:anycpu](platform.md) 컴파일러 옵션으로 표시된 실행 파일 또는 64비트 실행 파일이 높은 엔트로피의 ASLR(주소 공간 레이아웃 불규칙화)을 지원하는지 여부를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>인수  
 `+` &#124; `-`  
 선택 사항입니다. 이 옵션은 기본적으로 또는 `-highentropyva-`를 지정하는 경우 off입니다. `-highentropyva` 또는 `-highentropyva+`를 지정하는 경우에는 이 옵션이 on입니다.  
  
## <a name="remarks"></a>설명  
 이 옵션을 지정할 경우 Windows 커널의 호환되는 버전이 ASLR의 일부로 프로세스의 주소 공간 레이아웃을 임의로 선택할 때 보다 높은 수준의 엔트로피를 사용할 수 있습니다. 커널이 더 높은 수준의 엔트로피를 사용하면 스택 및 힙과 같은 메모리 영역에 더 많은 주소를 할당할 수 있습니다. 따라서 특정 메모리 영역의 위치를 추측하기 어려워집니다.  
  
 이 옵션이 on이면 대상 실행 파일과 이 실행 파일이 종속된 모든 모듈이 64비트 프로세스로 실행될 때 4GB보다 큰 포인터 값을 처리할 수 있어야 합니다.  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
