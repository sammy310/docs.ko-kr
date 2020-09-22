---
title: <permission>
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: ae6167f3582fe22cd10d9ef7a10873d6d9bdfa06
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872543"
---
# <a name="permission-visual-basic"></a>\<permission>(Visual Basic)

멤버에 필요한 사용 권한을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a>매개 변수  

 `member`  
 현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다. 컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 정식 요소 이름으로 변환하는지 확인합니다. `member`큰따옴표 ("")로 묶습니다.  
  
 `description`  
 멤버 액세스 권한에 대한 설명입니다.  
  
## <a name="remarks"></a>설명  

 태그를 사용 `<permission>` 하 여 멤버에 대 한 액세스를 문서화 합니다. 클래스를 사용 <xref:System.Security.PermissionSet> 하 여 멤버에 대 한 액세스를 지정 합니다.  
  
 [-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  

 이 예제에서는 태그를 사용 하 여 `<permission>` <xref:System.Security.Permissions.FileIOPermission> 이 메서드에 필요 함을 설명 합니다 `ReadFile` .  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a>참조

- [XML 주석 태그](index.md)
