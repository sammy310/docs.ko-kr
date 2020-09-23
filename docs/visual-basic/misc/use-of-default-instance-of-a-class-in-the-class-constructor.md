---
title: 클래스 생성자에 클래스의 기본 인스턴스를 사용하면 무한 재귀 호출이 발생할 수 있습니다.
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: 5d239fdb7dcc5c488bf0341043b810ec7dadc083
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100323"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a>클래스 생성자에 클래스의 기본 인스턴스를 사용하면 무한 재귀 호출이 발생할 수 있습니다.

클래스의 기본 인스턴스가 클래스의 생성자에서 사용되었습니다. 이로 인해 무한 루프라고도 하는 무한 재귀 호출이 발생할 수 있습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 클래스 생성자에서 기본 인스턴스를 제거합니다.  
  
## <a name="see-also"></a>참조

- [생성자](../programming-guide/concepts/object-oriented-programming.md#constructors)
