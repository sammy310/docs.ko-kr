---
description: 'BC31200: XML 리터럴 및 XML 속성이 ASP.NET 내의 포함 코드에서 지원 되지 않음에 대해 자세히 알아보세요.'
title: XML 리터럴 및 XML 속성은 ASP.NET의 포함 코드에서 지원되지 않습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
ms.openlocfilehash: 0a5328676ee38a56334b77f665a464daa586ce3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701406"
---
# <a name="bc31200-xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a>BC31200: ASP.NET 내의 포함 코드에서는 XML 리터럴 및 XML 속성이 지원 되지 않습니다.

XML 리터럴 및 XML 속성은 ASP.NET 내의 포함 코드에서 지원 되지 않습니다. XML 기능을 사용 하려면 코드를 코드 숨김으로 이동 합니다.

 XML 리터럴 또는 XML 축 속성은 ASP.NET 파일의 포함 코드 () 내에 정의 됩니다 `<%= =>` .

 **오류 ID:** BC31200

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- XML 리터럴 또는 XML 축 속성을 포함 하는 코드를 ASP.NET 코드 숨김으로 이동 합니다.

## <a name="see-also"></a>참고 항목

- [XML 리터럴](../xml-literals/index.md)
- [XML 축 속성](../xml-axis/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
