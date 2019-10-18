---
title: <permission> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: 904d573514bf35b773d47321b7fd3b6a86e90262
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524693"
---
# <a name="permission-visual-basic"></a>\<permission > (Visual Basic)
멤버에 필요한 사용 권한을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a>매개 변수  
 `member`  
 현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다. 컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 정식 요소 이름으로 변환하는지 확인합니다. @No__t_0를 따옴표 ("")로 묶습니다.  
  
 `description`  
 멤버 액세스 권한에 대한 설명입니다.  
  
## <a name="remarks"></a>주의  
 @No__t_0 태그를 사용 하 여 멤버에 대 한 액세스를 문서화 합니다. @No__t_0 클래스를 사용 하 여 멤버에 대 한 액세스를 지정 합니다.  
  
 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `<permission>` 태그를 사용 하 여 <xref:System.Security.Permissions.FileIOPermission> `ReadFile` 메서드에 필요 함을 설명 합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a>참조

- [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md)
