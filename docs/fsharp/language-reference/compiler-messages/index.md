---
title: 컴파일러 오류 및 경고
description: F# 컴파일러가 내보낼 오류 및 경고에 대한 설명과 해결 방법
ms.date: 12/21/2019
ms.openlocfilehash: 58430297abe807027afdc52841d67d1233401ff1
ms.sourcegitcommit: e395fabeeea5c705d243d246fa64446839ac85b6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2021
ms.locfileid: "97856122"
---
# <a name="f-compiler-messages"></a>F# 컴파일러 메시지

이 섹션에서는 F# 컴파일러가 특정 구문에 대해 내보내는 컴파일러 오류 및 경고에 대해 자세히 설명합니다. 기본 오류 집합은 다음과 같이 하여 변경할 수 있습니다.

- `-warnaserror+` 컴파일러 옵션을 사용하여 특정 경고를 오류로 취급하고

- `-nowarn` 컴파일러 옵션을 사용하여 특정 경고를 무시합니다.

특정 경고나 오류가 아직 이 섹션에 기록되지 않은 경우

- 이 페이지 끝으로 이동하여 오류 번호나 텍스트를 포함한 피드백을 보내거나
- [create-new-fsharp-compiler-message.fsx](https://github.com/dotnet/docs/blob/master/docs/fsharp/language-reference/compiler-messages/util/create-new-fsharp-compiler-message.fsx)의 지침에 따라 이 리포지토리에 대한 끌어오기 요청을 열어 직접 추가하세요.

## <a name="see-also"></a>참조

- [F# 컴파일러 옵션](../compiler-options.md)
