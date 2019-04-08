---
title: XML 리터럴 및 XML 속성은 ASP.NET의 포함 코드에서 지원되지 않습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
ms.openlocfilehash: 79be695478983055ae1f016cf841d733d3f4c430
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813927"
---
# <a name="xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a>XML 리터럴 및 XML 속성은 ASP.NET의 포함 코드에서 지원되지 않습니다.
XML 리터럴과 XML 속성은 ASP.NET의 포함된 코드에서 지원 되지 않습니다. XML 기능을 사용 하려면 코드 숨김에 코드를 이동 합니다.  
  
 XML 리터럴 또는 XML 축 속성이 포함 된 코드 내에서 정의 됩니다 (`<%= =>`) ASP.NET 파일에 있습니다.  
  
 **오류 ID:** BC31200  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   리터럴 XML을 포함 하는 코드 또는 XML 축 속성을 ASP.NET 코드 숨김 파일을 이동 합니다.  
  
## <a name="see-also"></a>참고자료

- [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md)
- [XML 축 속성](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
