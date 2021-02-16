---
description: '자세한 정보: 정적 클래스 디자인'
title: 정적 클래스 디자인
ms.date: 10/22/2008
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
ms.openlocfilehash: 16db470ab0975a5545617c9c5471d6ac157e688b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782470"
---
# <a name="static-class-design"></a>정적 클래스 디자인

정적 클래스는 <xref:System.Object?displayProperty=nameWithType> 및 가능한 프라이빗 생성자에서 상속되는 인스턴스 멤버 외에 정적 멤버만 포함하는 클래스로 정의됩니다. 일부 언어에서는 기본적으로 정적 클래스를 지원합니다. C# 2.0 이상에서는 정적으로 선언되는 클래스는 봉인된 추상 클래스이며, 인스턴스 멤버는 재정의하거나 선언할 수 없습니다.

 정적 클래스는 순수 개체 지향 디자인과 단순함 간의 절충안입니다. 일반적으로 다른 작업(예: <xref:System.IO.File?displayProperty=nameWithType>), 확장 메서드의 표시자, 전체 개체 지향 래퍼가 허가되지 않은 기능(예: <xref:System.Environment?displayProperty=nameWithType>)에 대한 바로 가기를 제공하는 데 사용됩니다.

 ✔️ 정적 클래스 사용을 자제하세요.

 정적 클래스는 프레임워크의 개체 지향 코어를 지원하는 클래스로만 사용해야 합니다.

 ❌ 정적 클래스를 기타 버킷으로 처리하지 마세요.

 ❌ 정적 클래스에서 인스턴스 멤버를 선언하거나 재정의하지 마세요.

 ✔️ 프로그래밍 언어에서 기본적으로 정적 클래스를 지원하지 않는 경우 정적 클래스를 봉인된 추상 클래스로 선언하고 프라이빗 인스턴스 생성자를 추가하세요.

 *Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [형식 디자인 지침](type.md)
- [프레임워크 디자인 지침](index.md)
