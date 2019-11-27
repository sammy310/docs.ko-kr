---
title: 액세스 수준
ms.date: 05/10/2018
helpviewer_keywords:
- members [Visual Basic], accessing in Visual Basic
- Friend access modifier
- access levels, declared elements
- access levels
- access modifiers
- Public access modifier
- Protected access modifier
- Protected Friend access modifier
- Private Protected access modifier
- Private access modifier
- declared elements [Visual Basic], access level
ms.assetid: 6e06c1ab-fd78-47f0-83a8-1152780b5e1a
ms.openlocfilehash: 33a218a2acc3c876428d6c9a887280a559f84323
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348675"
---
# <a name="access-levels-in-visual-basic"></a>Visual Basic의 액세스 수준

선언 된 요소의 *액세스 수준은* 이에 대 한 액세스 권한 (즉, 코드를 읽거나 쓸 수 있는 권한이 있는 코드)의 범위입니다. 이는 요소 자체를 선언 하는 방법 뿐만 아니라 요소 컨테이너의 액세스 수준에 의해서도 결정 됩니다. 포함 하는 요소에 액세스할 수 없는 코드는 `Public`으로 선언 된 요소를 비롯 하 여 포함 된 요소에 액세스할 수 없습니다. 예를 들어, 구조체를 포함 하는 클래스 내에서 `Private` 구조체의 `Public` 변수를 액세스할 수 있지만 해당 클래스 외부에서는 액세스할 수 없습니다.

## <a name="public"></a>Public

선언문의 [Public](../../../language-reference/modifiers/public.md) 키워드는 동일한 프로젝트의 모든 위치, 프로젝트를 참조 하는 다른 프로젝트 및 프로젝트에서 빌드된 모든 어셈블리에서 요소에 액세스할 수 있도록 지정 합니다. 다음 코드는 샘플 `Public` 선언을 보여 줍니다.

```vb
Public Class ClassForEverybody
```

`Public`는 모듈, 인터페이스 또는 네임 스페이스 수준 에서만 사용할 수 있습니다. 즉, 소스 파일 또는 네임 스페이스의 수준에서 또는 인터페이스, 모듈, 클래스 또는 구조체 내에서 public 요소를 선언할 수 있지만 프로시저에는 선언할 수 없습니다.
  
## <a name="protected"></a>보호됨

선언 문의 [Protected](../../../language-reference/modifiers/protected.md) 키워드는 동일한 클래스 또는이 클래스에서 파생 된 클래스 내 에서만 요소에 액세스할 수 있도록 지정 합니다. 다음 코드는 샘플 `Protected` 선언을 보여 줍니다.

```vb
Protected Class ClassForMyHeirs
```

클래스의 멤버를 선언 하는 경우에만 클래스 수준 에서만 `Protected`를 사용할 수 있습니다. 즉, 클래스에서 보호 된 요소를 선언할 수 있지만 소스 파일이 나 네임 스페이스의 수준이 나 인터페이스, 모듈, 구조체 또는 프로시저 내에서 선언할 수 없습니다.

## <a name="friend"></a>Friend

선언문의 [Friend](../../../language-reference/modifiers/friend.md) 키워드는 동일한 어셈블리 내에서 요소에 액세스할 수 있지만 어셈블리 외부에서 액세스할 수 없도록 지정 합니다. 다음 코드는 샘플 `Friend` 선언을 보여 줍니다.

```vb
Friend stringForThisProject As String
```

`Friend`는 모듈, 인터페이스 또는 네임 스페이스 수준 에서만 사용할 수 있습니다. 즉, 소스 파일 또는 네임 스페이스의 수준에서 또는 인터페이스, 모듈, 클래스 또는 구조체 내에서 friend 요소를 선언할 수 있지만 프로시저에는 선언할 수 없습니다.

## <a name="protected-friend"></a>Protected Friend

