---
title: 네임스페이스의 이름
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
ms.openlocfilehash: 0678f695e3ae7c40660031862c9073a21fd72491
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709233"
---
# <a name="names-of-namespaces"></a>네임스페이스의 이름
다른 명명 지침과 마찬가지로 네임 스페이스의 이름을 지정할 때의 목표는 프레임 워크를 사용 하 여 프로그래머에 게 네임 스페이스의 콘텐츠를 즉시 알 수 있는 충분 한 명확성을 만드는 것입니다. 다음 템플릿은 네임 스페이스 이름 지정에 대 한 일반 규칙을 지정 합니다.  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 예를 들면 다음과 같습니다.  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 **✓ DO** 이름이 같은 다른 회사의 네임 스페이스를 방지 하기 위해 회사 이름이 있는 네임 스페이스 이름 접두사를 사용 합니다.  
  
 **✓ DO** 네임 스페이스 이름의 두 번째 수준에서 안정적이 고 버전에 관계 없이 제품 이름을 사용 합니다.  
  
 **X DO NOT** 사용 하 여 조직 계층의 기준으로 네임 스페이스 계층의 이름에 대 한 기업의 그룹 이름은 일시적인 경우가 있기 때문입니다. 관련 기술 그룹에 대 한 네임 스페이스의 계층 구조를 구성 합니다.  
  
 **✓ DO** 기간이 PascalCasing, 및 별도 네임 스페이스 구성 요소를 사용 하 여 (예: `Microsoft.Office.PowerPoint`). 특수 대/소문자 구분을 채택 하는 경우 일반 네임 스페이스 대/소문자를 벗어나는 경우에도 브랜드에서 정의한 대/소문자 구분을 따라야 합니다.  
  
 **✓ CONSIDER** 적절 한 복수형 네임 스페이스 이름을 사용 합니다.  
  
 예를 들어 `System.Collection` 대신 `System.Collections`을 사용합니다. 그러나 브랜드 이름과 머리글자어는이 규칙의 예외입니다. 예를 들어 `System.IOs` 대신 `System.IO`을 사용합니다.  
  
 **X DO NOT** 해당 네임 스페이스에서 네임 스페이스 및 형식에 대 한 동일한 이름을 사용 합니다.  
  
 예를 들어 `Debug` 네임 스페이스 이름으로 사용 하지 말고 동일한 네임 스페이스에 `Debug` 라는 클래스를 제공 합니다. 일부 컴파일러에서는 이러한 형식을 정규화 해야 합니다.  
  
### <a name="namespaces-and-type-name-conflicts"></a>네임 스페이스 및 형식 이름 충돌  
 **X DO NOT** 와 같은 제네릭 형식 이름을 소개 `Element`, `Node`, `Log`, 및 `Message`합니다.  
  
 이렇게 하면 일반적인 시나리오에서 형식 이름 충돌이 발생 하 게 될 확률이 매우 높습니다. 제네릭 형식 이름 (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`)을 한정 해야 합니다.  
  
 네임 스페이스의 다양 한 범주에 대해 형식 이름 충돌을 방지 하기 위한 특정 지침이 있습니다.  
  
- **응용 프로그램 모델 네임 스페이스**  
  
     단일 응용 프로그램 모델에 속하는 네임 스페이스는 함께 사용 되는 경우가 많지만 다른 응용 프로그램 모델의 네임 스페이스와 거의 사용 되지 않습니다. 예를 들어 <xref:System.Windows.Forms?displayProperty=nameWithType> 네임 스페이스는 <xref:System.Web.UI?displayProperty=nameWithType> 네임 스페이스와 함께 거의 사용 되지 않습니다. 다음은 잘 알려진 응용 프로그램 모델 네임 스페이스 그룹의 목록입니다.  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     **X DO NOT** 단일 응용 프로그램 모델 내에서는 네임 스페이스의 형식에 같은 이름을 지정 합니다.  
  
     예를 들어 <xref:System.Web.UI?displayProperty=nameWithType> 네임 스페이스에 `Page`이라는 형식이 이미 포함 되어 있으므로 `Page` 라는 형식을 <xref:System.Web.UI.Adapters?displayProperty=nameWithType> 네임 스페이스에 추가 하지 마세요.  
  
- **인프라 네임 스페이스**  
  
     이 그룹에는 일반적인 응용 프로그램을 개발 하는 동안 거의 가져오지 않은 네임 스페이스가 포함 됩니다. 예를 들어 `.Design` 네임 스페이스는 프로그래밍 도구를 개발할 때 주로 사용 됩니다. 이러한 네임 스페이스의 형식과 충돌을 방지 하는 것은 중요 하지 않습니다.  
  
- **핵심 네임 스페이스**  
  
     핵심 네임 스페이스에는 응용 프로그램 모델의 네임 스페이스와 인프라 네임 스페이스를 제외한 모든 `System` 네임 스페이스가 포함 됩니다. 핵심 네임 스페이스에는 기타, `System`, `System.IO`, `System.Xml`및 `System.Net`포함 됩니다.  
  
     **X DO NOT** 제공 핵심 네임 스페이스에서 종류와 충돌 하는 이름을 입력 합니다.  
  
     예를 들어 `Stream` 형식 이름으로 사용 하지 마십시오. 매우 일반적으로 사용 되는 형식 <xref:System.IO.Stream?displayProperty=nameWithType>와 충돌 합니다.  
  
- **기술 네임 스페이스 그룹**  
  
     이 범주에는 `Microsoft.Build.Utilities` 및 `Microsoft.Build.Tasks`와 같은 처음 두 개의 네임 스페이스 노드가 `(<Company>.<Technology>*`) 인 모든 네임 스페이스가 포함 됩니다. 단일 기술에 속한 형식이 서로 충돌 하지 않는 것이 중요 합니다.  
  
     **X DO NOT** 단일 기술에서 다른 종류와 충돌 하는 형식 이름을 할당 합니다.  
  
     **X DO NOT** (없는 경우 기술 응용 프로그램 모델에 사용할 수 없습니다) 기술 네임 스페이스의 형식 및 응용 프로그램 모델 네임 스페이스는 간의 유형 이름 충돌을 소개 합니다.  
  
 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*  
  
 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>참조

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)
