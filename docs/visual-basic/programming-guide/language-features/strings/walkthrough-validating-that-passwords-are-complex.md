---
title: 암호 복잡도 확인
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: 8cb04286e98cf78f0fb66dde92002ee09e2ea0f5
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556247"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a>연습: 암호의 복합성 검사(Visual Basic)
이 메서드는 몇 가지 강력한 암호 특성을 확인 하 고 암호가 실패 한 검사에 대 한 정보를 사용 하 여 문자열 매개 변수를 업데이트 합니다.  
  
 암호는 보안 시스템에서 사용자에 게 권한을 부여 하는 데 사용할 수 있습니다. 그러나 암호는 권한이 없는 사용자가 추측 하기 어려울 수 있습니다. 공격자는 사전에 있는 모든 단어를 반복 하는 *사전 공격* 프로그램 (또는 다른 언어로 된 여러 사전을 사용 하 여)을 사용할 수 있으며, 모든 단어가 사용자의 암호로 작동 하는지 테스트 합니다. "Yankees" 또는 "Mustang"와 같은 취약 한 암호를 신속 하 게 추측할 수 있습니다. 더 강력한 암호 (예: "? ' L1N3vaFiNdMeyeP@sSWerd ! "을 (를) 추측할 가능성이 훨씬 낮습니다. 암호로 보호 된 시스템은 사용자가 강력한 암호를 선택 하도록 해야 합니다.  
  
 강력한 암호는 복합 (대문자, 소문자, 숫자 및 특수 문자를 혼합 하 여) 하며 단어는 아닙니다. 이 예에서는 복잡성을 확인 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
  
### <a name="code"></a>코드  
 [!code-vb[VbVbcnRegEx#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a>코드 컴파일  
 해당 암호를 포함 하는 문자열을 전달 하 여이 메서드를 호출 합니다.  
  
 이 예제에는 다음 사항이 필요합니다.  
  
- <xref:System.Text.RegularExpressions> 네임스페이스의 멤버에 대한 액세스 권한. 코드에서 멤버 이름을 정규화하지 않는 경우 `Imports` 문을 추가합니다. 자세한 내용은 [Imports 문(.NET 네임스페이스 및 형식)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하세요.  
  
## <a name="security"></a>보안  
 네트워크를 통해 암호를 이동 하는 경우 데이터를 전송 하는 안전한 방법을 사용 해야 합니다. 자세한 내용은 [ASP.NET Web Application Security](/previous-versions/aspnet/330a99hc(v=vs.100))을 참조 하세요.
  
 `ValidatePassword`더 복잡 한 검사를 추가 하 여 함수의 정확도를 향상할 수 있습니다.  
  
- 사용자 이름, 사용자 id 및 응용 프로그램 정의 사전과의 암호와 해당 부분 문자열을 비교 합니다. 또한 비교를 수행할 때 시각적으로 비슷한 문자를 동등 하 게 처리 합니다. 예를 들어, "l" 및 "e" 문자를 숫자 "1"과 "3"에 해당 하는 것으로 간주 합니다.  
  
- 대문자가 하나만 있는 경우 암호의 첫 문자가 아닌지 확인 합니다.  
  
- 암호의 마지막 두 문자가 편지 문자 인지 확인 합니다.  
  
- 모든 기호가 키보드의 맨 위 행에서 입력 되는 암호를 허용 하지 않습니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Text.RegularExpressions.Regex>
- [ASP.NET 웹 애플리케이션 보안](/previous-versions/aspnet/330a99hc(v=vs.100))
