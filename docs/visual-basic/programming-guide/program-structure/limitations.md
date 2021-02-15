---
description: Visual Basic 제한 사항에 대해 자세히 알아보세요.
title: 제한 사항
ms.date: 07/20/2015
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
ms.openlocfilehash: 9182c5fe475e4350cb17ed3e4b734e3924bb9f7b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100432847"
---
# <a name="visual-basic-limitations"></a>Visual Basic 제한 사항

이전 버전의에서는 변수 이름 길이, 모듈에서 허용 되는 변수 수 및 모듈 크기와 같이 코드에서 경계를 적용 Visual Basic. Visual Basic .NET에서는 이러한 제한이 완화 되어 코드를 작성 하 고 정렬 하는 데 더 많은 자유를 제공 합니다.  
  
 실제 제한은 컴파일 시간 고려 사항 보다 런타임 메모리에 따라 달라 집니다. 신중한 프로그래밍 관행을 사용 하 고 큰 응용 프로그램을 여러 클래스 및 모듈로 나누는 경우 내부 Visual Basic 제한이 발생할 가능성이 거의 없습니다.  
  
 극단적인 경우에 발생할 수 있는 몇 가지 제한 사항은 다음과 같습니다.  
  
- **이름 길이입니다.** 선언 된 모든 프로그래밍 요소의 이름에는 최대 자까지 사용할 수 있습니다. 이 최대값은 요소 이름이 정규화 된 경우 전체 정규화 문자열에 적용 됩니다. [Declared Element Names](../language-features/declared-elements/declared-element-names.md)을 참조하세요.  
  
- **줄 길이입니다.** 소스 코드의 물리적 줄에는 최대 65535 자까지 입력할 수 있습니다. 줄 연속 문자를 사용 하는 경우 논리적 소스 코드 줄이 더 길어질 수 있습니다. [방법: 코드에서 문 분리 및 결합을](how-to-break-and-combine-statements-in-code.md)참조 하세요.  
  
- **배열 차원입니다.** 배열에 대해 선언할 수 있는 차원의 최대 수가 있습니다. 이는 배열 요소를 지정 하는 데 사용할 수 있는 인덱스 수를 제한 합니다. [Visual Basic에서 배열 차원을](../language-features/arrays/array-dimensions.md)참조 하세요.  
  
- **문자열 길이입니다.** 단일 문자열에 저장할 수 있는 최대 유니코드 문자 수가 있습니다. [문자열 데이터 형식](../../language-reference/data-types/string-data-type.md)을 참조 하세요.  
  
- **환경 문자열 길이입니다.** 명령줄 인수로 사용 되는 환경 문자열에는 최대 32768 자까지 사용할 수 있습니다. 이는 모든 플랫폼에 대 한 제한 사항입니다.  
  
## <a name="see-also"></a>추가 정보

- [프로그램 구조 및 코드 규칙](program-structure-and-code-conventions.md)
- [Visual Basic 명명 규칙](naming-conventions.md)