선언 문의 [Protected Friend](../../../language-reference/modifiers/protected-friend.md) 키워드 조합은 요소가 파생 클래스에서 또는 동일한 어셈블리 내에서 또는 둘 모두에 액세스할 수 있도록 지정 합니다. 다음 코드는 샘플 `Protected Friend` 선언을 보여 줍니다.

```vb
Protected Friend stringForProjectAndHeirs As String
```

클래스의 멤버를 선언 하는 경우에만 클래스 수준 에서만 `Protected Friend`를 사용할 수 있습니다. 즉, 보호 된 friend 요소를 클래스에서 선언할 수 있지만 소스 파일이 나 네임 스페이스의 수준이 나 인터페이스, 모듈, 구조체 또는 프로시저 내에서 선언할 수 없습니다.

## <a name="private"></a>프라이빗

선언문의 [Private](../../../language-reference/modifiers/private.md) 키워드는 동일한 모듈, 클래스 또는 구조체 내 에서만 요소에 액세스할 수 있도록 지정 합니다. 다음 코드는 샘플 `Private` 선언을 보여 줍니다.

```vb
Private _numberForMeOnly As Integer
```

`Private`는 모듈 수준에서만 사용할 수 있습니다. 즉, 모듈, 클래스 또는 구조체 내에서 private 요소를 선언할 수 있지만 소스 파일이 나 네임 스페이스, 인터페이스 내부 또는 프로시저의 수준에서는 선언할 수 없습니다.

모듈 수준에서 액세스 수준 키워드가 없는 `Dim` 문은 `Private` 선언과 동일 합니다. 그러나 코드를 읽고 해석 하기 쉽도록 `Private` 키워드를 사용 하는 것이 좋습니다.

## <a name="private-protected"></a>비공개 보호

선언문의 [Private Protected](../../../language-reference/modifiers/private-protected.md) 키워드 조합은 동일한 클래스 뿐 아니라 포함 하는 클래스와 동일한 어셈블리에 있는 파생 클래스 에서만 요소에 액세스할 수 있도록 지정 합니다. `Private Protected` 액세스 한정자는 Visual Basic 15.5부터 지원 됩니다.

다음 예제에서는 `Private Protected` 선언을 보여 줍니다.

```vb
Private Protected internalValue As Integer
```

`Private Protected` 요소는 클래스 내부 에서만 선언할 수 있습니다. 인터페이스 또는 구조체 내에서 선언 하거나, 소스 파일 또는 네임 스페이스의 수준, 인터페이스 또는 구조체 내에서 또는 프로시저에서 선언할 수 없습니다.

`Private Protected` 액세스 한정자는 Visual Basic 15.5 이상에서 지원 됩니다. 이를 사용 하려면 Visual Basic 프로젝트 ( *\*.vbproj*) 파일에 다음 요소를 추가 합니다. Visual Basic 15.5 이상이 시스템에 설치 되어 있으면 최신 버전의 Visual Basic 컴파일러에서 지 원하는 모든 언어 기능을 활용할 수 있습니다.

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

`Private Protected` 액세스 한정자를 사용 하려면 Visual Basic 프로젝트 ( *\*.vbproj*) 파일에 다음 요소를 추가 해야 합니다.

