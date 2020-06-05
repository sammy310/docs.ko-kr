---
title: 문자열 조작 메서드 형식
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: aba9af9c699cf8d07862c5d2967902bec1623500
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363761"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>Visual Basic의 문자열 조작 메서드 유형
문자열을 분석 하 고 조작 하는 여러 가지 방법이 있습니다. 일부 메서드는 Visual Basic 언어의 일부 이며 다른 메서드는 클래스에 내재 되어 있습니다 `String` .  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Visual Basic 언어 및 .NET Framework  
 Visual Basic 메서드는 언어의 고유 함수로 사용 됩니다. 코드에서 한정자 없이 사용할 수 있습니다. 다음 예에서는 Visual Basic 문자열 조작 명령의 일반적인 사용을 보여 줍니다.  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 이 예제에서 함수는 `Mid` 에 대 한 직접 연산을 수행 하 `aString` 고에 값을 할당 `bString` 합니다.  
  
 Visual Basic 문자열 조작 메서드 목록은 [문자열 조작 요약](../../../language-reference/keywords/string-manipulation-summary.md)을 참조 하세요.  
  
### <a name="shared-methods-and-instance-methods"></a>공유 메서드 및 인스턴스 메서드  
 클래스의 메서드를 사용 하 여 문자열을 조작할 수도 있습니다 `String` . 에는 `String` *shared* 메서드와 *인스턴스* 메서드 라는 두 가지 유형의 메서드가 있습니다.  
  
#### <a name="shared-methods"></a>공유 메서드  
 공유 메서드는 `String` 클래스 자체에서 생기고 해당 클래스의 인스턴스가 작동 하지 않아도 되는 메서드입니다. 이러한 메서드는 클래스의 인스턴스가 아닌 클래스 이름 ()으로 정규화 될 수 있습니다 `String` `String` . 예를 들면 다음과 같습니다.  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 앞의 예제에서 메서드는 <xref:System.String.Copy%2A?displayProperty=nameWithType> 지정 된 식에 대해 작동 하 고 결과 값을에 할당 하는 정적 메서드입니다 `bString` .  
  
#### <a name="instance-methods"></a>인스턴스 메서드  
 이와 대조적으로 인스턴스 메서드는의 특정 인스턴스에서 생기고 `String` 인스턴스 이름으로 한정 되어야 합니다. 예를 들면 다음과 같습니다.  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 이 예제에서 메서드는 <xref:System.String.Substring%2A?displayProperty=nameWithType> 의 인스턴스 (즉,)의 메서드입니다 `String` `aString` . 에서 연산을 수행 하 `aString` 고 해당 값을에 할당 `bString` 합니다.  
  
 자세한 내용은 클래스에 대 한 설명서를 참조 하세요 <xref:System.String> .  
  
## <a name="see-also"></a>참고 항목

- [Visual Basic의 문자열 소개](introduction-to-strings.md)
