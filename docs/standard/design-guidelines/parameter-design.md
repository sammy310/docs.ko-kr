---
title: 매개 변수 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
author: KrzysztofCwalina
ms.openlocfilehash: 5a0f6e0fab5d0f2fe8574e348fc6b8ae726eeb99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757406"
---
# <a name="parameter-design"></a>매개 변수 디자인
이 섹션에서는 매개 변수 디자인, 인수를 확인 하는 것에 대 한 지침을 사용 하 여 섹션을 비롯 한 광범위 한 지침을 제공 합니다. 에 설명 된 지침을 참조 해야 뿐만 [매개 변수 명명](../../../docs/standard/design-guidelines/naming-parameters.md)합니다.  
  
 **✓ DO** 멤버에 필요한 기능을 제공 하는 최소 파생 된 매개 변수 형식을 사용 합니다.  
  
 예를 들어, 컬렉션을 열거 하 고 각 항목을 콘솔에 출력 하는 메서드를 디자인. 이러한 메서드를 취해야 <xref:System.Collections.IEnumerable> 매개 변수로 되지 <xref:System.Collections.ArrayList> 또는 <xref:System.Collections.IList>예를 들어 있습니다.  
  
 **X DO NOT** 예약 된 매개 변수를 사용 합니다.  
  
 멤버에 대 한 추가 입력 이후 버전에서 필요한 경우에 새 오버 로드를 추가할 수 있습니다.  
  
 **X DO NOT** 가 공개적으로 포인터, 포인터, 배열 또는 다차원 배열을 매개 변수로 사용 하는 메서드를 노출 합니다.  
  
 포인터 및 다차원 배열은 비교적 제대로 사용 하기가 어렵습니다. 대부분의 경우 Api 이러한 형식을 매개 변수로 방지 하기 위해 향후 재설계 될 수 있습니다.  
  
 **✓ DO** 모든 배치 `out` 다음 값으로의 모든 매개 변수 및 `ref` 매개 변수 (매개 변수 배열 제외) 매개 변수 오버 로드 간의 순서 지정에 불일치가 발생 하는 경우에 (참조 [멤버 오버 로드](../../../docs/standard/design-guidelines/member-overloading.md)).  
  
 `out` 메서드 시그니처를 더욱 쉽게 이해 함께 그룹화 하 고 추가 반환 값으로 매개 변수를 볼 수 있습니다.  
  
 **✓ DO** 멤버를 재정의 하는 경우 매개 변수를 명명 또는 인터페이스 멤버 구현 일관 되 게 합니다.  
  
 이 메서드 간의 관계를 더 잘 통신합니다.  
  
### <a name="choosing-between-enum-and-boolean-parameters"></a>열거형 및 부울 매개 변수 중에서 선택  
 **✓ DO** 구성원 부울 매개 변수 두 개 이상의 미칠 경우 열거형을 사용 합니다.  
  
 **X DO NOT** 확실히 될 수 없으므로 두 개 이상의 값에 대 한 필요 하지 않는 한 부울을 사용 합니다.  
  
 열거형 값을 이후 추가할 수 있는 공간을 제공 하지만에서 설명 하는 열거형 값을 추가 하는 모든 의미 고려해 야 [열거형 디자인](../../../docs/standard/design-guidelines/enum.md)합니다.  
  
 **✓ CONSIDER** 부울 값이 실제로 두 가지 상태는 부울 속성을 초기화 하는 생성자 매개 변수를 사용 하 여 합니다.  
  
