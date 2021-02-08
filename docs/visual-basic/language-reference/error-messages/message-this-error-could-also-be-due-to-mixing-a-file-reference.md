---
description: '자세한 내용은 다음에 대해 자세히 알아보세요. BC30971: <message> 이 오류는 파일 참조가 어셈블리에 대 한 프로젝트 참조를 혼합 했기 때문에 발생할 수도 있습니다.<assemblyname>'
title: <message> 이 오류는 '<assemblyname>' 어셈블리에 대한 프로젝트 참조와 파일 참조가 섞여 있기 때문에 발생할 수도 있습니다.
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: c3b7c27c3f253389cd0a8e725ddcae3816c612b5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795848"
---
# <a name="bc30971-message-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-assemblyname"></a>BC30971: \<message> 이 오류는 ' ' 어셈블리에 대 한 프로젝트 참조와 파일 참조가 섞여 있기 때문에 발생할 수도 있습니다. \<assemblyname>

\<message> 이 오류는 ' 어셈블리에 대 한 프로젝트 참조와 파일 참조가 섞여 있기 때문에 발생할 수도 있습니다 \<assemblyname> . ' 이 경우 ' ' 프로젝트의 ' '에 대 한 파일 참조를 \<assemblyfilename> \<projectname1> ' '에 대 한 프로젝트 참조로 바꿔 보세요 \<projectname2> .

 프로젝트의 코드에서 다른 프로젝트의 멤버에 액세스 하지만 솔루션 구성에서는 Visual Basic 컴파일러가 참조를 확인할 수 없습니다.

 다른 어셈블리에 정의 된 형식에 액세스 하려면 Visual Basic 컴파일러에 해당 어셈블리에 대 한 참조가 있어야 합니다. 이 참조는 프로젝트 간의 순환 참조를 발생시키지 않는 명확한 단일 참조여야 합니다.

 **오류 ID:** BC30971

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 참조할 프로젝트에 가장 적합한 어셈블리를 생성하는 프로젝트를 결정합니다. 이러한 결정을 위해 파일 접근성 및 업데이트 빈도 등의 조건을 사용할 수 있습니다.

2. 프로젝트 속성에서 사용 중인 형식을 정의하는 어셈블리가 포함된 프로젝트에 대한 참조를 추가합니다.

## <a name="see-also"></a>참고 항목

- [프로젝트의 참조 관리](/visualstudio/ide/managing-references-in-a-project)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)
- [Troubleshooting Broken References](/visualstudio/ide/troubleshooting-broken-references)
