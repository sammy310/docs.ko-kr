---
description: '#nullable - C# 참조'
title: '#nullable - C# 참조'
ms.date: 11/18/2020
f1_keywords:
- '#nullable'
helpviewer_keywords:
- '#nullable directive [C#]'
ms.openlocfilehash: 4c114a09f29769fcc824bcdabdc1d523e33f199d
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099450"
---
# <a name="nullable-c-reference"></a>#nullable(C# 참조)

`#nullable` 전처리기 지시문은 ‘null 허용 주석 컨텍스트’ 및 ‘null 허용 경고 컨텍스트’를 설정합니다.  이 지시문은 null 허용 주석이 적용되는지와 null 허용 여부 경고가 지정되는지를 제어합니다. 각 컨텍스트는 *disabled* 또는 *enabled* 입니다.

두 컨텍스트 모두 프로젝트 수준(C# 소스 코드 외부)에서 지정할 수 있습니다. `#nullable` 지시문은 주석 및 경고 컨텍스트를 제어하고 프로젝트 수준 설정보다 우선으로 적용됩니다. 지시문은 다른 지시문이 재정의할 때까지 제어하는 컨텍스트를 설정하거나 소스 파일의 끝까지 설정합니다.

지시문의 효과는 다음과 같습니다.

- `#nullable disable`: null 허용 주석 및 경고 컨텍스트를 *disabled* 로 설정합니다.
- `#nullable enable`: null 허용 주석 및 경고 컨텍스트를 *enabled* 로 설정합니다.
- `#nullable restore`: null 허용 주석 및 경고 컨텍스트를 프로젝트 설정으로 복원합니다.
- `#nullable disable annotations`: null 허용 주석 컨텍스트를 *disabled* 로 설정합니다.
- `#nullable enable annotations`: null 허용 주석 컨텍스트를 *enabled* 로 설정합니다.
- `#nullable restore annotations`: null 허용 주석 컨텍스트를 프로젝트 설정으로 복원합니다.
- `#nullable disable warnings`: null 허용 경고 컨텍스트를 *disabled* 로 설정합니다.
- `#nullable enable warnings`: null 허용 경고 컨텍스트를 *enabled* 로 설정합니다.
- `#nullable restore warnings`: null 허용 경고 컨텍스트를 프로젝트 설정으로 복원합니다.

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 전처리기 지시문](./index.md)
