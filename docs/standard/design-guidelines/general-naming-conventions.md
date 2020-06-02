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
ms.openlocfilehash: c90987fd28d5157cfb7f7eea4680b5ab4be1a200
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290956"
---
# <a name="general-naming-conventions"></a>일반 명명 규칙

이 섹션에서는 단어 선택, 약어 및 머리글자어 사용에 대 한 지침, 언어별 이름 사용을 방지 하는 방법에 대 한 권장 사항을 설명 하는 일반적인 명명 규칙을 설명 합니다.

## <a name="word-choice"></a>단어 선택
 쉽게 읽을 수 있는 식별자 이름을 선택 ✔️ 합니다.

 예를 들어 라는 속성 `HorizontalAlignment` 은 보다 영어에서 읽을 수 `AlignmentHorizontal` 있습니다.

 ✔️를 통해 보다 쉽게 이해할 필요가 있습니다.

 속성 이름이 `CanScrollHorizontally` `ScrollableX` (X 축에 대 한 모호한 참조) 보다 좋습니다.

 ❌밑줄, 하이픈 또는 다른 영숫자가 아닌 문자를 사용 하지 마십시오.

 ❌헝가리어 표기법은 사용 하지 마십시오.

 ❌널리 사용 되는 프로그래밍 언어의 키워드와 충돌 하는 식별자를 사용 하지 마십시오.

 CLS (공용 언어 사양)의 규칙 4에 따라 모든 규격 언어는 해당 언어의 키워드를 식별자로 사용 하는 명명 된 항목에 대 한 액세스를 허용 하는 메커니즘을 제공 해야 합니다. 예를 들어 c #에서는이 경우 이스케이프 메커니즘으로 @ 기호를 사용 합니다. 그러나 이스케이프 시퀀스가 없는 메서드를 사용 하는 것은 훨씬 더 어렵기 때문에 일반적인 키워드를 사용 하지 않는 것이 좋습니다.

## <a name="using-abbreviations-and-acronyms"></a>약어 및 머리글자어 사용
 ❌식별자 이름의 일부로 약어 또는 축약를 사용 하지 마십시오.

 예를 들어 대신를 사용 `GetWindow` `GetWin` 합니다.

 ❌광범위 하 게 허용 되지 않는 머리글자어를 사용 하 고, 필요한 경우에만 사용 하지 마십시오.

## <a name="avoiding-language-specific-names"></a>언어별 이름 방지
 ✔️ 형식 이름에 대해 언어별 키워드 대신 의미 있는 이름을 사용 합니다.

 예를 들어 `GetLength` 는 보다 더 나은 이름입니다 `GetInt` .

 드문 경우 이지만 식별자에 형식 이외의 의미 체계가 없는 경우에는 언어별 이름이 아니라 제네릭 CLR 형식 이름을 사용 ✔️ 합니다.

 예를 들어를로 변환 하는 메서드는 <xref:System.Int64> `ToInt64` `ToLong` ( <xref:System.Int64> c # 관련 별칭의 CLR 이름)이 아니라로 명명 되어야 합니다 `long` . 다음 표에서는 CLR 형식 이름 뿐만 아니라 c #, Visual Basic 및 c + +에 해당 하는 형식 이름을 사용 하는 여러 기본 데이터 형식을 보여 줍니다.

|C#|Visual Basic|C++|CLR|
|---------|------------------|-----------|---------|
|**sbyte**|**SByte**|**char**|**SByte**|
|**바이트**|**Byte**|**unsigned char**|**Byte**|
|**short**|**간략히**|**short**|**Int16**|
|**ushort**|**UInt16**|**unsigned short**|**UInt16**|
|**int**|**값**|**int**|**Int32**|
|**uint**|**UInt32**|**unsigned int**|**UInt32**|
|**long**|**Long**|**__int64**|**Int64**|
|**ulong**|**UInt64**|**unsigned __int64**|**UInt64**|
|**float**|**Single**|**float**|**Single**|
|**double**|**double**|**double**|**double**|
|**bool**|**Boolean**|**bool**|**Boolean**|
|**char**|**Char**|**wchar_t**|**Char**|
|**string**|**String**|**String**|**String**|
|**object**|**Object**|**Object**|**Object**|

 `value` `item` 드문 경우 이지만 식별자에 의미 체계가 없고 매개 변수의 형식이 중요 하지 않은 경우에는 형식 이름을 반복 하는 대신 또는와 같은 일반 이름을 사용 ✔️ 합니다.

## <a name="naming-new-versions-of-existing-apis"></a>새 버전의 기존 Api 이름 지정
 기존 api의 새 버전을 만들 때 이전 API와 유사한 이름을 사용 ✔️ 합니다.

 이렇게 하면 Api 간의 관계를 강조 표시 하는 데 도움이 됩니다.

 기존 API의 새 버전을 나타내기 위해 접두사 대신 접미사를 추가 하는 것이 좋습니다 ✔️.

 그러면 설명서를 찾아보거나 IntelliSense를 사용 하 여 검색을 지원할 수 있습니다. 대부분의 브라우저와 IntelliSense는 식별자를 사전순으로 표시 하기 때문에 이전 버전의 API는 새 Api와 거의 유사 하 게 구성 됩니다.

 ✔️ 접미사 또는 접두사를 추가 하는 대신 새로운 브랜드의 의미 있는 식별자를 사용 하는 것이 좋습니다.

 기존 API의 새 버전을 나타내기 위해 숫자 접미사를 사용 합니다. 특히 API의 기존 이름이 적절 한 이름 (예: 업계 표준) 인 경우에는 의미 있는 접미사를 추가 하거나 이름을 변경 하는 것이 적절 한 옵션이 아닌 경우에 ✔️ 합니다.

 ❌식별자에 대해 "Ex" (또는 이와 유사한) 접미사를 사용 하 여 동일한 API의 이전 버전과 구별 하지 마십시오.

 ✔️ 32 비트 정수 대신 64 비트 정수 (long 정수)에서 작동 하는 Api 버전을 도입할 때 "64" 접미사를 사용 합니다. 기존 32 비트 API가 있는 경우에만이 방법을 사용 해야 합니다. 64 비트 버전만 사용 하는 새로운 Api에 대해서는이 작업을 수행 하지 마세요.

 *&copy;2005 부분, 2009 Microsoft Corporation. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임워크 디자인 지침](index.md)
- [명명 지침](naming-guidelines.md)
- [EditorConfig에 대한 .NET 명명 규칙](/visualstudio/ide/editorconfig-naming-conventions)
