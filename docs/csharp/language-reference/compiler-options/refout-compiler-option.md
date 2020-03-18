---
title: -refout(C# 컴파일러 옵션)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: f48316a1e6f657e3bd0190d269dfe0e875a833d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "72771753"
---
# <a name="-refout-c-compiler-options"></a>-refout(C# 컴파일러 옵션)

**-refout** 옵션은 참조 어셈블리가 출력되어야 하는 파일 경로를 지정합니다. 이것은 Emit API에서 `metadataPeStream`으로 전환됩니다. 이 옵션은 MSBuild의 [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) 프로젝트 속성에 해당합니다.

## <a name="syntax"></a>구문

```console
-refout:filepath
```

## <a name="arguments"></a>인수

 `filepath` 참조 어셈블리의 파일 경로입니다. 일반적으로 주 어셈블리의 경로와 일치해야 합니다. 권장되는 규칙(MSBuild에서 사용됨)은 주 어셈블리에 상대적으로 “ref/” sub-폴더에 참조 어셈블리를 배치하는 것입니다.

## <a name="remarks"></a>설명

참조 어셈블리는 라이브러리의 퍼블릭 API 표면을 나타내는 데 필요한 최소한의 메타데이터만 포함하는 특수한 형식의 어셈블리입니다. 빌드 도구에서 어셈블리를 참조할 때 중요한 모든 멤버에 대한 선언을 포함하지만, 해당 API 계약에 영향을 미치지 않는 프라이빗 멤버의 선언과 모든 멤버 구현은 제외됩니다. 자세한 내용은 .NET 가이드에서 [참조 어셈블리](../../../standard/assembly/reference-assemblies.md)를 참조하세요.

`-refout` 및 [`-refonly`](refonly-compiler-option.md) 옵션은 함께 사용할 수 없습니다.

## <a name="see-also"></a>참고 항목

- [C# 컴파일러 옵션](./index.md)
- [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)
