---
title: XML CDATA 리터럴(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: ee269ca5cf9635fec35165d1ea65d6a6483cadef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938634"
---
# <a name="xml-cdata-literal-visual-basic"></a>XML CDATA 리터럴(Visual Basic)
리터럴 나타내는 <xref:System.Xml.Linq.XCData> 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a>요소  
 `<![CDATA[`  
 필수 요소. XML CDATA 섹션의 시작을 나타냅니다.  
  
 `content`  
 필수 요소. XML CDATA 섹션에 표시할 텍스트 내용입니다.  
  
 `]]>`  
 필수 요소. 섹션의 끝을 나타냅니다.  
  
## <a name="return-value"></a>반환 값  
 <xref:System.Xml.Linq.XCData> 개체입니다.  
  
## <a name="remarks"></a>설명  
 XML CDATA 섹션에는 포함 하지만 구문 분석 되지 포함 하는 XML을 사용 하 여 해야 하는 원시 텍스트를 있습니다. XML CDATA 섹션 모든 텍스트를 포함할 수 있습니다. 예약 된 XML 문자를 포함 합니다. XML CDATA 섹션 종료 시퀀스를 사용 하 여 "]] >"입니다. 이 다음 사항을 의미 합니다.  
  
- 포함된 식 구분 기호는 유효한 XML CDATA 내용 때문에 XML CDATA 리터럴 포함된 식을 사용할 수 없습니다.  
  
- XML CDATA 섹션 중첩 될 수 없으므로 있으므로 `content` 값을 포함할 수 없습니다 "]] >"입니다.  
  
 XML 주석 리터럴에서 변수에 할당할 수도 있고 XML 요소 리터럴에 포함할 수 있습니다.  
  
> [!NOTE]
>  XML 리터럴을 여러 줄으로 나누어 입력할 수 있지만 줄 연속 문자를 사용 하지 않습니다. 이 옵션을 사용 하면 XML 문서에서 콘텐츠를 복사 하 고 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.  
  
 Visual Basic 컴파일러를 호출 하는 XML CDATA 리터럴 변환 된 <xref:System.Xml.Linq.XCData.%23ctor%2A> 생성자입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 텍스트를 포함 하는 CDATA 섹션 "리터럴 포함 될 수 있습니다 \<XML > 태그"입니다.  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a>참고자료

- <xref:System.Xml.Linq.XCData>
- [XML 요소 리터럴](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md)
- [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
