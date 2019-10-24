---
title: -refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: 552e611f222bfcc3ce12520ecdb891fd7b8b21de
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775556"
---
# <a name="-refout-visual-basic"></a>-refout (Visual Basic)

**-refout** 옵션은 참조 어셈블리가 출력되어야 하는 파일 경로를 지정합니다.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>구문

```console
-refout:filepath
```

## <a name="arguments"></a>인수

`filepath`  
참조 어셈블리의 경로 및 파일 이름입니다. 일반적으로 주 어셈블리의 하위 폴더에 있어야 합니다. 권장되는 규칙(MSBuild에서 사용됨)은 주 어셈블리에 상대적으로 “ref/” sub-폴더에 참조 어셈블리를 배치하는 것입니다. @No__t_0의 모든 폴더가 존재 해야 합니다. 컴파일러는 생성 하지 않습니다.

## <a name="remarks"></a>주의

Visual Basic 버전 15.3부터 `-refout` 스위치를 지원 합니다.

참조 어셈블리는 라이브러리의 공용 API 화면을 나타내는 데 필요한 최소한의 메타 데이터만 포함 하는 특수 한 형식의 어셈블리입니다. 여기에는 빌드 도구에서 어셈블리를 참조할 때 중요 한 모든 멤버에 대 한 선언이 포함 되지만, 해당 API 계약에 대 한 관찰 효과가 없는 전용 멤버의 모든 멤버 구현 및 선언은 제외 됩니다. 자세한 내용은 .NET의 [참조 어셈블리](../../../standard/assembly/reference-assemblies.md) 가이드를 참조 하세요.

`-refout` 및 [`-refonly`](refonly-compiler-option.md) 옵션은 함께 사용할 수 없습니다.

## <a name="see-also"></a>참조

- [/refonly](refonly-compiler-option.md)
- [Visual Basic 명령줄 컴파일러](index.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
