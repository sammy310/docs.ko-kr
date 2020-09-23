---
title: 대상 디렉터리가 소스 디렉터리 아래에 있기 때문에 작업을 완료할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: d159b9bb3a765a2fefe99fa15dff42e979fda9e3
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91079141"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a>대상 디렉터리가 소스 디렉터리 아래에 있기 때문에 작업을 완료할 수 없습니다.

순환 작업이 실패했습니다. 순환 작업이 계속 실행되므로 완료할 수 없습니다. 예를 들어 개체 A는 개체 B에서 상속하려고 하고 개체 B는 개체 A에서 상속하려고 합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 상속 시 순환 참조가 없어야 합니다.  
  
## <a name="see-also"></a>참조

- [오류 형식](../programming-guide/language-features/error-types.md)
- [Visual Studio 디버거에서 중단점 사용](/visualstudio/debugger/using-breakpoints)
