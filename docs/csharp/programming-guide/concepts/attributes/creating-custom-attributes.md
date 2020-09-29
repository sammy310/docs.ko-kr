---
title: 사용자 지정 특성 만들기(C#)
description: Attribute 클래스에서 파생되는 특성 클래스를 정의하여 C#에서 사용자 지정 특성을 작성하는 방법에 대해 알아봅니다.
ms.date: 07/20/2015
ms.assetid: 500e1977-c6de-462d-abce-78a0eb1eda22
ms.openlocfilehash: 6946b707134b2bdbc245b8786f144517a5870440
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202606"
---
# <a name="creating-custom-attributes-c"></a>사용자 지정 특성 만들기(C#)

메타데이터를 통해 특성의 정의를 빠르고 쉽게 식별할 수 있도록 해주는 <xref:System.Attribute>로부터 직접적으로 또는 간접적으로 상속한 특성 클래스를 정의하여 사용자 지정 특성을 만들 수 있습니다. 형식을 작성한 프로그래머의 이름을 형식에 태그로 지정한다고 가정해봅시다. 사용자 지정 `Author` 특성 클래스를 아래와 같이 정의할 수 있습니다.  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct)  
]  
public class AuthorAttribute : System.Attribute  
{  
    private string name;  
    public double version;  
  
    public AuthorAttribute(string name)  
    {  
        this.name = name;  
        version = 1.0;  
    }  
}  
```  
  
 클래스 이름 `AuthorAttribute`는 특성의 이름인 `Author`와 `Attribute` 접미사입니다. 이 클래스는 `System.Attribute`를 상속하므로 사용자 지정 특성 클래스입니다. 생성자의 매개 변수는 사용자 지정 특성의 위치 매개 변수입니다. 이 예제에서는 `name`이 위치 매개 변수입니다. 모든 public 읽기-쓰기 필드 또는 속성은 명명된 매개 변수입니다. 이 경우에는 `version`이 유일한 명명된 매개 변수입니다. 클래스 및 `struct` 선언에서만 `Author` 특성을 유효하게 설정하려면 `AttributeUsage` 특성을 사용해야 합니다.  
  
 이 새로운 특성은 다음과 같이 사용할 수 있습니다.  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
}  
```  
  
 `AttributeUsage`에는 사용자 지정 특성을 한 번 또는 여러 번 사용하도록 설정하기 위해 사용하는 명명된 매개 변수인 `AllowMultiple`이 있습니다. 다음 코드 예제에서는 다중 사용 특성을 만듭니다.  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // multiuse attribute  
]  
public class AuthorAttribute : System.Attribute  
```  
  
 다음 코드 예제에서는 같은 형식의 여러 특성이 한 클래스에 적용됩니다.  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
[Author("R. Koch", version = 1.2)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
    // R. Koch's code goes here...  
}  
```  
  
## <a name="see-also"></a>참조

- <xref:System.Reflection>
- [C# 프로그래밍 가이드](../../index.md)
- [사용자 지정 특성 작성](../../../../standard/attributes/writing-custom-attributes.md)
- [리플렉션(C#)](../reflection.md)
- [특성(C#)](./index.md)
- [리플렉션을 사용하여 특성 액세스(C#)](./accessing-attributes-by-using-reflection.md)
- [AttributeUsage(C#)](../../../language-reference/attributes/general.md)
