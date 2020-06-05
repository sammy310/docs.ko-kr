---
title: XML 리터럴 및 XML 속성은 ASP.NET의 포함 코드에서 지원되지 않습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
ms.openlocfilehash: bda92b4244631f66142499a94be562854b35437e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406471"
---
# <a name="xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a>XML 리터럴 및 XML 속성은 ASP.NET의 포함 코드에서 지원되지 않습니다.
XML 리터럴 및 XML 속성은 ASP.NET 내의 포함 코드에서 지원 되지 않습니다. XML 기능을 사용 하려면 코드를 코드 숨김으로 이동 합니다.  
  
 XML 리터럴 또는 XML 축 속성은 ASP.NET 파일의 포함 코드 () 내에 정의 됩니다 `<%= =>` .  
  
 **오류 ID:** BC31200  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- XML 리터럴 또는 XML 축 속성을 포함 하는 코드를 ASP.NET 코드 숨김으로 이동 합니다.  
  
## <a name="see-also"></a>참고 항목

- [XML 리터럴](../xml-literals/index.md)
- [XML 축 속성](../xml-axis/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
