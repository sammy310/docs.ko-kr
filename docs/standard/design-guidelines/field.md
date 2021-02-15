---
description: '자세한 정보: 필드 디자인'
title: 필드 디자인
ms.date: 10/22/2008
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
ms.openlocfilehash: 88df60c3050035221dc65429bbd543c71d5d69b3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642047"
---
# <a name="field-design"></a>필드 디자인

캡슐화의 원칙은 개체 지향 디자인에서 가장 중요한 개념 중 하나입니다. 이 원칙에 따르면 개체 내에 저장된 데이터에는 해당 개체만 액세스할 수 있어야 합니다.

 이 원칙은 형식의 멤버에 대한 코드 이외의 코드를 중단하지 않고 해당 형식의 필드를 변경(이름 또는 형식 변경)할 수 있도록 형식을 디자인해야 한다는 의미로 해석하는 것이 가장 유용합니다. 이 해석은 곧 모든 필드가 프라이빗이어야 함을 의미합니다.

 상수 및 정적 읽기 전용 필드와 같은 필드는 정의에 따라 변경할 필요가 없기 때문에 이 엄격한 제한에서 제외합니다.

 ❌ 퍼블릭이거나 보호된 인스턴스 필드를 제공하지 마세요.

 퍼블릭 또는 보호된 필드로 설정하는 속성 대신 필드에 액세스하기 위한 속성을 제공해야 합니다.

 ✔️ 변경되지 않는 상수에는 상수 필드를 사용하세요.

 컴파일러는 const 필드의 값을 호출 코드에 직접 포함합니다. 따라서 호환성을 손상하지 않고 const 값을 변경할 수 없습니다.

 ✔️ 미리 정의된 개체 인스턴스에 퍼블릭 정적 `readonly` 필드를 사용하세요.

 형식의 미리 정의된 인스턴스가 있는 경우 형식 자체의 퍼블릭 읽기 전용 정적 필드로 선언하세요.

 ❌ 변경 가능한 형식의 인스턴스를 `readonly` 필드에 할당하지 마세요.

 변경 가능한 형식은 인스턴스화된 후 수정할 수 있는 인스턴스가 있는 형식입니다. 예를 들어 배열, 대부분의 컬렉션, 스트림은 변경 가능한 형식이지만 <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>은 모두 변경할 수 없습니다. 참조 형식 필드의 읽기 전용 한정자는 필드에 저장된 인스턴스를 대체할 수 없도록 하지만 인스턴스를 변경하는 멤버를 호출하여 필드의 인스턴스 데이터를 수정할 수 있습니다.

 *Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [멤버 디자인 지침](member.md)
- [프레임워크 디자인 지침](index.md)
