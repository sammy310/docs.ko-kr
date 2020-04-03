---
title: 일반 명명 규칙
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], conflicts
- type names, conflicts
- language-specific type names
- names [.NET Framework], about naming guidelines
- names [.NET Framework], abbreviations
- abbreviation naming guidelines
- acronym naming guidelines
- Hungarian notation
- names [.NET Framework], type names
- names [.NET Framework], acronyms
ms.assetid: d3a77ea1-75d2-4969-a8c3-3e1e3e1aaedc
ms.openlocfilehash: ef4a8f571a67477739bbc59d3103ba78dea47177
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635913"
---
# <a name="general-naming-conventions"></a>일반 명명 규칙

이 섹션에서는 단어 선택과 관련된 일반적인 명명 규칙, 약어 및 머리글자어 사용에 대한 지침 및 언어별 이름을 사용하지 않는 방법에 대한 권장 사항을 설명합니다.

## <a name="word-choice"></a>단어 선택
 ✔️ 쉽게 읽을 수 있는 식별자 이름을 선택합니다.

 예를 들어 명명된 `HorizontalAlignment` 속성은 에 보다 `AlignmentHorizontal`영어읽기가 더 적합합니다.

 ✔️ 간결성보다 가독성을 선호합니다.

 속성 이름은 `CanScrollHorizontally` (X `ScrollableX` 축에 대한 모호한 참조)보다 낫습니다.

 ❌밑줄, 하이픈 또는 기타 알파인이 아닌 문자를 사용하지 마십시오.

 ❌헝가리어 표기는 사용하지 마십시오.

 ❌널리 사용되는 프로그래밍 언어의 키워드와 충돌하는 식별자를 사용하지 마십시오.

 공통 언어 사양(CLS)의 규칙 4에 따라 모든 호환 언어는 해당 언어의 키워드를 식별자로 사용하는 명명된 항목에 대한 액세스를 허용하는 메커니즘을 제공해야 합니다. 예를 들어 C#은 이 경우 @ 기호를 이스케이프 메커니즘으로 사용합니다. 그러나 이스케이프 시퀀스가 없는 키워드보다 이스케이프 시퀀스를 사용하는 것이 훨씬 어렵기 때문에 일반적인 키워드를 사용하지 않는 것이 좋습니다.

## <a name="using-abbreviations-and-acronyms"></a>약어 및 약어 사용
 ❌식별자 이름의 일부로 약어 나 수축을 사용하지 마십시오.

 예를 `GetWin`들어. `GetWindow`

 ❌널리 받아들여지지 않는 약어는 사용하지 마십시오.

## <a name="avoiding-language-specific-names"></a>언어별 이름 피하기
 ✔️ do do는 형식 이름에 대한 언어별 키워드보다는 중요한 용도로 흥미로운 이름을 사용합니다.

 예를 들어, `GetLength` 보다 더 `GetInt`나은 이름입니다.

 ✔️ 식별자가 해당 형식 이외의 의미 체계 의미가 없는 경우 드물게 언어별 이름이 아닌 제네릭 CLR 형식 이름을 사용합니다.

 예를 <xref:System.Int64> 들어 변환하는 메서드는 `ToInt64`이름이 아니라(C#특정 `ToLong` 별칭의 <xref:System.Int64> `long`CLR 이름이기 때문). 다음 표에서는 CLR 형식 이름(C#, Visual Basic 및 C++)에 해당하는 형식 이름뿐만 아니라 CLR 형식 이름을 사용하는 여러 기본 데이터 형식을 제공합니다.

|C#|Visual Basic|C++|CLR|
|---------|------------------|-----------|---------|
|**sbyte**|**SByte**|**char**|**SByte**|
|**바이트**|**Byte**|**unsigned char**|**Byte**|
|**short**|**짧은**|**short**|**Int16**|
|**ushort**|**UInt16**|**unsigned short**|**UInt16**|
|**Int**|**정수**|**Int**|**Int32**|
|**uint**|**UInt32**|**부호 없는 정수**|**UInt32**|
|**긴**|**긴**|**__int64**|**Int64**|
|**Ulong**|**UInt64**|**unsigned __int64**|**UInt64**|
|**플 로트**|**Single**|**플 로트**|**Single**|
|**double**|**double**|**double**|**double**|
|**bool**|**Boolean**|**bool**|**Boolean**|
|**char**|**Char**|**wchar_t**|**Char**|
|**string**|**String**|**String**|**String**|
|**개체**|**Object**|**Object**|**Object**|

 ✔️ 식별자가 의미 체계 `value` 의미가 `item`없고 매개 변수의 형식이 중요하지 않은 경우 드물게 형식 이름을 반복하는 대신 또는 또는 와 같은 공통 이름을 사용합니다.

## <a name="naming-new-versions-of-existing-apis"></a>기존 API의 새 버전 이름 지정
 ✔️ 기존 API의 새 버전을 만들 때 이전 API와 유사한 이름을 사용합니다.

 이렇게 하면 API 간의 관계를 강조 표시하는 데 도움이 됩니다.

 ✔️ 기존 API의 새 버전을 나타내는 접두사 보다는 접미사를 추가하는 것을 선호합니다.

 이렇게 하면 문서를 검색하거나 IntelliSense를 사용할 때 검색에 도움이 됩니다. 대부분의 브라우저와 IntelliSense는 알파벳 순으로 식별자를 표시하기 때문에 API의 이전 버전은 새 API에 가깝게 구성됩니다.

 ✔️ 접미사 나 접두사를 추가하는 대신 새롭지만 의미있는 식별자를 사용하는 것이 좋습니다.

 ✔️ 숫자 접미사를 사용하여 기존 API의 새 버전을 나타내는데, 특히 API의 기존 이름이 의미 있는 유일한 이름(예: 산업 표준인 경우)이고 의미 있는 접미사를 추가하거나 이름을 변경하는 것이 적절한 옵션이 아닌 경우 특히 유용합니다.

 ❌식별자가 동일한 API의 이전 버전과 구별하기 위해 "Ex" (또는 이와 유사한) 접미사를 사용하지 마십시오.

 ✔️ 32비트 정수 대신 64비트 정수(긴 정수)에서 작동하는 API 버전을 도입할 때 "64" 접미사를 사용합니다. 기존 32비트 API가 있는 경우에만 이 방법을 사용하면 됩니다. 64비트 버전만 있는 새로운 API에는 이러한 작업을 수행하지 마십시오.

 *&copy; 2005년, 2009년 마이크로소프트. 판권.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)
- [EditorConfig에 대한 .NET 명명 규칙](/visualstudio/ide/editorconfig-naming-conventions)
