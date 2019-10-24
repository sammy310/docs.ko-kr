---
title: -refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: 8e64989ac1410b51991027ffcb33e8dae0c0284b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775561"
---
# <a name="-refonly-visual-basic"></a>-refonly (Visual Basic)

**-Refonly** 옵션은 컴파일의 기본 출력이 구현 어셈블리 대신 참조 어셈블리 여야 함을 나타냅니다. `-refonly` 매개 변수는 참조 어셈블리가 실행될 수 없을 때 PDB 출력을 자동으로 사용하지 않도록 설정합니다.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>구문

```console
-refonly
```

## <a name="remarks"></a>주의

Visual Basic 버전 15.3부터 `-refonly` 스위치를 지원 합니다.

참조 어셈블리는 라이브러리의 공용 API 화면을 나타내는 데 필요한 최소한의 메타 데이터만 포함 하는 특수 한 형식의 어셈블리입니다. 여기에는 빌드 도구에서 어셈블리를 참조할 때 중요 한 모든 멤버에 대 한 선언이 포함 되지만, 해당 API 계약에 대 한 관찰 효과가 없는 전용 멤버의 모든 멤버 구현 및 선언은 제외 됩니다. 자세한 내용은 .NET의 [참조 어셈블리](../../../standard/assembly/reference-assemblies.md) 가이드를 참조 하세요.

`-refonly` 및 [`-refout`](refout-compiler-option.md) 옵션은 함께 사용할 수 없습니다.

## <a name="see-also"></a>참조

- [/refout](refout-compiler-option.md)
- [Visual Basic 명령줄 컴파일러](index.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
