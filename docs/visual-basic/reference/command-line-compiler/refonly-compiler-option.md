---
title: -refonly
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: b906178abf8d159083d95e41448596d512e857de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348569"
---
# <a name="-refonly-visual-basic"></a>-refonly (Visual Basic)

**-Refonly** 옵션은 컴파일의 기본 출력이 구현 어셈블리 대신 참조 어셈블리 여야 함을 나타냅니다. `-refonly` 매개 변수는 참조 어셈블리가 실행될 수 없을 때 PDB 출력을 자동으로 사용하지 않도록 설정합니다.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>구문

```console
-refonly
```

## <a name="remarks"></a>설명

Visual Basic 버전 15.3부터 `-refonly` 스위치를 지원 합니다.

참조 어셈블리는 라이브러리의 퍼블릭 API 표면을 나타내는 데 필요한 최소한의 메타데이터만 포함하는 특수한 형식의 어셈블리입니다. 빌드 도구에서 어셈블리를 참조할 때 중요한 모든 멤버에 대한 선언을 포함하지만, 해당 API 계약에 영향을 미치지 않는 프라이빗 멤버의 선언과 모든 멤버 구현은 제외됩니다. 자세한 내용은 .NET 가이드에서 [참조 어셈블리](../../../standard/assembly/reference-assemblies.md)를 참조하세요.

`-refonly` 및 [`-refout`](refout-compiler-option.md) 옵션은 함께 사용할 수 없습니다.

## <a name="see-also"></a>참고자료

- [/refout](refout-compiler-option.md)
- [Visual Basic 명령줄 컴파일러](index.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
