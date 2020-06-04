---
title: <see>
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 380923c2313450afc5745b25eeea6a444705dd3f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411527"
---
# <a name="see-visual-basic"></a>\<see>(Visual Basic)
다른 멤버에 대 한 링크를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a>매개 변수  
 `member`  
 현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다. 컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 요소 이름에 전달하는지 확인합니다. `member`는 큰따옴표(" ")로 묶어야 합니다.  
  
## <a name="remarks"></a>설명  
 태그를 사용 `<see>` 하 여 텍스트 내에서 링크를 지정 합니다. [\<seealso>](seealso.md)"참고 항목" 섹션에 표시할 텍스트를 나타내는 데 사용 합니다.  
  
 [-Doc](../../reference/command-line-compiler/doc.md) 로 컴파일하여 문서 주석을 파일로 처리 합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `<see>` 설명 섹션의 태그를 사용 하 여 `UpdateRecord` 메서드를 참조 `DoesRecordExist` 합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>참고 항목

- [XML 주석 태그](index.md)
