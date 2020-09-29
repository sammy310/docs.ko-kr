---
title: 인터페이스 멤버를 명시적으로 구현하는 방법 - C# 프로그래밍 가이드
description: 이 C# 예제에서는 인터페이스 멤버를 명시적으로 구현하는 방법을 알아봅니다. 멤버는 인터페이스 인스턴스를 통해 액세스합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: a9c019cdcf6e229199d980a2d1913df7c72a2169
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157397"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a>인터페이스 멤버를 명시적으로 구현하는 방법(C# 프로그래밍 가이드)

이 예제에서는 [interface](../../language-reference/keywords/interface.md)`IDimensions` 및 `Box` 클래스를 선언합니다. 이 클래스는 인터페이스 멤버 `GetLength` 및 `GetWidth`를 명시적으로 구현합니다. 멤버는 인터페이스 인스턴스 `dimensions`를 통해 액세스합니다.  
  
## <a name="example"></a>예제  

 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
  
- `Main` 메서드의 다음 줄은 컴파일 오류를 생성하므로 주석으로 처리되었습니다. 명시적으로 구현된 인터페이스 멤버는 [class](../../language-reference/keywords/class.md) 인스턴스에서 액세스할 수 없습니다.  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
- 또한 `Main` 메서드의 다음 줄은 메서드가 인터페이스 인스턴스에서 호출되기 때문에 상자 크기를 성공적으로 출력합니다.  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../index.md)
- [클래스 및 구조체](../classes-and-structs/index.md)
- [인터페이스](./index.md)
- [두 인터페이스의 멤버를 명시적으로 구현하는 방법](./how-to-explicitly-implement-members-of-two-interfaces.md)
