---
title: 리소스 이름 지정
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
ms.openlocfilehash: b64a3ef6e12f8ea1abf7efd9c22f2f4333dda5c8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709168"
---
# <a name="naming-resources"></a>리소스 이름 지정
지역화할 수 있는 리소스는 속성과 같이 특정 개체를 통해 참조 될 수 있기 때문에 리소스에 대 한 명명 지침은 속성 지침과 비슷합니다.  
  
 **✓ DO** PascalCasing 리소스 키에 사용 합니다.  
  
 **✓ DO** 설명 하는 대신 짧은 식별자를 제공 합니다.  
  
 **X DO NOT** 주 CLR 언어의 언어 관련 키워드를 사용 합니다.  
  
 **✓ DO** 영숫자 문자와 밑줄 리소스 이름 지정 시에 사용 합니다.  
  
 **✓ DO** 예외 메시지 리소스에 대 한 다음과 같은 명명 규칙을 사용 합니다.  
  
 리소스 식별자는 예외 형식 이름 및 예외의 짧은 식별자 여야 합니다.  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*  
  
 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>참조

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)
