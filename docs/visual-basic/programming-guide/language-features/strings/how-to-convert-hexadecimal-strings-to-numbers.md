---
title: '방법: 16진수 문자열을 숫자로 변환'
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
ms.openlocfilehash: f0a97a0c212a64bfa4db4606ee526b666f07877a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347168"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a>방법: 16진수 문자열을 숫자로 변환(Visual Basic)

이 예제에서는 <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> 메서드를 사용 하 여 16 진수 문자열을 정수로 변환 합니다.

## <a name="to-convert-a-hexadecimal-string-to-a-number"></a>16 진수 문자열을 숫자로 변환 하려면

- <xref:System.Convert.ToInt32(System.String,System.Int32)> 메서드를 사용 하 여 base-16으로 표현 된 숫자를 정수로 변환 합니다.

  <xref:System.Convert.ToInt32(System.String,System.Int32)> 메서드의 첫 번째 인수는 변환할 문자열입니다. 두 번째 인수는 숫자가 표시 되는 기준에 대해 설명 합니다. 16 진수는 base 16입니다.

  [!code-vb[VbVbalrStrings#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#62)]

- 16 진수 문자열에는 다음과 같은 제한 사항이 있습니다.

  - `&h` 접두사는 포함할 수 없습니다.
  - `_` 자릿수 구분 기호를 포함할 수 없습니다.

  접두사 또는 숫자 구분 기호가 있으면 <xref:System.Convert.ToInt32(System.String,System.Int32)> 메서드를 호출 하면 <xref:System.FormatException>throw 됩니다.

## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
