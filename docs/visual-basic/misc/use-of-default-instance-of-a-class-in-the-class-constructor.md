---
description: '자세히 알아보기: 클래스 생성자에 클래스의 기본 인스턴스를 사용 하면 무한 재귀 호출이 발생할 수 있습니다.'
title: 클래스 생성자에 클래스의 기본 인스턴스를 사용하면 무한 재귀 호출이 발생할 수 있습니다.
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: f65956c92f7d391aa77734d7afd5adf3bea1f906
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475684"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a>클래스 생성자에 클래스의 기본 인스턴스를 사용하면 무한 재귀 호출이 발생할 수 있습니다.

클래스의 기본 인스턴스가 클래스의 생성자에서 사용되었습니다. 이로 인해 무한 루프라고도 하는 무한 재귀 호출이 발생할 수 있습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 클래스 생성자에서 기본 인스턴스를 제거합니다.  
  
## <a name="see-also"></a>추가 정보

- [생성자](../programming-guide/concepts/object-oriented-programming.md#constructors)
