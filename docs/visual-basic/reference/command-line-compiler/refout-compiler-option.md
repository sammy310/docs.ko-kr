---
title: -refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: c11d83ff37da41faa3dc6b66a87e2c52c5f6c7ac
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582868"
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

참조 어셈블리는 메타 데이터를 포함 하지만 구현 코드는 포함 하지 않는 메타 데이터 전용 어셈블리입니다. 익명 형식을 제외한 모든 항목에 대 한 형식 및 멤버 정보를 포함 합니다. 해당 메서드 본문은 단일 `throw null` 문으로 바뀝니다. 본문이 아닌 `throw null` 메서드 본문을 사용 하는 이유는 PEVerify를 실행 하 고 통과 하 여 메타 데이터의 완전성을 확인할 수 있도록 하는 것입니다.

참조 어셈블리에는 어셈블리 수준 [Referenceassembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) 특성이 포함 됩니다. 이 특성을 소스에서 지정할 수 있습니다. 이렇게 하면 컴파일러가 특성을 합성할 필요가 없습니다. 이 특성으로 인해 런타임은 실행을 위해 참조 어셈블리를 로드 하는 것을 거부 하지만 여전히 리플렉션 전용 컨텍스트에서 로드 될 수 있습니다. 어셈블리를 반영 하는 도구는 참조 어셈블리를 리플렉션 전용으로 로드 하도록 해야 합니다. 그렇지 않으면 런타임에서 <xref:System.BadImageFormatException>을 throw 합니다.

`-refout` 및 [`-refonly`](refonly-compiler-option.md) 옵션은 함께 사용할 수 없습니다.

## <a name="see-also"></a>참조

- [/refonly](refonly-compiler-option.md)
- [Visual Basic 명령줄 컴파일러](index.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
