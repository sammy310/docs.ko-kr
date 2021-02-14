---
description: "자세한 정보: BC30955: ' ' 형식의 값 <typename1> 을 ' ' (으)로 변환할 수 없습니다. <typename2>"
title: "'<typename1>' 형식의 값을 '<typename2>'(으)로 변환할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
ms.openlocfilehash: a013e274a1776dee6a98add63138236ad11111b8
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100426558"
---
# <a name="bc30955-value-of-type-typename1-cannot-be-converted-to-typename2"></a>BC30955: ' ' 형식의 값 \<typename1> 을 ' ' (으)로 변환할 수 없습니다. \<typename2>

' ' 형식의 값 \<typename1> 을 ' ' (으)로 변환할 수 없습니다 \<typename2> . ' ' 어셈블리에 대 한 프로젝트 참조와 파일 참조가 섞여 있기 때문에 형식이 일치 하지 않을 수 있습니다 \<assemblyname> . ' ' 프로젝트의 ' '에 대 한 파일 참조를 \<filepath> \<projectname1> ' '에 대 한 프로젝트 참조로 바꿔 보세요 \<projectname2> .

 프로젝트에서 프로젝트 참조와 파일 참조를 모두 사용 하는 경우 컴파일러는 한 형식을 다른 형식으로 변환할 수 있음을 보장할 수 없습니다.

 다음 의사 코드는이 오류를 생성할 수 있는 상황을 보여 줍니다.

 `' ================ Visual Basic project P1 ================`

 `'        P1 makes a PROJECT REFERENCE to project P2`

 `'        and a FILE REFERENCE to project P3.`

 `Public commonObject As P3.commonClass`

 `commonObject = P2.getCommonClass()`

 `' ================ Visual Basic project P2 ================`

 `'        P2 makes a PROJECT REFERENCE to project P3`

 `Public Function getCommonClass() As P3.commonClass`

 `Return New P3.commonClass`

 `End Function`

 `' ================ Visual Basic project P3 ================`

 `Public Class commonClass`

 `End Class`

 프로젝트에서 프로젝트 `P1` 에 대 한 간접 프로젝트 참조 `P2` `P3` 와에 대 한 직접 파일 참조를 만듭니다 `P3` . 에 대 한 호출에서에 대 한 프로젝트 참조를 사용 하는의 선언에는 `commonObject` 에 대 한 파일 참조가 사용 `P3` `P2.getCommonClass` `P3` 됩니다.

 이 경우의 문제는 파일 참조가의 출력 파일에 대 한 파일 경로 및 이름을 지정 하는 것입니다 `P3` (일반적으로 p3.dll). 프로젝트 참조는 `P3` 프로젝트 이름으로 소스 프로젝트 ()를 식별 합니다. 이로 인해 컴파일러는 형식이 `P3.commonClass` 두 개의 다른 참조를 통해 동일한 소스 코드에서 제공 되는 것을 보장할 수 없습니다.

 이 상황은 일반적으로 프로젝트 참조와 파일 참조가 섞여 있을 때 발생 합니다. 위의 그림에서 `P1` 파일 참조 대신에 직접 프로젝트 참조를 만든 경우 문제가 발생 하지 않습니다 `P3` .

 **오류 ID:** BC30955

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 프로젝트 참조에 대 한 파일 참조를 변경 합니다.

## <a name="see-also"></a>추가 정보

- [Visual Basic의 형식 변환](../../programming-guide/language-features/data-types/type-conversions.md)
- [프로젝트의 참조 관리](/visualstudio/ide/managing-references-in-a-project)
