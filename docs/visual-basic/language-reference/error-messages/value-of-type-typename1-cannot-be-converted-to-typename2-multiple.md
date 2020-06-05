---
title: "'<typename1>' 형식의 값을 '<typename2>'(으)로 변환할 수 없습니다.(여러 파일 참조)"
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 25008f05979638e050b74fc659fdc0a6d13b3c31
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406588"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2-multiple-file-references"></a>'\<typename1>' 형식의 값을 '\<typename2>'(으)로 변환할 수 없습니다.(여러 파일 참조)
' ' 형식의 값 \<typename1> 을 ' ' (으)로 변환할 수 없습니다 \<typename2> . ' ' 프로젝트의 ' '에 대 한 파일 참조와 ' ' 프로젝트의 ' '에 대 한 파일 참조를 혼합 했기 때문에 형식이 일치 하지 않을 수 있습니다 \<filepath1> \<projectname1> \<filepath2> \<projectname2> . 두 어셈블리가 동일하면 동일한 대상을 참조하도록 두 참조를 바꿔 보세요.  
  
 프로젝트에서 어셈블리에 대 한 파일 참조를 두 개 이상 만드는 경우 컴파일러는 한 형식을 다른 형식으로 변환할 수 있음을 보장할 수 없습니다.  
  
 각 파일 참조는 프로젝트의 출력 파일에 대 한 파일 경로와 이름을 지정 합니다 (일반적으로 DLL 파일). 컴파일러가 출력 파일을 동일한 소스에서 제공 하거나 동일한 어셈블리의 동일한 버전을 나타낸다는 것을 보장할 수 없습니다. 따라서 다른 참조의 형식이 동일한 형식이 나 다른 참조로 변환 될 수 있음을 보장할 수 없습니다.  
  
 참조 된 어셈블리의 어셈블리 id가 동일 하다는 것을 알고 있는 경우 단일 파일 참조를 사용할 수 있습니다. *어셈블리 id* 에는 어셈블리 이름, 버전, 공개 키 (있는 경우) 및 문화권이 포함 됩니다. 이 정보는 어셈블리를 고유하게 식별합니다.  
  
 **오류 ID:** BC30961  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 참조 된 어셈블리의 어셈블리 id가 같은 경우 파일 참조 중 하나를 제거 하거나 바꿔서 파일 참조가 하나만 있도록 합니다.  
  
- 참조 된 어셈블리의 어셈블리 id가 같지 않은 경우 한 형식에서 다른 형식으로 변환 하려고 시도 하지 않도록 코드를 변경 합니다.  
  
## <a name="see-also"></a>참고 항목

- [Visual Basic의 형식 변환](../../programming-guide/language-features/data-types/type-conversions.md)
- [프로젝트의 참조 관리](/visualstudio/ide/managing-references-in-a-project)
