---
title: '방법: 문자열 구문 분석'
ms.date: 07/20/2015
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
ms.openlocfilehash: 0a9076fc516bb8e6bc74732ca252fabfeda43d53
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398014"
---
# <a name="how-to-parse-a-string-visual-basic"></a>방법: 문자열 구문 분석 (Visual Basic)
이 항목에서는 c #에서 XML 트리를 만드는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 메서드를 사용 하 여 Visual Basic에서 문자열을 구문 분석할 수 있습니다 `XElement.Parse` . 그러나 XML 리터럴을 사용하면 문자열에서 XML의 구문을 분석하는 것과 동일한 성능 저하가 발생하지 않기 때문에 다음 코드에서와 같이 XML 리터럴을 사용하는 것이 더 효율적입니다.  
  
 Xml 리터럴을 사용 하면 XML을 복사 하 여 Visual Basic 프로그램에 붙여 넣을 수 있습니다.  
  
> [!NOTE]
> 텍스트의 구문을 분석하거나 텍스트 파일에서 XML 문서를 로드하는 방법은 함수 생성보다 효율적이지 않습니다. 코드에서 XML 트리를 초기화하는 경우 텍스트의 구문을 분석하는 경우보다 함수 생성을 사용하는 경우에 프로세서 시간을 적게 사용합니다.  
  
```vb  
Dim contacts as XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="home">206-555-0144</Phone>  
            <Phone Type="work">425-555-0145</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>10</NetWorth>  
        </Contact>  
        <Contact>  
            <Name>Gretchen Rivas</Name>  
            <Phone Type="mobile">206-555-0163</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>11</NetWorth>  
        </Contact>  
    </Contacts>  
```  
  
## <a name="see-also"></a>참고 항목

- [XML 구문 분석 (Visual Basic)](parsing-xml.md)
