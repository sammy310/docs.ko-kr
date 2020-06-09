---
title: 어셈블리 및 DLL의 이름
description: 어셈블리 및 Dll (동적 연결 라이브러리)의 이름을 지정 하는 방법에 대 한 지침을 알아봅니다. 어셈블리는 하나 이상의 파일에 걸쳐 있을 수 있지만 일반적으로 하나 이상의 파일에 매핑할 수 있습니다.
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
ms.openlocfilehash: de7ce3ee774d4598521d7156d0d660c3fe30154c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594480"
---
# <a name="names-of-assemblies-and-dlls"></a>어셈블리 및 DLL의 이름
어셈블리는 관리 코드 프로그램에 대 한 배포 및 id의 단위입니다. 어셈블리는 하나 이상의 파일에 걸쳐 있을 수 있지만 일반적으로 어셈블리는 어셈블리를 사용 하 여 일대일로 매핑됩니다. 따라서이 섹션에서는 DLL 명명 규칙에 대해서만 설명 하며,이 규칙을 어셈블리 명명 규칙에 매핑할 수 있습니다.

 ✔️는 System.object와 같이 많은 양의 기능을 제안 하는 어셈블리 Dll의 이름을 선택 합니다.

 어셈블리 및 DLL 이름은 네임 스페이스 이름과 일치 하지 않아도 되지만 어셈블리 이름을 지정할 때 네임 스페이스 이름을 따르는 것이 적절 합니다. 좋은 방법은 어셈블리에 포함 된 네임 스페이스의 공통 접두사를 기반으로 DLL의 이름을 설정 하는 것입니다. 예를 들어, 및 라는 두 네임 스페이스를 포함 하는 어셈블리를 `MyCompany.MyTechnology.FirstFeature` `MyCompany.MyTechnology.SecondFeature` 호출할 수 있습니다 `MyCompany.MyTechnology.dll` .

 다음 패턴에 따라 Dll의 이름을 지정 하는 것이 좋습니다 ✔️.

 `<Company>.<Component>.dll`

 여기 `<Component>` 에는 점으로 구분 된 절이 하나 이상 포함 됩니다. 예를 들면 다음과 같습니다.

 `Litware.Controls.dll`.

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임 워크 디자인 지침](index.md)
- [명명 지침](naming-guidelines.md)
