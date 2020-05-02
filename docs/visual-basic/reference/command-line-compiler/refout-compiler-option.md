---
title: -refout
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: 3649a24a52cc6a448ea7cf4d850915adf02147fb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348651"
---
# <a name="-refout-visual-basic"></a>-refout(Visual Basic)

**-refout** 옵션은 참조 어셈블리가 출력되어야 하는 파일 경로를 지정합니다.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>구문

```console
-refout:filepath
```

## <a name="arguments"></a>인수

`filepath`  
참조 어셈블리의 경로 및 파일 이름입니다. 일반적으로 기본 어셈블리의 하위 폴더에 있어야 합니다. 권장되는 규칙(MSBuild에서 사용됨)은 주 어셈블리에 상대적으로 “ref/” sub-폴더에 참조 어셈블리를 배치하는 것입니다. `filepath`의 모든 폴더가 존재해야 합니다. 컴파일러는 폴더를 생성하지 않습니다.

## <a name="remarks"></a>설명

Visual Basic은 버전 15.3부터 `-refout` 스위치를 지원합니다.

참조 어셈블리는 라이브러리의 퍼블릭 API 표면을 나타내는 데 필요한 최소한의 메타데이터만 포함하는 특수한 형식의 어셈블리입니다. 빌드 도구에서 어셈블리를 참조할 때 중요한 모든 멤버에 대한 선언을 포함하지만, 해당 API 계약에 영향을 미치지 않는 프라이빗 멤버의 선언과 모든 멤버 구현은 제외됩니다. 자세한 내용은 .NET 가이드에서 [참조 어셈블리](../../../standard/assembly/reference-assemblies.md)를 참조하세요.

`-refout` 및 [`-refonly`](refonly-compiler-option.md) 옵션은 함께 사용할 수 없습니다.

## <a name="see-also"></a>참조

- [/refonly](refonly-compiler-option.md)
- [Visual Basic 명령줄 컴파일러](index.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
