---
title: 생성자 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- parameterless constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
author: KrzysztofCwalina
ms.openlocfilehash: 074aa391b71257584a01171e95da7472354cdc2c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746782"
---
# <a name="constructor-design"></a>생성자 디자인
생성자의 두 가지가: 생성자 및 인스턴스 생성자를 입력 합니다.  
  
 형식 생성자는 정적 이며 형식 사용 하기 전에 CLR에서 실행 됩니다. 인스턴스 생성자에는 형식의 인스턴스를 만들 때 실행 합니다.  
  
 형식 생성자 매개 변수를 사용할 수 없습니다. 인스턴스 생성자는 다음 작업을 할 수 있습니다. 매개 변수를 사용 하지는 인스턴스 생성자에 매개 변수가 없는 생성자 라고 합니다.  
  
 생성자는 형식의 인스턴스를 만들기 위한 가장 자연 스러운 방법입니다. 대부분의 개발자가 검색 되며 인스턴스 (예: 팩터리 메서드)를 만드는 다른 방법으로 간주 되기 전에 생성자를 사용 하려고 합니다.  
  
 **✓ CONSIDER** 단순, 이상적으로 기본적으로 생성자를 제공 합니다.  
  
 간단한 생성자 매개 변수의 매우 작은 수 있고 모든 매개 변수는 기본 형식 또는 열거형입니다. 이러한 간단한 생성자 프레임 워크의 유용성을 늘립니다.  
  
 **✓ CONSIDER** 원하는 작업의 의미 체계의 새 인스턴스를 생성에 직접 매핑되지 않는 경우 또는 비 자연 느낌 생성자 설계 지침을 따르는 경우 생성자를 대신 정적 팩터리 메서드를 사용 합니다.  
  
 **✓ DO** 가기로 생성자 매개 변수를 사용 하 여 기본 속성을 설정 합니다.  
  
 사이 의미 없는 차이가 일부 속성 집합 뒤에 빈 생성자를 사용 하 고 생성자를 사용 하 여 여러 인수를 사용 합니다.  
  
 **✓ DO** 생성자 매개 변수는 단순히 속성을 설정 하는 데 사용 되는 경우 생성자 매개 변수 및 속성에 대 한 동일한 이름을 사용 합니다.  
  
 이러한 매개 변수 및 속성 간의 유일한 차이점 대/소문자 구분 해야 합니다.  
  
 **✓ DO** 생성자에서 최소한의 작업만 있습니다.  
  
 생성자 캡처 이외의 작업량 생성자 매개 변수를 수행 하지 해야 합니다. 필요할 때 까지는 다른 처리를 지연 해야 합니다.  
  
 **✓ DO** 해당 되는 경우에 인스턴스 생성자에서 예외를 throw 합니다.  
  
 **✓ 수행** 이러한 생성자가 필요한 경우 클래스에서 매개 변수가 없는 public 생성자를 명시적으로 선언 합니다.  
  
 다양 한 언어 형식에서 생성자를 명시적으로 선언 하지 하는 경우 (같은 C#) 매개 변수가 없는 public 생성자를 자동으로 추가 됩니다. (추상 클래스는 protected 생성자를 가져옵니다.)  
  
 클래스에 매개 변수화 된 생성자를 추가 컴파일러를에서 매개 변수가 없는 생성자를 추가 하지 않습니다. 이 오류는 실수로 인 한 주요 변경 내용 많은 경우.  
  
 **하지 말고 X** 구조체에 매개 변수가 없는 생성자를 명시적으로 정의 합니다.  
  
 이렇게 하면 배열 만들기 빠르고 없기 때문에 매개 변수가 없는 생성자를 정의 하지 않은 경우이 배열에 있는 모든 슬롯에서 실행 될 수 있습니다. Note 많은 컴파일러를 포함 하 여 C#의 경우이 매개 변수가 없는 생성자가 구조체를 허용 하지 않습니다.  
  
 **X AVOID** 개체의 생성자 내에서 가상 멤버를 호출 합니다.  
  
 가상 멤버를 호출 하면 가장 많이 파생 된 재정의 호출할 수는 가장 많이 파생 된 형식의 생성자에 완벽 하 게 아직 실행 되지 하는 경우에 합니다.  
  
### <a name="type-constructor-guidelines"></a>형식 생성자 지침  
 **✓ DO** 정적 생성자를 private입니다.  
  
 클래스 생성자, 정적 생성자 형식을 초기화 됩니다. CLR 형식의 첫 번째 인스턴스가 만들어지거나 정적 멤버가 해당 형식에 호출 됩니다 전에 정적 생성자를 호출 합니다. 사용자가 정적 생성자가 호출 하는 경우 제어 하지 않습니다. 정적 생성자를 private 인 경우에 CLR 코드에서 호출할 수 있습니다. 생성자에서 수행 되는 작업에 따라이 예기치 않은 동작이 발생할 수 있습니다. C# 컴파일러를 전용 정적 생성자를 강제로 수행 합니다.  
  
 **X DO NOT** 정적 생성자에서 예외를 throw 합니다.  
  
 형식 생성자에서 예외가 throw 되 면 형식을 사용할 수 없는 현재 응용 프로그램 도메인입니다.  
  
 **✓ CONSIDER** 런타임 형식에서 명시적으로 정의 된 정적 생성자를 갖지 않는의 성능을 최적화할 수 있기 때문에 정적 생성자를 사용 하 여 명시적으로 보다는 정적 필드 인라인을 초기화 합니다.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## <a name="see-also"></a>참고자료

- [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)
- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
