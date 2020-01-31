---
title: 예외 상호 운용성
ms.date: 01/16/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: 2aff71e97e1be0dbb584f4fe43c322cea86d2480
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794623"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a>비관리 코드에서 Interop 예외 작업

비관리 코드 예외 interop는 Windows 플랫폼 에서만 지원 됩니다. Windows 이외의 플랫폼에서 이식성 문제가 발생 합니다. Unix ABI에는 예외 처리에 대 한 정의가 없으므로 관리 코드는 예외 메커니즘이 내부적으로 작동 하는 방식을 알 수 없습니다. 따라서 예외가 발생 하 여 예기치 않은 동작이 발생할 수 있으며 충돌이 발생할 수 있습니다.

## <a name="setjmplongjmp-behaviors"></a>Setjmp/o Jmp 동작

`setjmp` 및 `longjmp` C 함수를 사용 하는 Interop는 지원 되지 않습니다. `longjmp`를 사용 하 여 관리 되는 프레임을 건너뛸 수 없습니다.

자세한 내용은 [entjmp 설명서](https://docs.microsoft.com/cpp/c-runtime-library/reference/longjmp)를 참조 하세요.

## <a name="see-also"></a>참조

- [예외](index.md)
- [네이티브 라이브러리와의 상호 운용성](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
