---
title: 새 열거형 메서드를 만드는 방법 - C# 프로그래밍 가이드
description: 확장 메서드를 사용하여 C#의 열거형에 기능을 추가하는 방법에 대해 알아봅니다. 이 예제에서는 성적이라는 열거형에 Passing이라는 확장 메서드를 보여줍니다.
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 6c01a73476e98e8344a7a8dc35a5fd80384fc7a2
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864490"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a>새 열거형 메서드를 만드는 방법(C# 프로그래밍 가이드)
확장 메서드를 사용하여 특정 열거형 형식과 관련된 기능을 추가할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서 `Grades` 열거형은 학생이 클래스에서 받을 수 있는 문자 성적을 나타냅니다. 해당 형식의 각 인스턴스가 이제 합격 성적을 나타내는지 여부를 "알 수 있도록" `Passing`이라는 확장 메서드가 `Grades` 형식에 추가됩니다.  
  
 [!code-csharp[csProgGuideExtensionMethods#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#2)]  
  
 또한 `Extensions` 클래스에는 동적으로 업데이트되는 정적 변수가 포함되며, 확장 메서드의 반환 값이 해당 변수의 현재 값을 반영합니다. 이는 확장 메서드가 정의된 정적 클래스에서 내부적으로 직접 호출됨을 보여 줍니다.  
  
## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../index.md)
- [확장명 메서드](./extension-methods.md)
