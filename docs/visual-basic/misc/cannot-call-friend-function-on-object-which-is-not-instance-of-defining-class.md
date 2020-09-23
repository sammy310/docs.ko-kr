---
title: 클래스 정의 인스턴스가 아닌 개체에서 friend 함수를 호출할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: fe95f80d42fc12ab2829db899fe295e32f358db6
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059810"
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a>클래스 정의 인스턴스가 아닌 개체에서 friend 함수를 호출할 수 없습니다.

크로스 프로세스 또는 크로스 스레드로 클래스의 `Friend` 프로시저를 호출하려고 했거나 `Friend` 속성 또는 메서드에 액세스하려고 했습니다. `Friend` 프로시저는 클래스 외부에 있지만 클래스가 정의되는 프로젝트의 일부인 모듈에서 호출할 수 있습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 클래스가 정의되는 프로젝트의 일부인 모듈에서 프로시저를 호출하거나 액세스하고 있는지 확인합니다.  
  
## <a name="see-also"></a>참조

- [Friend](../language-reference/modifiers/friend.md)
