---
title: x:TypeArguments 지시문
ms.date: 03/30/2017
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
ms.openlocfilehash: 1d1b10b4da1263843bdce5447f0716569c7700e3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085807"
---
# <a name="xtypearguments-directive"></a>x:TypeArguments 지시문
전달 된 제네릭 형식의 생성자에 제네릭 인수를 입력 합니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`object`|CLR 제네릭 형식에서 지원 되는 XAML 형식의 개체 요소 선언 합니다. 하는 경우 `object` 아니라 기본 XAML 네임 스페이스는 XAML 형식을 참조 `object` 나타내는 XAML 네임 스페이스 접두사가 필요 여기서 `object` 존재 합니다.|  
|`typeString`|하나 이상의 XAML을 선언 하는 문자열에 입력 문자열로 CLR 제네릭 형식의 형식 인수를 제공 하는 이름입니다. 자세한 구문 정보에 대 한 설명을 참조 하세요.|  
  
## <a name="remarks"></a>설명  
 대부분의 경우에서 정보 항목으로 사용 되는 XAML 형식에는 `typeString` 문자열 붙습니다. 일반적인 유형의 CLR 제네릭 제약 조건 (예를 들어 <xref:System.Int32> 고 <xref:System.String>) CLR 기본 클래스 라이브러리에서 제공 합니다. 해당 라이브러리에 일반적인 매핑된 프레임 워크 관련 기본 XAML 네임 스페이스에 없는 및 따라서 접두사 매핑을 XAML 사용에 대 한 필요 합니다.  
  
 쉼표 구분 기호를 사용 하 여 둘 이상의 XAML 형식 이름을 지정할 수 있습니다.  
  
 제네릭 제약 조건 자체가 제네릭 형식을 사용 하는 경우 중첩 된 제약 조건 형식 인수는 괄호 () 포함할 수 있습니다.  
  
 이 정의의 `x:TypeArguments` .NET Framework XAML 서비스와 관련 되 고 CLR 백업의 사용 합니다. 언어 수준 정의에서 찾을 수 있습니다 [ \[MS XAML\] 5.3.11 섹션](https://go.microsoft.com/fwlink/?LinkId=114525)합니다.  
  
## <a name="usage-examples"></a>사용 예제  
 이러한 예를 들어 다음 XAML 네임 스페이스 정의 선언 된 가정 합니다.  
  
```  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a>목록\<문자열 >  
 `<scg:List x:TypeArguments="sys:String" ...>` 새 인스턴스화합니다 <xref:System.Collections.Generic.List%601> 사용 하 여는 <xref:System.String> 인수를 입력 합니다.  
  
### <a name="dictionarystringstring"></a>사전\<문자열, 문자열 >  
 `<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` 새 인스턴스화합니다 <xref:System.Collections.Generic.Dictionary%602> 두 개의 <xref:System.String> 인수를 입력 합니다.  
  
### <a name="queuekeyvaluepairstringstring"></a>Queue<KeyValuePair\<String,String>>  
 `<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` 새 인스턴스화합니다 <xref:System.Collections.Generic.Queue%601> 의 제약 조건이 있는 <xref:System.Collections.Generic.KeyValuePair%602> 내부 제약 조건 형식 인수를 사용 하 여 <xref:System.String> 고 <xref:System.String>입니다.  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>XAML 2006 및 WPF 일반 XAML 사용  
 XAML 2006 사용 및 WPF 응용 프로그램에 사용 되는 XAML의 경우는 다음과 같은 제한 사항이 `x:TypeArguments` 및 일반 XAML에서 제네릭 형식 사용:  
  
-   XAML 파일의 루트 요소에만 제네릭 형식을 참조 하는 제네릭 XAML 사용을 지원할 수 있습니다.  
  
-   루트 요소는 하나 이상의 형식 인수가 있는 제네릭 형식에 매핑되어야 합니다. 예로 <xref:System.Windows.Navigation.PageFunction%601>합니다. 페이지는 WPF의 XAML 제네릭 사용 지원에 대 한 기본 시나리오.  
  
-   제네릭에 대 한 루트 요소 XAML 개체 요소를 사용 하 여 partial 클래스를 선언 해야 합니다 `x:Class`합니다. 빌드 작업 WPF를 정의 하는 경우에 마찬가지입니다.  
  
-   `x:TypeArguments` 중첩 된 제네릭 제약을 참조할 수 없습니다.  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 또는 WPF 3.0 또는 3.5 WPF 없이 XAML 2006 종속성  
 XAML 2006 또는 XAML 2009에 대 한.NET Framework XAML 서비스에서 제네릭 XAML 사용에 WPF 관련 대 한 제한이 완화 됩니다. XAML 태그는 지원 형식 시스템 및 개체 모델을 지원할 수 있는 모든 위치에서 일반 개체 요소를 인스턴스화할 수 있습니다.  
  
 XAML 2009를 사용 하는 경우 CLR 대신 기본 공용 언어 기본 형식에 대 한 XAML 형식을 가져올 형식, 사용할 수 있습니다 [공용 XAML 언어 기본 형식에 대 한 기본 제공 형식](built-in-types-for-common-xaml-language-primitives.md) 의 정보 항목으로는 `typeString`합니다. 예를 들어, 다음에 선언할 수 있습니다 (접두사 매핑이 표시 되지 않지만 x는 XAML 2009에 대해 XAML 언어 XAML 네임 스페이스):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 Wpf에서 및 대상으로 할 때 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]와 함께 XAML 2009 기능을 사용할 수 있습니다 `x:TypeArguments` 느슨한 XAML (태그 컴파일되지 않은 XAML)에 대해서만 합니다. WPF에 대한 태그로 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다. 태그에는 XAML을 컴파일해야 하는 경우 "XAML 2006 및 WPF 일반 XAML 사용" 섹션에서 설명한 제한에서 작동 해야 합니다.  
  
## <a name="see-also"></a>참고자료

- [x:Class 지시문](x-class-directive.md)
- [x:Type 태그 확장](x-type-markup-extension.md)
- [공용 XAML 언어 기본 형식에 대한 기본 제공 형식](built-in-types-for-common-xaml-language-primitives.md)
- [XAML의 제네릭](generics-in-xaml.md)
