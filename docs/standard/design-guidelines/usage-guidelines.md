---
title: 사용 지침
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
ms.openlocfilehash: 57f6600f60e99c72b72c9f82856dc9eb631a9d4b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708999"
---
# <a name="usage-guidelines"></a>사용 지침

이 섹션에는 공개적으로 액세스할 수 있는 Api에서 공용 형식을 사용 하기 위한 지침이 포함 되어 있습니다. 기본 제공 프레임 워크 형식 (예: serialization 특성)을 직접 사용 하 고 일반적인 연산자를 오버 로드 하는 방법을 다룹니다.
  
이 단원에서는 <xref:System.IDisposable?displayProperty=nameWithType> 인터페이스에 대해 다루지 않지만 [삭제 패턴](../garbage-collection/implementing-dispose.md) 섹션에 설명 되어 있습니다.

> [!NOTE]
> 일반적인 기본 제공 .NET Framework 형식에 대 한 지침 및 추가 정보는 <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>에 대 한 참조 항목을 참조 하세요.

## <a name="in-this-section"></a>단원 내용

[배열](arrays.md)  
[특성](attributes.md)  
[컬렉션](guidelines-for-collections.md)  
[serialization](serialization.md)  
[System.Xml 사용법](system-xml-usage.md)  
[같음 연산자](equality-operators.md)  

*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*
  
## <a name="see-also"></a>참조

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
