---
title: XML 처리 명령 리터럴(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: 3fbb16a4d47801b671d37566573215d3a57afff1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938608"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a>XML 처리 명령 리터럴(Visual Basic)
리터럴 나타내는 <xref:System.Xml.Linq.XProcessingInstruction> 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>요소  
 `<?`  
 필수 요소. XML 처리 명령 리터럴의 시작을 나타냅니다.  
  
 `piName`  
 필수 요소. 이름을 나타내는 응용 프로그램 처리 명령의 대상입니다. "Xml" 또는 "XML"로 시작할 수 없습니다.  
  
 `piData`  
 선택 사항입니다. 응용 프로그램 대상으로 지정 하는 방법을 나타내는 문자열 `piName` XML 문서를 처리 해야 합니다.  
  
 `?>`  
 필수 요소. 처리 명령의 끝을 나타냅니다.  
  
## <a name="return-value"></a>반환 값  
 <xref:System.Xml.Linq.XProcessingInstruction> 개체입니다.  
  
## <a name="remarks"></a>설명  
 XML 처리 명령 리터럴 응용 프로그램 XML 문서를 처리 해야 하는 방법을 나타냅니다. XML 문서를 로드 하는 응용 프로그램을 하는 경우 응용 프로그램 XML 처리 명령이 문서를 처리 하는 방법을 결정을 확인할 수 있습니다. 응용 프로그램의 의미를 해석 `piName` 고 `piData`입니다.  
  
 리터럴 XML 문서에는 XML 처리 명령 하는 유사한 구문을 사용 합니다. 자세한 내용은 [XML 문서 리터럴](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)합니다.  
  
> [!NOTE]
>  `piName` 요소는 XML 1.0 사양에는 해당 식별자를 예약 하기 때문에 문자열 "xml" 또는 "XML"로 시작할 수 없습니다.  
  
 XML 처리 명령 리터럴 변수에 할당할 수도 있고 리터럴 XML 문서에 포함할 수 있습니다.  
  
> [!NOTE]
>  XML 리터럴의 줄 연속 문자가 필요 없이 여러 줄으로 나누어 입력할 수 있습니다. 이 옵션을 사용 하면 XML 문서에서 콘텐츠를 복사 하 고 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.  
  
 Visual Basic 컴파일러는 XML 처리 명령 리터럴의 호출으로 변환 된 <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> 생성자입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 XML 문서에 대 한 스타일 시트를 식별 하는 처리 명령을 만듭니다.  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a>참고자료

- <xref:System.Xml.Linq.XProcessingInstruction>
- [XML 문서 리터럴](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md)
- [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
