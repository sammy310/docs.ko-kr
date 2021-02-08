---
description: '자세한 정보: XML 처리 명령 리터럴 (Visual Basic)'
title: XML 처리 명령 리터럴
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: 5037aab343cbe50ebc48614991e96da8198a481f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787528"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a>XML 처리 명령 리터럴(Visual Basic)

개체를 나타내는 리터럴입니다 <xref:System.Xml.Linq.XProcessingInstruction> .  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>부분  

 `<?`  
 필수 사항입니다. XML 처리 명령 리터럴의 시작을 나타냅니다.  
  
 `piName`  
 필수 사항입니다. 처리 명령이 대상으로 하는 응용 프로그램을 나타내는 이름입니다. "Xml" 또는 "XML"로 시작할 수 없습니다.  
  
 `piData`  
 선택 사항입니다. 에서 대상으로 하는 응용 프로그램이 `piName` XML 문서를 처리 하는 방법을 나타내는 문자열입니다.  
  
 `?>`  
 필수 사항입니다. 처리 명령의 끝을 나타냅니다.  
  
## <a name="return-value"></a>Return Value  

 <xref:System.Xml.Linq.XProcessingInstruction> 개체입니다.  
  
## <a name="remarks"></a>설명  

 XML 처리 명령 리터럴은 응용 프로그램이 XML 문서를 처리 하는 방법을 지정 합니다. 응용 프로그램이 XML 문서를 로드할 때 응용 프로그램은 XML 처리 명령을 확인 하 여 문서 처리 방법을 결정할 수 있습니다. 응용 프로그램은 및의 의미를 해석 합니다 `piName` `piData` .  
  
 XML 문서 리터럴은 XML 처리 명령의 구문과 비슷한 구문을 사용 합니다. 자세한 내용은 [XML 문서 리터럴](xml-document-literal.md)을 참조 하세요.  
  
> [!NOTE]
> `piName`Xml 1.0 사양에서는 이러한 식별자를 예약 하기 때문에 요소는 문자열 "xml" 또는 "xml"로 시작할 수 없습니다.  
  
 XML 처리 명령 리터럴을 변수에 할당 하거나 XML 문서 리터럴에 포함할 수 있습니다.  
  
> [!NOTE]
> XML 리터럴은 줄 연속 문자 없이 여러 줄에 걸쳐 있을 수 있습니다. 이렇게 하면 XML 문서에서 콘텐츠를 복사 하 여 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.  
  
 Visual Basic 컴파일러는 XML 처리 명령 리터럴을 생성자에 대 한 호출로 변환 합니다 <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> .  
  
## <a name="example"></a>예제  

 다음 예에서는 XML 문서에 대 한 스타일 시트를 식별 하는 처리 명령을 만듭니다.  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Xml.Linq.XProcessingInstruction>
- [XML 문서 리터럴](xml-document-literal.md)
- [XML 리터럴](index.md)
- [Visual Basic에서 XML 만들기](../../programming-guide/language-features/xml/creating-xml.md)
