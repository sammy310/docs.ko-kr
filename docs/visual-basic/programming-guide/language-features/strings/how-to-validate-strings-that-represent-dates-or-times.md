---
description: '자세한 정보: 방법: 날짜 또는 시간을 나타내는 문자열 유효성 검사 (Visual Basic)'
title: '방법: 날짜 또는 시간을 나타내는 문자열의 유효성 검사'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 4e9255717d1711d8e9839c218a78b359549d9eef
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100424257"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>방법: 날짜 또는 시간을 나타내는 문자열 확인(Visual Basic)

다음 코드 예제에서는 `Boolean` 문자열이 유효한 날짜 또는 시간을 나타내는지 여부를 나타내는 값을 설정 합니다.  
  
## <a name="example"></a>예  

 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compile-the-code"></a>코드 컴파일  

 `("01/01/03")`및을 `"9:30 PM"` 유효성을 검사할 날짜 및 시간으로 바꿉니다. 문자열을 하드 코드 된 다른 문자열, `String` 변수 또는 문자열을 반환 하는 메서드 (예:)로 바꿀 수 있습니다 `InputBox` .  
  
## <a name="robust-programming"></a>강력한 프로그래밍  

 를 변수로 변환 하기 전에이 메서드를 사용 하 여 문자열의 유효성을 검사 합니다 `String` `DateTime` . 먼저 날짜나 시간을 확인 하 여 런타임에 예외가 생성 되는 것을 방지할 수 있습니다.  
  
## <a name="see-also"></a>추가 정보

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [Visual Basic의 문자열 유효성 검사](validating-strings.md)
