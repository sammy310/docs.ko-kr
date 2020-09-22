---
title: "'<typename>'은(는) 기본 <type>의 액세스를 해당 어셈블리 범위 밖으로 확장하므로 <basetypename> '<type>'에서 상속할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: 5adb5a74c220c7b2f95ac7370040a7fa2bd34299
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872066"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a>'\<typename>'은(는) 기본 \<type>의 액세스를 해당 어셈블리 범위 밖으로 확장하므로 \<basetypename> '\<type>'에서 상속할 수 없습니다.

클래스 또는 인터페이스가 기본 클래스 또는 인터페이스에서 상속 되지만 덜 제한적인 액세스 수준을 포함 합니다.  
  
 예를 들어 `Public` 인터페이스는 인터페이스에서 상속 `Friend` 하거나 클래스 `Protected` 에서 상속 `Private` 됩니다. 이는 기본 클래스 또는 인터페이스를 제공 하 여 원하는 수준 이상으로 액세스 합니다.  
  
 **오류 ID:** BC30910  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 파생 클래스 또는 인터페이스의 액세스 수준을 기본 클래스 또는 인터페이스와 최소한 제한적으로 변경 합니다.  
  
     또는  
  
- 덜 제한적인 액세스 수준을 필요로 하는 경우 `Inherits` 문을 제거 합니다. 더 제한 된 기본 클래스 또는 인터페이스에서 상속할 수 없습니다.  
  
## <a name="see-also"></a>참조

- [Class 문](../statements/class-statement.md)
- [Interface 문](../statements/interface-statement.md)
- [Inherits Statement](../statements/inherits-statement.md)
- [Visual Basic의 액세스 수준](../../programming-guide/language-features/declared-elements/access-levels.md)
