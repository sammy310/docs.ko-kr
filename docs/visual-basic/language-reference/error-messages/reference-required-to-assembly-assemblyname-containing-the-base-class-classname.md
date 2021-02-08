---
description: "BC30007: ' <assemblyname> ' 기본 클래스를 포함 하는 ' ' 어셈블리에 대 한 참조가 필요 합니다.<classname>"
title: 기본 클래스 '<assemblyname>'을(를) 포함하는 '<classname>' 어셈블리에 대한 참조가 필요합니다.
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: f01795d3e8147015f9f46697b047a8c63099ff32
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792052"
---
# <a name="bc30007-reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a>BC30007: ' ' \<assemblyname> 기본 클래스를 포함 하는 ' ' 어셈블리에 대 한 참조가 필요 합니다. \<classname>

기본 클래스 ' '을 (를) 포함 하는 ' ' 어셈블리에 대 한 참조가 필요 \<assemblyname> \<classname> 합니다. 하나를 프로젝트에 추가합니다.

 클래스는 프로젝트에서 직접 참조하지 않는 어셈블리 또는 DLL(동적 연결 라이브러리)에서 정의됩니다. 클래스가 둘 이상의 DLL 또는 어셈블리에서 정의 된 경우에는 모호성을 방지 하기 위해 Visual Basic 컴파일러에 참조가 필요 합니다.

 **오류 ID:** BC30007

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 참조되지 않은 DLL 또는 어셈블리 이름을 프로젝트 참조에 포함합니다.

## <a name="see-also"></a>참고 항목

- [프로젝트의 참조 관리](/visualstudio/ide/managing-references-in-a-project)
- [Troubleshooting Broken References](/visualstudio/ide/troubleshooting-broken-references)