### <a name="validating-arguments"></a>인수 유효성 검사  
 **✓ DO** public, protected 또는 명시적으로 구현 된 멤버에 전달 되는 인수의 유효성을 검사 합니다. Throw <xref:System.ArgumentException?displayProperty=nameWithType>, 또는 해당 서브 클래스 중 하나를 유효성 검사에 실패 합니다.  
  
 없는 실제 유효성 검사를 반드시 public 또는 protected 멤버 자체에서 발생 하는 참고 합니다. 일부 private 또는 internal 루틴에서 하위 수준에서 발생할 수 있습니다. 중요 한 점은 최종 사용자에 게 노출 되는 전체 화면 영역에서 인수를 검사 하도록 합니다.  
  
 **✓ DO** throw <xref:System.ArgumentNullException> 에 null 인수가 전달 되 고 멤버가 null 인수를 지원 하지 않는 경우.  
  
 **✓ DO** enum 매개 변수 유효성 검사 합니다.  
  
 열거형 인수가 열거형으로 정의 된 범위에 있을 것을 가정 하지 마십시오. CLR 값을 열거형에 정의 되지 않은 경우에 모든 정수 값 열거형 값으로 캐스팅할 수 있습니다.  
  
 **X DO NOT** 사용 <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> 열거형 범위 검사 합니다.  
  
 **✓ DO** 유효성을 검사 한 후 인수가 변경할 수 있는 변경 수에 유의 합니다.  
  
 멤버는 중요 한 보안을 모르는 경우 복사본 및 다음 유효성 검사 및 인수를 처리 하는 것이 좋습니다.  
  
### <a name="parameter-passing"></a>매개 변수 전달  
 프레임 워크 디자이너의 관점에서 그룹이 세 가지 주요 매개 변수: by 값 매개 변수 `ref` 매개 변수 및 `out` 매개 변수입니다.  
  
 인수 값으로 매개 변수를 통해 전달 되 면 멤버에 전달 된 실제 인수의 복사본을 받습니다. 인수 값 형식이 면 인수의 복사본이 스택에 추가 됩니다. 인수가 참조 형식이 면 참조의 복사본이 스택에 추가 됩니다. 가장 인기 있는 CLR 언어와 같은 C#, VB.NET 및 C++를 기본적으로 매개 변수 값으로 전달 합니다.  
  
 인수로 전달 되는 경우는 `ref` 매개 변수를 멤버에 전달 된 실제 인수에 대 한 참조를 수신 합니다. 인수 값 형식이 면 인수에 대 한 참조를 스택에 배치 됩니다. 인수가 참조 형식이 면 참조에 대 한 참조를 스택에 배치 됩니다. `Ref` 호출자에 의해 전달 된 인수를 수정 하려면 멤버 수 있도록 매개 변수를 사용할 수 있습니다.  
  
 `Out` 매개 변수는 유사한 `ref` 매개 변수를 약간 달라 집니다. 매개 변수가 처음 것으로 간주 되어 할당 되지 않은 일부 값을 할당 하기 전에 멤버 본문에서 읽을 수 없습니다. 또한 매개 변수 멤버를 반환 하기 전에 일부 값을 할당 해야 합니다.  
  
 **X AVOID** 를 사용 하 여 `out` 또는 `ref` 매개 변수입니다.  
  
 사용 하 여 `out` 또는 `ref` 매개 변수는 포인터를 값 형식과 참조 형식이 어떻게를 이해 하 고 여러 개의 반환 값을 사용 하 여 메서드를 처리 해야 합니다. 간의 차이 뿐만 `out` 고 `ref` 매개 변수는 잘 알려져 있지 않습니다. 마스터 작업에 사용자가 일반 사용자를 대상에 대 한 디자인 하는 프레임 워크 설계자를 기대할 수 없습니다 `out` 또는 `ref` 매개 변수입니다.  
  
 **X DO NOT** 참조 형식을 참조로 전달 합니다.  
  
 참조를 바꿔 사용할 수 있는 메서드와 같은 규칙으로 제한 된 몇 가지 예외가 있습니다.  
  
### <a name="members-with-variable-number-of-parameters"></a>가변 개수의 매개 변수를 사용 하 여 멤버  
 가변 개수의 인수를 사용할 수 있는 멤버 배열 매개 변수에 제공 하 여 표현 됩니다. 예를 들어 <xref:System.String> 다음 메서드를 제공 합니다.  
  
