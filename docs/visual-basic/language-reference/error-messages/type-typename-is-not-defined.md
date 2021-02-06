---
description: "자세한 정보: BC30002: 형식 ' <typename> '이 (가) 정의 되지 않았습니다."
title: "'<typename>' 형식이 정의되지 않았습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 48ee0c38492769aea8c1be2e9d54eaa537e35766
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641126"
---
# <a name="bc30002-type-typename-is-not-defined"></a>BC30002: ' \<typename> ' 형식이 정의 되지 않았습니다.

문이 정의 되지 않은 형식에 대 한 참조를 만들었습니다. ,, 또는와 같은 선언 문에서 형식을 정의할 수 있습니다 `Enum` `Structure` `Class` `Interface` .

 **오류 ID:** BC30002

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 형식 정의와 해당 참조가 모두 동일한 철자를 사용 하는지 확인 합니다.

- 참조에서 형식 정의에 액세스할 수 있는지 확인 합니다. 예를 들어 형식이 다른 모듈에 있고 선언 된 경우 `Private` 형식 정의를 참조 하는 모듈로 이동 하거나 선언 `Public` 합니다.

- 형식의 네임 스페이스를 프로젝트 내에서 다시 정의 하지 않았는지 확인 합니다. 인 경우 키워드를 사용 `Global` 하 여 형식 이름을 정규화 합니다. 예를 들어, 프로젝트에서 라는 네임 스페이스를 정의 하는 경우 `System` <xref:System.Object?displayProperty=nameWithType> 키워드를 사용 하 여 정규화 되지 않은 경우 형식에 액세스할 수 없습니다 `Global` `Global.System.Object` .

- 형식이 정의 되어 있지만 해당 형식이 정의 된 개체 라이브러리 또는 형식 라이브러리가 Visual Basic에 등록 되지 않은 경우 **프로젝트** 메뉴에서 **참조 추가** 를 클릭 한 다음 적절 한 개체 라이브러리 또는 형식 라이브러리를 선택 합니다.

- 형식이 대상 .NET Framework 프로필의 일부인 어셈블리에 있는지 확인 합니다. 자세한 내용은 [.NET Framework 대상 지정 오류 문제 해결](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [Visual Basic의 네임스페이스](../../programming-guide/program-structure/namespaces.md)
- [Enum 문](../statements/enum-statement.md)
- [Structure 문](../statements/structure-statement.md)
- [Class 문](../statements/class-statement.md)
- [Interface 문](../statements/interface-statement.md)
- [프로젝트의 참조 관리](/visualstudio/ide/managing-references-in-a-project)