```xml
<PropertyGroup>
   <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

자세한 내용은 [Visual Basic 언어 버전 설정](../../../language-reference/configure-language-version.md)을 참조 하세요.

## <a name="access-modifiers"></a>액세스 한정자

액세스 수준을 지정 하는 키워드를 *액세스 한정자*라고 합니다. 다음 표에서는 액세스 한정자를 비교 합니다.

|액세스 한정자|액세스 수준 부여 됨|이 액세스 수준으로 선언할 수 있는 요소|이 한정자를 사용할 수 있는 선언 컨텍스트입니다.|
|---------------------|--------------------------|-----------------------------------------------------|----------------------------------------------------------------|
|`Public`|무제한<br /><br /> Public 요소를 볼 수 있는 모든 코드에서 액세스할 수 있습니다.|인터페이스<br /><br /> 모듈<br /><br /> 클래스<br /><br /> 구조<br /><br /> 구조체 멤버<br /><br /> 절차<br /><br /> 속성<br /><br /> 멤버 변수<br /><br /> 상수<br /><br /> 열거형<br /><br /> 이벤트<br /><br /> 외부 선언<br /><br /> 대리자|원본 파일<br /><br /> 네임스페이스<br /><br /> 인터페이스<br /><br /> Module<br /><br /> 클래스<br /><br /> 구조|
|`Protected`|Derivational:<br /><br /> 보호 된 요소 또는이 요소에서 파생 된 클래스를 선언 하는 클래스의 코드는 요소에 액세스할 수 있습니다.|인터페이스<br /><br /> 클래스<br /><br /> 구조<br /><br /> 절차<br /><br /> 속성<br /><br /> 멤버 변수<br /><br /> 상수<br /><br /> 열거형<br /><br /> 이벤트<br /><br /> 외부 선언<br /><br /> 대리자|클래스|
|`Friend`|어셈블리:<br /><br /> Friend 요소를 선언 하는 어셈블리의 코드에서 액세스할 수 있습니다.|인터페이스<br /><br /> 모듈<br /><br /> 클래스<br /><br /> 구조<br /><br /> 구조체 멤버<br /><br /> 절차<br /><br /> 속성<br /><br /> 멤버 변수<br /><br /> 상수<br /><br /> 열거형<br /><br /> 이벤트<br /><br /> 외부 선언<br /><br /> 대리자|원본 파일<br /><br /> 네임스페이스<br /><br /> 인터페이스<br /><br /> Module<br /><br /> 클래스<br /><br /> 구조|
|`Protected` `Friend`|`Protected` 및 `Friend`의 합집합:<br /><br /> 동일한 클래스 또는 보호 된 friend 요소와 같은 어셈블리 또는 요소의 클래스에서 파생 된 클래스 내에서 코드에 액세스할 수 있습니다.|인터페이스<br /><br /> 클래스<br /><br /> 구조<br /><br /> 절차<br /><br /> 속성<br /><br /> 멤버 변수<br /><br /> 상수<br /><br /> 열거형<br /><br /> 이벤트<br /><br /> 외부 선언<br /><br /> 대리자|클래스|
|`Private`|선언 컨텍스트:<br /><br /> Private 요소를 선언 하는 형식의 코드 (포함 된 형식 내 코드 포함)는 요소에 액세스할 수 있습니다.|인터페이스<br /><br /> 클래스<br /><br /> 구조<br /><br /> 구조체 멤버<br /><br /> 절차<br /><br /> 속성<br /><br /> 멤버 변수<br /><br /> 상수<br /><br /> 열거형<br /><br /> 이벤트<br /><br /> 외부 선언<br /><br /> 대리자|Module<br /><br /> 클래스<br /><br /> 구조|
|`Private Protected`|Private protected 요소를 선언 하는 클래스의 코드 또는 bas 클래스와 동일한 어셈블리에 있는 파생 클래스의 코드입니다.|인터페이스<br /><br /> 클래스<br /><br /> 구조<br /><br /> 절차<br /><br /> 속성<br /><br /> 멤버 변수<br /><br /> 상수<br /><br /> 열거형<br /><br /> 이벤트<br /><br /> 외부 선언<br /><br /> 대리자|클래스|

## <a name="see-also"></a>참고자료

- [Dim 문](../../../language-reference/statements/dim-statement.md)
- [정적](../../../language-reference/modifiers/static.md)
- [선언 요소 이름](declared-element-names.md)
- [선언된 요소 참조](references-to-declared-elements.md)
- [선언 요소의 특징](declared-element-characteristics.md)
- [Visual Basic 수명](lifetime.md)
- [Visual Basic 범위](scope.md)
- [방법: 변수의 사용 가능성 제어](how-to-control-the-availability-of-a-variable.md)
- [변수](../variables/index.md)
- [변수 선언](../variables/variable-declaration.md)
