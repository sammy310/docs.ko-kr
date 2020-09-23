---
title: 선언된 XML 요소 및 특성의 이름
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
ms.openlocfilehash: 2142674c3de4c5ac9e806c1328daa3efb697beb9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085622"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a>선언된 XML 요소 및 특성의 이름(Visual Basic)

이 항목에서는 xml 리터럴의 XML 요소와 특성 이름을 지정 하는 Visual Basic 지침을 제공 합니다.  XML 리터럴에서 로컬 이름 또는 정규화 된 이름을 지정할 수 있습니다. 정규화 된 이름은 XML 네임 스페이스 접두사, 콜론 및 로컬 이름으로 구성 됩니다. XML 네임 스페이스 접두사에 대 한 자세한 내용은 [Xml 요소 리터럴](../../../language-reference/xml-literals/xml-element-literal.md)을 참조 하세요.  
  
## <a name="rules"></a>규칙  

 Visual Basic에 있는 요소 또는 특성의 로컬 이름은 다음 규칙을 따라야 합니다.  
  
- 네임 스페이스로 시작할 수 있습니다. 알파벳 문자 또는 밑줄 ()로 시작 해야 합니다 `_` .  
  
- 알파벳 문자, 10 진수 숫자, 밑줄, 마침표 (.) 및 하이픈 (-)만 포함 해야 합니다.  
  
- 길이는 1024 자이 하 여야 합니다.  
  
- 이름에 표시 되는 콜론은 네임 스페이스 경계를 의미 합니다. 따라서 콜론만 사용 하 여 특정 이름에 대 한 XML 네임 스페이스를 지정할 수 있습니다.  
  
 또한 다음 지침을 따라야 합니다.  
  
- XML 1.0 사양은 대문자 변형의 문자열 "xml"로 시작 하는 모든 이름을 예약 합니다. 따라서 요소 및 특성 이름에는 이러한 이름을 사용 하지 마십시오.  
  
### <a name="name-length-guidelines"></a>이름 길이 지침  

 실제로는 요소의 특성을 명확 하 게 식별 하면서 가능한 한 짧은 이름 이어야 합니다. 이렇게 하면 코드의 가독성을 높이고 줄 길이와 소스 파일 크기를 줄입니다.  
  
 그러나 요소 또는 코드에서 요소를 사용 하는 방법을 적절 하 게 설명 하지 않는 것은 아닙니다. 이는 코드의 가독성을 높이기 위해 중요 합니다. 다른 사용자가이를 이해 하려고 하거나 사용자가 작성 한 후 오랜 시간을 확인 하는 경우 적절 한 요소 이름을 통해 시간을 절약할 수 있습니다.  
  
## <a name="case-sensitivity-in-names"></a>이름에서 대/소문자 구분  

 XML 요소 이름은 대/소문자를 구분 합니다. 즉, Visual Basic 컴파일러는 알파벳 대/소문자만 다른 두 이름을 비교할 때 다른 이름으로 해석 합니다. 예를 들어 및는 `ABC` `abc` 개별 요소를 참조 하는 것으로 해석 됩니다.  
  
## <a name="xml-namespaces"></a>XML 네임스페이스  

 XML 요소 리터럴을 만들 때 요소 이름에 대 한 XML 네임 스페이스 접두사를 지정할 수 있습니다. 자세한 내용은 [XML 요소 리터럴](../../../language-reference/xml-literals/xml-element-literal.md)을 참조 하세요.  
  
## <a name="see-also"></a>참조

- [Visual Basic에서 XML 만들기](creating-xml.md)
- [XML 요소 리터럴](../../../language-reference/xml-literals/xml-element-literal.md)
