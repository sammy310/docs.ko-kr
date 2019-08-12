---
title: '방법: 전역 네임스페이스 별칭 사용 - C# 프로그래밍 가이드'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
ms.openlocfilehash: b163981d3cf6d56ab953757931b0b386a47263ff
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796284"
---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a>방법: 전역 네임스페이스 별칭 사용(C# 프로그래밍 가이드)
전역 [네임스페이스](../../../csharp/language-reference/keywords/namespace.md)의 멤버에 액세스하는 기능은 멤버가 동일한 이름의 다른 엔터티에 의해 숨겨질 수 있는 경우에 유용합니다.  
  
 예를 들어 다음 코드에서 `Console`은 <xref:System> 네임스페이스의 `Console` 형식 대신 `TestApp.Console`로 확인됩니다.  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuideNamespaces#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#1)]  
  
 `System.Console`을 사용하면 `System` 네임스페이스가 `TestApp.System` 클래스에 의해 숨겨지기 때문에 여전히 오류가 발생합니다.  
  
 [!code-csharp[csProgGuideNamespaces#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#2)]  
  
 그러나 다음과 같이 `global::System.Console`을 사용하여 이 오류를 해결할 수 있습니다.  
  
 [!code-csharp[csProgGuideNamespaces#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#3)]  
  
 왼쪽 식별자가 `global`이면 오른쪽 식별자 검색이 전역 네임스페이스에서 시작됩니다. 예를 들어 다음 선언에서는 `TestApp`을 전역 공간의 멤버로 참조합니다.  
  
 [!code-csharp[csProgGuideNamespaces#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#4)]  
  
 물론, `System`이라는 고유한 네임스페이스를 만드는 것은 권장되지 않으며, 이러한 작업이 수행된 코드를 발견할 가능성은 거의 없습니다. 그러나 대규모 프로젝트에서는 어떤 형태로든 네임스페이스 중복이 발생할 수 있습니다. 이러한 상황에서 전역 네임스페이스 한정자는 루트 네임스페이스를 지정할 수 있도록 보장합니다.  
  
## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)
- [네임스페이스](../../../csharp/programming-guide/namespaces/index.md)
- [:: 연산자](../../../csharp/language-reference/operators/namespace-alias-qualifier.md)
- [extern](../../../csharp/language-reference/keywords/extern.md)
