---
title: '방법: (Visual Basic) 문자열을 구문 분석'
ms.date: 07/20/2015
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
ms.openlocfilehash: 815e94b3b41c2c0cc1d18d598307ab292919bea4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942599"
---
# <a name="how-to-parse-a-string-visual-basic"></a>방법: (Visual Basic) 문자열을 구문 분석
이 항목에서는 XML 트리를 만드는 방법 C#입니다.  
  
## <a name="example"></a>예제  
 사용 하 여 Visual Basic의 문자열을 구문 분석할 수 있습니다는 `XElement.Parse` 메서드. 그러나 XML 리터럴 문자열에서 XML을 구문 분석으로 동일한 성능 저하의 저하가 발생 하지 않기 때문에 다음 코드에 표시 된 대로 XML 리터럴을 사용 하 여를 더 효율적입니다.  
  
 XML 리터럴을 사용 하 여 복사 하 고 Visual Basic 프로그램에 XML을 붙여 넣습니다. 방금 수 있습니다.  
  
> [!NOTE]
>  텍스트의 구문을 분석하거나 텍스트 파일에서 XML 문서를 로드하는 방법은 함수 생성보다 효율적이지 않습니다. 코드에서 XML 트리를 초기화하는 경우 텍스트의 구문을 분석하는 경우보다 함수 생성을 사용하는 경우에 프로세서 시간을 적게 사용합니다.  
  
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
  
## <a name="see-also"></a>참고자료

- [(Visual Basic) XML 구문 분석](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
