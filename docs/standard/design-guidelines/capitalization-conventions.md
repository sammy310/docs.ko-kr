---
title: 대/소문자 표기법
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
ms.openlocfilehash: 10d628700a9cbf0e842416878ec2c7febfa3d6f5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280402"
---
# <a name="capitalization-conventions"></a>대/소문자 표기법
이 장의 지침은 일관 되 게 적용 될 때 형식, 멤버 및 매개 변수에 대 한 식별자를 쉽게 읽을 수 있도록 하는 사례를 사용 하는 간단한 방법을 설명 합니다.

## <a name="capitalization-rules-for-identifiers"></a>식별자에 대 한 대/소문자 규칙
 식별자에서 단어를 구분 하려면 식별자에서 각 단어의 첫 글자를 대문자로 바꿉니다. 밑줄을 사용 하 여 단어를 구분 하거나 식별자의 어디에서 나 해당 문제를 구분 하지 마십시오. 식별자를 사용 하는 방법에 따라 두 가지 적절 한 방법으로 식별자를 대문자를 사용할 수 있습니다.

- 대/소문자 구분

- camelCasing

 매개 변수 이름을 제외한 모든 식별자에 사용 되는 대/소문자 구분 규칙은 다음 예제에 표시 된 것과 같이 각 단어의 첫 번째 문자 (두 문자 길이에 대 한 머리글자어 포함)를 대문자로 표시 합니다.

 `PropertyDescriptor`
 `HtmlTag`

 다음 식별자에 표시 된 것 처럼 두 문자를 대문자로 표기 하는 두 문자로 된 머리글자어에 대해 특별 한 사례가 수행 됩니다.

 `IOStream`

 다음 예제와 같이 매개 변수 이름에만 사용 되는 camelCasing 규칙은 첫 번째 단어를 제외 하 고 각 단어의 첫 번째 문자를 대문자로 표시 합니다. 또한이 예제에서는 카멜식 대/소문자를 구분 하는 식별자를 시작 하는 두 문자로 된 머리글자어는 모두 소문자입니다.

 `propertyDescriptor`
 `ioStream`
 `htmlTag`

 ✔️는 여러 단어로 구성 된 모든 public 멤버, 형식 및 네임 스페이스 이름에 대 한 대/소문자를 사용 합니다.

 매개 변수 이름에 camelCasing를 사용 ✔️ 합니다.

 다음 표에서는 다양 한 유형의 식별자에 대 한 대/소문자 규칙을 설명 합니다.

|ID|대/소문자 구분|예제|
|----------------|------------|-------------|
|네임스페이스|파스칼식|`namespace System.Security { ... }`|
|유형|파스칼식|`public class StreamReader { ... }`|
|인터페이스|파스칼식|`public interface IEnumerable { ... }`|
|방법|파스칼식|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|
|속성|파스칼식|`public class String {` <br />  `public int Length { get; }` <br /> `}`|
|이벤트|파스칼식|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|
|필드|파스칼식|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|
|열거형 값|파스칼식|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|
|매개 변수|Camel|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|

## <a name="capitalizing-compound-words-and-common-terms"></a>복합 단어 및 일반적인 단어를 대문자로
 대부분의 복합 용어는 대문자 표시를 위해 단일 단어로 취급 됩니다.

 ❌닫힌 형태의 복합 단어에서 각 단어를 대문자로 표기 하지 마십시오.

 이러한 단어는 끝점과 같이 단일 단어로 작성 된 복합 단어입니다. 대/소문자를 구분 하기 위해 폐쇄형 형식의 복합 단어를 단일 단어로 처리 합니다. 현재 사전을 사용 하 여 복합 단어가 닫힌 형태로 작성 되었는지 확인 합니다.

|파스칼식|Camel|Not|
|------------|-----------|---------|
|`BitFlag`|`bitFlag`|`Bitflag`|
|`Callback`|`callback`|`CallBack`|
|`Canceled`|`canceled`|`Cancelled`|
|`DoNot`|`doNot`|`Don't`|
|`Email`|`email`|`EMail`|
|`Endpoint`|`endpoint`|`EndPoint`|
|`FileName`|`fileName`|`Filename`|
|`Gridline`|`gridline`|`GridLine`|
|`Hashtable`|`hashtable`|`HashTable`|
|`Id`|`id`|`ID`|
|`Indexes`|`indexes`|`Indices`|
|`LogOff`|`logOff`|`LogOut`|
|`LogOn`|`logOn`|`LogIn`|
|`Metadata`|`metadata`|`MetaData, metaData`|
|`Multipanel`|`multipanel`|`MultiPanel`|
|`Multiview`|`multiview`|`MultiView`|
|`Namespace`|`namespace`|`NameSpace`|
|`Ok`|`ok`|`OK`|
|`Pi`|`pi`|`PI`|
|`Placeholder`|`placeholder`|`PlaceHolder`|
|`SignIn`|`signIn`|`SignOn`|
|`SignOut`|`signOut`|`SignOff`|
|`UserName`|`userName`|`Username`|
|`WhiteSpace`|`whiteSpace`|`Whitespace`|
|`Writable`|`writable`|`Writeable`|

## <a name="case-sensitivity"></a>대/소문자 구분
 CLR에서 실행할 수 있는 언어는 대/소문자 구분을 지 원하는 데 필요 하지 않습니다. 언어가 지 원하는 경우에도 프레임 워크에 액세스할 수 있는 다른 언어는 그렇지 않습니다. 따라서 외부에서 액세스할 수 있는 모든 Api는 사례를 단독으로 사용 하 여 동일한 컨텍스트에서 두 이름을 구분할 수 없습니다.

 ❌모든 프로그래밍 언어가 대/소문자를 구분 한다고 가정 하지 마십시오. 그러나 동일하지 않습니다. 이름은 대/소문자만 다를 수 있습니다.

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임 워크 디자인 지침](index.md)
- [명명 지침](naming-guidelines.md)
