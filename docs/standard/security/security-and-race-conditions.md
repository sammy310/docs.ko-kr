---
title: 보안 및 경합 상태
'description:': Describes pitfalls to avoid around security holes exploited by race conditions, including dispose methods, constructors, cached objects, and finalizers.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], race conditions
- race conditions
- secure coding, race conditions
- code security, race conditions
ms.assetid: ea3edb80-b2e8-4e85-bfed-311b20cb59b6
ms.openlocfilehash: 09d8d0d6e85af04fe0fb00f53df408126012081e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186788"
---
# <a name="security-and-race-conditions"></a>보안 및 경합 상태
또 다른 우려 영역은 경주 조건에 의해 악용되는 보안 허점의 가능성입니다. 이 문제가 발생할 수 있는 방법에는 여러 가지가 있습니다. 다음 하위 항목은 개발자가 피해야 하는 몇 가지 주요 함정에 대해 설명합니다.  
  
## <a name="race-conditions-in-the-dispose-method"></a>처분 방식의 레이스 조건  
 클래스의 **Dispose** 메서드(자세한 내용은 [가비지 수집](../../../docs/standard/garbage-collection/index.md)참조)가 동기화되지 않은 경우 다음 예제와 같이 **Dispose** 내부의 정리 코드를 두 번 이상 실행할 수 있습니다.  
  
```vb  
Sub Dispose()  
    If Not (myObj Is Nothing) Then  
       Cleanup(myObj)  
       myObj = Nothing  
    End If  
End Sub  
```  
  
```csharp  
void Dispose()
{  
    if (myObj != null)
    {  
        Cleanup(myObj);  
        myObj = null;  
    }  
}  
```  
  
 이 **Dispose** 구현은 동기화되지 않으므로 첫 `Cleanup` 번째 스레드에서 호출한 다음 두 번째 `_myObj` 스레드를 **null로**설정할 수 있습니다. 이것이 보안 문제인지 여부는 `Cleanup` 코드가 실행될 때 발생하는 상황에 따라 달라집니다. 동기화되지 않은 **Dispose** 구현의 주요 문제는 파일과 같은 리소스 핸들을 사용하는 것입니다. 부적절한 처리로 인해 잘못된 핸들이 사용될 수 있으며, 이로 인해 보안 취약점이 발생할 수 있습니다.  
  
## <a name="race-conditions-in-constructors"></a>생성자 내의 레이스 조건  
 일부 응용 프로그램에서는 클래스 생성자가 완전히 실행되기 전에 다른 스레드가 클래스 멤버에 액세스할 수 있습니다. 모든 클래스 생성자검토하여 이 문제가 발생할 경우 보안 문제가 없는지 확인하거나 필요한 경우 스레드를 동기화해야 합니다.  
  
## <a name="race-conditions-with-cached-objects"></a>캐시된 객체가 있는 경합 조건  
 다음 예제와 같이 보안 정보를 캐시하거나 코드 액세스 보안 [Assert](../../../docs/framework/misc/using-the-assert-method.md) 작업을 사용하는 코드는 클래스의 다른 부분이 적절하게 동기화되지 않은 경우 경합 조건에 취약할 수 있습니다.  
  
```vb  
Sub SomeSecureFunction()  
    If SomeDemandPasses() Then  
        fCallersOk = True  
        DoOtherWork()  
        fCallersOk = False  
    End If  
End Sub  
  
Sub DoOtherWork()  
    If fCallersOK Then  
        DoSomethingTrusted()  
    Else  
        DemandSomething()  
        DoSomethingTrusted()  
    End If  
End Sub  
```  
  
```csharp  
void SomeSecureFunction()
{  
    if (SomeDemandPasses())
    {  
        fCallersOk = true;  
        DoOtherWork();  
        fCallersOk = false;  
    }  
}  
void DoOtherWork()
{  
    if (fCallersOK)
    {  
        DoSomethingTrusted();  
    }  
    else
    {  
        DemandSomething();  
        DoSomethingTrusted();  
    }  
}  
```  
  
 동일한 개체를 `DoOtherWork` 가진 다른 스레드에서 호출할 수 있는 다른 경로가 있는 경우 신뢰할 수 없는 호출자는 요청을 통과할 수 있습니다.  
  
 코드가 보안 정보를 캐시하는 경우 이 취약점을 검토해야 합니다.  
  
## <a name="race-conditions-in-finalizers"></a>종료자의 레이스 조건  
 경합 조건은 정적 또는 관리되지 않는 리소스를 참조한 다음 종료자에서 해제하는 개체에서도 발생할 수 있습니다. 여러 개체가 클래스의 종료자에서 조작된 리소스를 공유하는 경우 개체는 해당 리소스에 대한 모든 액세스를 동기화해야 합니다.  
  
## <a name="see-also"></a>참고 항목

- [보안 코딩 지침](../../../docs/standard/security/secure-coding-guidelines.md)