```  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 사용자를 호출할 수는 <xref:System.String.Format%2A?displayProperty=nameWithType> 메서드를 다음과 같이 합니다.  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 배열 매개 변수에 C# params 키워드를 추가 소위 매개 변수 배열 매개 변수에 매개 변수를 변경 하 고 임시 배열을 만드는 바로 가기를 제공 합니다.  
  
```  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 이렇게 하면 배열 요소를 인수 목록에서 직접 전달 하 여 메서드를 호출 하 합니다.  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 참고 매개 변수 목록의 마지막 매개 변수에 params 키워드를 추가할 수 있습니다.  
  
 **✓ CONSIDER** 는 적은 수의 요소 배열을 전달 하는 최종 사용자가 예상 되는 경우에 params 키워드 배열 매개 변수를 추가 합니다. 예상 하지만 많은 요소 전달할 공통 시나리오, 사용자가 이러한 요소를 인라인으로, 전달 되지 않을 수 있습니다 하 고 params 키워드 이므로 필요 하지 않습니다.  
  
 **X AVOID** 호출자에 게는 거의 항상 이미 입력 배열의 경우 매개 변수 배열을 사용 하 여 합니다.  
  
 예를 들어, 바이트 배열 매개 변수를 사용 하 여 멤버 개별 바이트를 전달 하 여 호출 됩니다 거의 없습니다. 이러한 이유로.NET Framework의 바이트 배열 매개 변수는 params 키워드를 사용 하지 마십시오.  
  
 **X DO NOT** 배열 멤버 params 배열 매개 변수를 사용 하 여 수정 된 경우 매개 변수 배열을 사용 합니다.  
  
 대부분의 컴파일러 호출 사이트에서 임시 배열로 멤버에 대 한 인수를 사용 하는 사실 때문에 배열 임시 개체 일 수 있습니다 및 배열에 대 한 수정은 손실 됩니다.  
  
 **✓ CONSIDER** 단순 오버 로드에서에 params 키워드를 사용 하 여 경우에 더 복잡 한 오버 로드를 사용 하지 못했습니다.  
  
 사용자는 모든 오버 로드의 경우에 매개 변수 배열을 하나의 오버 로드에 있는 값 경우 직접 요청 합니다.  
  
 **✓ DO** params 키워드를 사용할 수 있도록 적절 한 매개 변수를 하려고 합니다.  
  
 **✓ CONSIDER** 적은 수의 성능에 민감한 매우 Api에는 인수를 사용 하 여 호출에 대 한 특별 한 오버 로드와 코드 경로 제공 합니다.  
  
 이렇게 하면 적은 수의 인수를 사용 하 여 API를 호출할 때 배열 개체를 만들지 않도록 합니다. 배열 매개 변수의 단 수 형태를 가져오고 숫자 접미사를 추가 하 여 매개 변수의 이름이 형성 합니다.  
  
 특별 한 경우 전체 코드 경로 배열을 만듭니다 뿐 아니라 한 보다 일반적인 메서드를 호출 하려는 경우에 다음이 수행만 해야 합니다.  
  
 **✓ DO** 유의 매개 변수 배열 인수는 null을 전달할 수 있습니다.  
  
 배열의 처리 하기 전에 null 인지 확인 해야 합니다.  
  
 **X DO NOT** 사용는 `varargs` 메서드, 줄임표 라고도 합니다.  
  
 일부 CLR 언어와 같은 C++를 호출 하는 가변 매개 변수 목록을 전달 하는 것에 대 한 대체는 규칙을 지원 `varargs` 메서드. CLS 규격이 아니므로 프레임 워크에서 규칙을 해야 사용할 수 없습니다.  
  
### <a name="pointer-parameters"></a>포인터 매개 변수  
 일반적으로 포인터 하지 잘 설계 된 관리 코드 프레임 워크는 공개 노출 영역에 나타납니다. 대부분의 경우 포인터를 캡슐화 해야 합니다. 그러나 포인터는 상호 운용성을 위해 필요한 경우에 따라 및 포인터를 사용 하 여 이러한 사례에 적합 합니다.  
  
 **✓ DO** 포인터 CLS 규격이 아닙니다. 때문에 포인터 인수를 사용 하는 멤버에 대 한 대체 방법을 제공 합니다.  
  
 **X AVOID** 과도 한 인수 포인터 인수의 검사를 수행 합니다.  
  
 **✓ DO** 포인터로 멤버를 디자인 하는 경우 일반 포인터와 관련 된 규칙을 따릅니다.  
  
 예를 들어, 간단한 포인터 산술 연산은 동일한 결과 얻는 데 사용할 수 있으므로 시작 인덱스를 전달할 필요가 없습니다 있습니다.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## <a name="see-also"></a>참고자료

- [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)
- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
