---
title: 표준 예외 형식 사용
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
ms.openlocfilehash: 6b202d618d9d2216c8998181303250081de6781c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708986"
---
# <a name="using-standard-exception-types"></a>표준 예외 형식 사용
이 섹션에서는 프레임 워크에서 제공 하는 표준 예외 및 사용에 대 한 세부 정보를 설명 합니다. 이 목록은 완전 한 방법이 아닙니다. 다른 프레임 워크 예외 형식의 사용에 대 한 .NET Framework 참조 설명서를 참조 하세요.  
  
## <a name="exception-and-systemexception"></a>예외 및 SystemException  
 **X DO NOT** throw <xref:System.Exception?displayProperty=nameWithType> 또는 <xref:System.SystemException?displayProperty=nameWithType>합니다.  
  
 **X DO NOT** catch `System.Exception` 또는 `System.SystemException` 프레임 워크 코드에 다시 throw 하려는 경우가 아니면 합니다.  
  
 **X AVOID** 위해서 `System.Exception` 또는 `System.SystemException`, 최상위 예외 처리기에서를 제외 하 고 있습니다.  
  
## <a name="applicationexception"></a>ApplicationException  
 **X DO NOT** throw 하거나이 로부터 파생할 <xref:System.ApplicationException>합니다.  
  
## <a name="invalidoperationexception"></a>InvalidOperationException  
 **✓ DO** throw 한 <xref:System.InvalidOperationException> 부적절 한 상태에 개체가 있으면 됩니다.  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>ArgumentException, ArgumentNullException 및 ArgumentOutOfRangeException  
 **✓ DO** throw <xref:System.ArgumentException> 또는 멤버에 잘못 된 인수가 전달 되 면 그 하위 중 하나입니다. 해당 하는 경우 가장 많이 파생 된 예외 형식을 선호 합니다.  
  
 **✓ DO** 설정는 `ParamName` 속성의 서브 클래스 중 하나를 throw 할 때 `ArgumentException`합니다.  
  
 이 속성은 예외를 throw 한 매개 변수의 이름을 나타냅니다. 생성자 오버 로드 중 하나를 사용 하 여 속성을 설정할 수 있습니다.  
  
 **✓ DO** 사용 `value` 속성 setter의 암시적 값 매개 변수 이름에 대 한 합니다.  
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a>NullReferenceException, IndexOutOfRangeException 및 AccessViolationException  
 **X DO NOT** 공개적으로 호출할 수 Api 명시적 또는 암시적으로 throw 할 수 있도록 <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, 또는 <xref:System.IndexOutOfRangeException>합니다. 이러한 예외는 실행 엔진에서 예약 및 throw 되며 대부분의 경우에는 버그를 표시 합니다.  
  
 이러한 예외가 발생 하지 않도록 인수 검사를 수행 합니다. 이러한 예외를 throw 하면 시간이 지남에 따라 변경 될 수 있는 메서드의 구현 세부 정보가 노출 됩니다.  
  
## <a name="stackoverflowexception"></a>StackOverflowException  
 **X DO NOT** 명시적으로 throw <xref:System.StackOverflowException>합니다. 예외는 CLR 에서만 명시적으로 throw 해야 합니다.  
  
 **X DO NOT** catch `StackOverflowException`합니다.  
  
 임의 스택 오버플로가 있는 상태에서 일관성을 유지 하는 관리 코드를 작성 하는 것은 거의 불가능 합니다. CLR의 관리 되지 않는 부분은 프로브를 사용 하 여 스택 오버플로를 임의 스택 오버플로 로부터 백업 하지 않고 잘 정의 된 위치로 이동 하 여 일관성을 유지 합니다.  
  
## <a name="outofmemoryexception"></a>OutOfMemoryException  
 **X DO NOT** 명시적으로 throw <xref:System.OutOfMemoryException>합니다. 이 예외는 CLR 인프라 에서만 throw 됩니다.  
  
## <a name="comexception-sehexception-and-executionengineexception"></a>ComException, SEHException 및 ExecutionEngineException  
 **X DO NOT** 명시적으로 throw <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>, 및 <xref:System.Runtime.InteropServices.SEHException>합니다. 이러한 예외는 CLR 인프라에 의해서만 throw 됩니다.  
  
 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*  
  
 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>참조

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [예외 디자인 지침](../../../docs/standard/design-guidelines/exceptions.md)
