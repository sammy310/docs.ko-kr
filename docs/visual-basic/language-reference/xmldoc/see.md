---
title: <see>
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 3c149b8ff60bcc2aba06856ad95f461fb18da4b6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352225"
---
# <a name="see-visual-basic"></a>> 참조 \<(Visual Basic)
다른 멤버에 대 한 링크를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a>매개 변수  
 `member`  
 현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다. 컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 요소 이름에 전달하는지 확인합니다. `member`는 큰따옴표(" ")로 묶어야 합니다.  
  
## <a name="remarks"></a>설명  
 `<see>` 태그를 사용 하 여 텍스트 내에서 링크를 지정 합니다. [\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) 를 사용 하 여 "참고 항목" 섹션에 표시할 텍스트를 지정할 수 있습니다.  
  
 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `UpdateRecord` 설명 섹션의 `<see>` 태그를 사용 하 여 `DoesRecordExist` 메서드를 참조 합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>참고자료

- [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md)
