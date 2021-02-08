---
description: '자세히 알아보기: Implements 문'
title: Implements 문
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: aa53d1f3b4ba9d9111f5ffb09198a11511f8d9e9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768989"
---
# <a name="implements-statement"></a>Implements 문

인터페이스가 표시 되는 클래스 또는 구조체 정의에 구현 해야 하는 인터페이스 또는 인터페이스 멤버를 하나 이상 지정 합니다.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Implements interfacename [, ...]  
' -or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a>부분  

 `interfacename`  
 필수 사항입니다. 클래스 또는 구조체의 해당 멤버에 의해 구현 되는 속성, 프로시저 및 이벤트를 포함 하는 인터페이스입니다.  
  
 `interfacemember`  
 필수 사항입니다. 구현 되는 인터페이스의 멤버입니다.  
  
## <a name="remarks"></a>설명  

 인터페이스는 인터페이스에서 캡슐화 하는 멤버 (속성, 프로시저 및 이벤트)를 나타내는 프로토타입의 컬렉션입니다. 인터페이스에는 멤버에 대 한 선언만 포함 됩니다. 클래스와 구조체는 이러한 멤버를 구현 합니다. 자세한 내용은 [인터페이스](../../programming-guide/language-features/interfaces/index.md)를 참조하세요.  
  
 `Implements`문은 또는 문 바로 뒤에와 야 합니다 `Class` `Structure` .  
  
 인터페이스를 구현 하는 경우 인터페이스에 선언 된 모든 멤버를 구현 해야 합니다. 멤버를 생략 하면 구문 오류로 간주 됩니다. 개별 멤버를 구현 하려면 [](implements-clause.md) `Implements` 클래스 또는 구조체에서 멤버를 선언할 때 Implements 키워드 (문과 분리 됨)를 지정 합니다. 자세한 내용은 [인터페이스](../../programming-guide/language-features/interfaces/index.md)를 참조하세요.  
  
 클래스는 속성 및 프로시저의 [전용](../modifiers/private.md) 구현을 사용할 수 있지만 이러한 멤버는 구현 클래스의 인스턴스를 인터페이스 형식으로 선언 된 변수로 캐스팅 하 여 액세스할 수 있습니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 문을 사용 하 여 인터페이스의 멤버를 구현 하는 방법을 보여 줍니다 `Implements` . `ICustomerInfo`이벤트, 속성 및 프로시저를 사용 하 여 라는 인터페이스를 정의 합니다. 클래스는 `customerInfo` 인터페이스에 정의 된 모든 멤버를 구현 합니다.  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 클래스는 클래스에서 `customerInfo` `Implements` 인터페이스의 모든 멤버를 구현 한다는 것을 나타내기 위해 문을 별도의 소스 코드 줄에 사용 합니다 `ICustomerInfo` . 그런 다음 클래스의 각 멤버가 해당 멤버 선언의 일부로 키워드를 사용 하 여 해당 `Implements` 인터페이스 멤버를 구현 함을 표시 합니다.  
  
## <a name="example"></a>예제  

 다음 두 절차에서는 앞의 예제에서 구현 된 인터페이스를 사용 하는 방법을 보여 줍니다. 구현을 테스트 하려면 이러한 프로시저를 프로젝트에 추가 하 고 프로시저를 호출 `testImplements` 합니다.  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>참고 항목

- [구현](implements-clause.md)
- [Interface 문](interface-statement.md)
- [인터페이스](../../programming-guide/language-features/interfaces/index.md)
