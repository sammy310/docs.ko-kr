---
title: 멤버 오버로드
ms.date: 10/22/2008
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
ms.openlocfilehash: 16e84f06ec388fe7e3c221f35c3e970b9b483ba5
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820971"
---
# <a name="member-overloading"></a>멤버 오버로드
멤버 오버 로드는 매개 변수의 개수나 형식만 다르고 이름이 동일한 동일한 형식으로 둘 이상의 멤버를 만드는 것을 의미 합니다. 예를 들어, 다음에서 메서드는 `WriteLine` 오버 로드 됩니다.

```csharp
public static class Console {
    public void WriteLine();
    public void WriteLine(string value);
    public void WriteLine(bool value);
    ...
}
```

 메서드, 생성자 및 인덱싱된 속성만 매개 변수를 가질 수 있으므로 해당 멤버만 오버 로드 될 수 있습니다.

 오버 로드는 유용성, 생산성 및 재사용 가능한 라이브러리의 가독성을 향상 시키기 위한 가장 중요 한 기술 중 하나입니다. 매개 변수 수를 오버 로드 하면 더 간단한 버전의 생성자와 메서드를 제공할 수 있습니다. 매개 변수 형식에 대 한 오버 로드를 사용 하면 선택한 다른 형식 집합에 대해 동일한 작업을 수행 하는 멤버에 대해 동일한 멤버 이름을 사용할 수 있습니다.

 설명 매개 변수 이름을 사용 하 여 짧은 오버 로드에서 사용 되는 기본값을 나타내는 ✔️ 합니다.

 ❌ 오버 로드에서 임의로 다양 한 매개 변수 이름을 사용 하지 않습니다. 한 오버 로드의 매개 변수가 다른 오버 로드의 매개 변수와 동일한 입력을 나타내는 경우 매개 변수의 이름이 같아야 합니다.

 ❌ 오버 로드 된 멤버의 매개 변수 순서가 일치 하지 않도록 합니다. 이름이 같은 매개 변수는 모든 오버 로드에서 동일한 위치에 표시 되어야 합니다.

 ✔️ 가장 긴 오버 로드 가상 (확장성이 필요한 경우)만 수행 합니다. 짧은 오버 로드는 단순히를 통해 보다 긴 오버 로드를 호출 해야 합니다.

 ❌`ref`또는 `out` 한정자를 사용 하 여 멤버를 오버 로드 하지 마세요.

 일부 언어에서는 다음과 같은 오버 로드에 대 한 호출을 확인할 수 없습니다. 또한 이러한 오버 로드는 일반적으로 완전히 다른 의미 체계를 가지 며 오버 로드를 제외 하 고 별도의 두 메서드를 대신 하 여 사용할 수 있습니다.

 ❌ 다른 의미 체계를 사용 하는 동일한 위치 및 유사한 형식의 매개 변수가 있는 오버 로드가 없습니다.

 ✔️ `null` 은 선택적 인수를 전달 하도록 허용 합니다.

 ✔️는 기본 인수를 사용 하 여 멤버를 정의 하는 대신 멤버 오버 로드를 사용 합니다.

 기본 인수는 CLS 규격이 아닙니다.

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [멤버 디자인 지침](member.md)
- [프레임 워크 디자인 지침](index.md)
