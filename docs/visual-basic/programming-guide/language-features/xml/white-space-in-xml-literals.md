---
description: '자세한 정보: XML 리터럴의 공백 (Visual Basic)'
title: XML 리터럴의 공백
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 9b4134626c0ad1f7f4be2923573eb6058fa7687f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100428118"
---
# <a name="white-space-in-xml-literals-visual-basic"></a>XML 리터럴의 공백(Visual Basic)

Visual Basic 컴파일러는 개체를 만들 때 XML 리터럴의 유효 공백 문자만을 포함 합니다 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] . 무효 공백 문자는 통합 되지 않습니다.  
  
## <a name="significant-and-insignificant-white-space"></a>중요 및 무효 공백  

 XML 리터럴의 공백 문자는 다음 세 가지 영역 에서만 의미가 있습니다.  
  
- 특성 값에 있는 경우  
  
- 요소가 요소의 텍스트 내용에 포함 되 고 텍스트에 다른 문자가 포함 된 경우  
  
- 요소가 요소의 텍스트 콘텐츠에 대 한 포함 식에 있는 경우  
  
 그렇지 않으면 컴파일러는 공백 문자를 중요 하지 않은 것으로 처리 하 고이를 리터럴의 개체에 포함 하지 않습니다 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .  
  
 XML 리터럴에 의미 없는 공백을 포함 하려면 공백이 있는 문자열 리터럴이 포함 된 포함 식을 사용 합니다.  
  
> [!NOTE]
> `xml:space`특성이 XML 요소 리터럴에 표시 되는 경우 Visual Basic 컴파일러는 개체에 특성을 포함 <xref:System.Xml.Linq.XElement> 하지만이 특성을 추가 해도 컴파일러에서 공백을 처리 하는 방법은 변경 되지 않습니다.  
  
## <a name="examples"></a>예제  

 다음 예제에는 외부 및 내부 라는 두 개의 XML 요소가 포함 되어 있습니다. 두 요소 모두 텍스트 내용에 공백을 포함 합니다. 외부 요소의 공백은 공백과 XML 요소만 포함 하기 때문에 중요 하지 않습니다. 내부 요소의 공백은 공백과 텍스트를 포함 하기 때문에 중요 합니다.  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 이 코드는 실행 될 때 다음 텍스트를 표시 합니다.  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>추가 정보

- [Visual Basic에서 XML 만들기](creating-xml.md)
