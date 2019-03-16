---
title: x:Code 내장 XAML 형식
ms.date: 03/30/2017
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
ms.openlocfilehash: 8d0dbc03bb5eaedd89d5a6ce97d625a51507e820
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2019
ms.locfileid: "58050604"
---
# <a name="xcode-intrinsic-xaml-type"></a>x:Code 내장 XAML 형식
XAML 프로덕션 내에서 코드를 배치할 수 있습니다. 이러한 코드 XAML, 또는 런타임에 의해 해석 등 사용에 대 한 XAML 프로덕션의 왼쪽을 컴파일되지 않는 XAML 프로세서 구현 하 여 컴파일될 수 있습니다.  
  
## <a name="xaml-object-element-usage"></a>XAML 개체 요소 사용  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a>설명  
 내의 코드는 `x:Code` XAML 지시문 요소는 여전히 일반 XML 네임 스페이스 내에서 해석 및 제공 된 XAML 네임 스페이스입니다. 에 사용 되는 코드를 포함 하는 데 일반적으로 필요한 것 이므로 `x:Code` 안에 `CDATA` 세그먼트입니다.  
  
 `x:Code` XAML 프로덕션의 모든 가능한 배포 메커니즘에 대해 허용 되지 않습니다. 특정 프레임 워크 (예: WPF) 코드를 컴파일해야 합니다. 다른 프레임 워크에서 `x:Code` 사용은 일반적으로 허용 되지 않을 수 있습니다.  
  
 관리 되는 허용 하는 프레임 워크 `x:Code` 콘텐츠를에 사용할 언어 컴파일러 `x:Code` 콘텐츠 설정 및 응용 프로그램을 컴파일하는 데 사용 되는 포함 하는 프로젝트의 대상에 따라 결정 됩니다.  
  
## <a name="wpf-usage-notes"></a>WPF 사용 정보  
 코드 내에서 선언 된 `x:Code` WPF에 몇 가지 주목할 만한 제한 사항이 있습니다.  
  
-   `x:Code` 지시문 요소는 XAML 프로덕션의 루트 요소의 직계 자식 요소 여야 합니다.  
  
-   [X:class 지시문](x-class-directive.md) 부모 root 요소에서 제공 해야 합니다.  
  
-   코드 내에 배치 `x:Code` 만들어지는 이미 해당 XAML 페이지에 대 한 partial 클래스의 범위 내에 있는 컴파일 작업으로 간주 됩니다. 따라서 정의한 모든 코드는 partial 클래스의 멤버 또는 변수 여야 합니다.  
  
-   Partial 클래스 내에 클래스를 중첩 하는 대신 추가 클래스를 정의할 수 없습니다 (중첩 허용 되지만 아니므로 일반적인 XAML에서 중첩된 클래스를 참조할 수 없습니다). 기존 partial 클래스에 사용 되는 네임 스페이스 이외의 CLR 네임 스페이스를 정의 하거나 추가할 수 없습니다.  
  
-   Partial 클래스 CLR 네임 스페이스 외부 코드 엔터티에 대 한 참조는 모두 정규화 해야 합니다. 멤버 선언 되는 부분 클래스 재정의 가능한 멤버에 대 한 재정의 경우이 언어별 override 키워드를 사용 하 여 지정 해야 합니다. 멤버에 선언 된 경우 `x:Code` 범위는 XAML에서 생성 된 partial 클래스의 멤버와 충돌, 이러한 방식으로 컴파일러에서 충돌을 보고 하는 XAML 파일 컴파일 없거나 로드 합니다.  
  
## <a name="see-also"></a>참고자료
- [x:Class 지시문](x-class-directive.md)
- [WPF의 코드 숨김 및 XAML](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [XAML 개요(WPF)](../wpf/advanced/xaml-overview-wpf.md)
