---
title: <include>
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: 2f2bebfd06d4614f05cb66834cc5bef40524ce3b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348453"
---
# <a name="include-visual-basic"></a>\<> (Visual Basic) 포함
소스 코드의 형식 및 멤버를 설명 하는 다른 파일을 참조 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
## <a name="parameters"></a>매개 변수  
 `filename`  
 필수입니다. 문서가 포함된 파일의 이름입니다. 경로를 사용하여 파일 이름을 정규화할 수 있습니다. `filename`를 큰따옴표 ("")로 묶습니다.  
  
 `tagpath`  
 필수입니다. `filename`의 태그 경로로, `name` 태그에 연결됩니다. 경로를 큰따옴표 ("")로 묶습니다.  
  
 `name`  
 필수입니다. 주석 앞에 오는 태그의 이름 지정자입니다. `Name`에는 `id`있습니다.  
  
 `id`  
 필수입니다. 주석 앞에 오는 태그의 ID입니다. ID를 작은따옴표 (' ')로 묶습니다.  
  
## <a name="remarks"></a>주의  
 `<include>` 태그를 사용 하 여 소스 코드의 형식 및 멤버를 설명 하는 다른 파일의 주석을 참조할 수 있습니다. 소스 코드 파일에 직접 문서 주석을 포함하는 대신 사용되는 대안입니다.  
  
 `<include>` 태그는 W3C XPath (XML Path Language) 버전 1.0 권장 사항을 사용 합니다. `<include>` 사용을 사용자 지정 하는 방법에 대 한 자세한 내용은 <https://www.w3.org/TR/xpath>을 참조 하세요.  
  
## <a name="example"></a>예제  
 이 예제에서는 `<include>` 태그를 사용 하 여 `commentFile.xml`이라는 파일에서 멤버 문서 주석을 가져옵니다.  
  
 [!code-vb[VbVbcnXmlDocComments#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#4)]  
  
 `commentFile.xml` 형식은 다음과 같습니다.  
  
```xml  
<Docs>  
<Members name="Open">  
<summary>Opens a file.</summary>  
<param name="filename">File name to open.</param>  
</Members>  
<Members name="Close">  
<summary>Closes a file.</summary>  
<param name="filename">File name to close.</param>  
</Members>  
</Docs>  
```  
  
## <a name="see-also"></a>참고 항목

- [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md)
