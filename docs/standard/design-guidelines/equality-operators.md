---
description: '자세한 정보: 같음 연산자'
title: 같음 연산자
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
ms.openlocfilehash: 8678ed1b4bc320f685cf7ae172f064b3dededd04
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642242"
---
# <a name="equality-operators"></a>같음 연산자

이 섹션에서는 같음 연산자 오버로드에 대해 설명하고 `operator==` 및 `operator!=`를 같음 연산자로 참조합니다.

 ❌ 같음 연산자 중 하나를 오버로드하지 않고 다른 연산자를 오버로드하지 마세요.

 ✔️ <xref:System.Object.Equals%2A?displayProperty=nameWithType> 및 같음 연산자가 정확하게 동일한 의미 체계 및 유사한 성능 특성을 갖는지 확인하세요.

 즉, 같음 연산자를 오버로드할 때 `Object.Equals`를 재정의해야 함을 의미하는 경우가 많습니다.

 ❌ 같음 연산자에서 예외를 throw하면 안 됩니다.

 예를 들어 인수 중 하나가 null인 경우 `NullReferenceException`을 throw하는 대신 false를 반환합니다.

## <a name="equality-operators-on-value-types"></a>값 형식의 같음 연산자

 ✔️ 같음이 의미가 있는 경우 값 형식에서 같음 연산자를 오버로드하세요.

 대부분의 프로그래밍 언어에는 값 형식에 대한 `operator==`의 기본 구현이 없습니다.

## <a name="equality-operators-on-reference-types"></a>참조 형식의 같음 연산자

 ❌ 변경 가능한 참조 형식에서 같음 연산자를 오버로드하면 안 됩니다.

 많은 언어에는 참조 형식에 대한 기본 제공 같음 연산자가 있습니다. 기본 제공 연산자는 일반적으로 참조 같음을 구현하며, 기본 동작이 값 같음으로 변경될 때 많은 개발자가 놀랍니다.

 불변성으로 인해 참조 같음과 값 같음 간의 차이를 알아차리기가 훨씬 더 어렵기 때문에 변경 불가능한 참조 형식에서는 이 문제가 완화됩니다.

 ❌ 구현 속도가 참조 같음의 구현보다 현저하게 느린 경우 참조 형식에서 같음 연산자를 오버로드하면 안 됩니다.

 *Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임워크 디자인 지침](index.md)
- [사용 지침](usage-guidelines.md)
