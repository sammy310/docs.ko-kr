---
description: '자세한 정보: XML 파일 처리 (Visual Basic)'
title: XML 파일 처리
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
ms.openlocfilehash: 2314e7dafbd747f9a19b73d06d71c73631e53861
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468397"
---
# <a name="processing-the-xml-file-visual-basic"></a>XML 파일 처리(Visual Basic)

컴파일러는 문서 생성을 위해 태그가 지정되는 코드의 각 구문에 대해 ID 문자열을 생성합니다. 코드에 태그를 설정 하는 방법에 대 한 자세한 내용은 [XML 주석 태그](../../language-reference/xmldoc/index.md)를 참조 하세요. ID 문자열은 구문을 고유 하 게 식별 합니다. XML 파일을 처리 하는 프로그램은 ID 문자열을 사용 하 여 해당 하는 .NET Framework metadata/reflection 항목을 식별할 수 있습니다.  
  
 XML 파일은 코드의 계층적 표현이 아닙니다. 각 요소에 대해 생성 된 ID가 있는 단순 목록입니다.  
  
 컴파일러는 ID 문자열을 생성할 때 다음 규칙을 관찰합니다.  
  
- 문자열에 공백이 배치되지 않았습니다.  
  
- ID 문자열의 첫 부분이 뒤에 콜론이 붙은 한 글자로 식별 대상 멤버를 식별합니다. 다음 멤버 유형이 사용 됩니다.  
  
|문자|설명|  
|---|---|  
|N|namespace<br /><br /> 네임 스페이스에 문서 주석을 추가할 수는 없지만 지원 되는 경우에는이에 대 한 CREF 참조를 만들 수 있습니다.|  
|T|형식: `Class` , `Module` , `Interface` , `Structure` , `Enum` , `Delegate`|  
|F|필드가 `Dim`|  
|P|속성: `Property` (기본 속성 포함)|  
|M|메서드: `Sub` , `Function` , `Declare` , `Operator`|  
|E|이벤트 `Event`|  
|!|오류 문자열<br /><br /> 문자열의 나머지 부분은 오류에 대한 정보를 제공합니다. Visual Basic 컴파일러는 확인할 수 없는 링크에 대 한 오류 정보를 생성 합니다.|  
  
- 의 두 번째 부분은 `String` 네임 스페이스의 루트에서 시작 하는 항목의 정규화 된 이름입니다. 항목의 이름, 바깥쪽 형식 및 네임 스페이스는 마침표로 구분 됩니다. 항목 자체의 이름에 마침표가 포함 되어 있으면 숫자 기호 (#)로 대체 됩니다. 이름에 직접 번호 기호가 있는 항목이 없는 것으로 가정 합니다. 예를 들어 생성자의 정규화 된 이름은 `String` `System.String.#ctor` 입니다.  
  
- 속성 및 메서드의 경우 메서드에 대한 인수가 있으면 괄호로 묶인 인수 목록이 문자열 뒤에 붙습니다. 인수가 없으면 괄호도 없습니다. 인수는 쉼표로 구분됩니다. 각 인수의 인코딩은 .NET Framework 시그니처에서 인코딩 되는 방식을 직접 따릅니다.  
  
## <a name="example"></a>예  

 다음 코드에서는 클래스 및 해당 멤버에 대 한 ID 문자열이 생성 되는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbcnXmlDocComments#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#10)]  
  
## <a name="see-also"></a>추가 정보

- [-doc](../../reference/command-line-compiler/doc.md)
- [방법: XML 설명서 만들기](how-to-create-xml-documentation.md)
