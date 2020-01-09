---
title: 보안 및 경합 상태
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
ms.openlocfilehash: 8980122acdd069bc840aa09129483a1cb9a379fd
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705875"
---
# <a name="security-and-race-conditions"></a>보안 및 경합 상태
또 다른 문제는 경합 상태에서 악용 되는 보안 허점을 일으킬 수 있다는 것입니다. 이는 여러 가지 방법으로 발생할 수 있습니다. 다음 하위 항목은 개발자가 피해 야 하는 주요 문제 중 일부를 간략하게 설명 합니다.  
  
## <a name="race-conditions-in-the-dispose-method"></a>Dispose 메서드의 경합 상태  
 클래스의 **dispose** 메서드 (자세한 내용은 [가비지 컬렉션](../../../docs/standard/garbage-collection/index.md)참조)가 동기화 되지 않은 경우 다음 예제와 같이 **dispose** 내의 정리 코드를 두 번 이상 실행할 수 있습니다.  
  
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
  
 이 **Dispose** 구현이 동기화 되지 않기 때문에 첫 번째 스레드를 통해 `Cleanup`를 호출한 다음 `_myObj`가 **null**로 설정 되기 전에 두 번째 스레드가 호출 될 수 있습니다. 보안 문제가 발생 하는지 여부는 `Cleanup` 코드가 실행 될 때 발생 하는 상황에 따라 달라 집니다. 동기화 되지 않은 **Dispose** 구현과 관련 된 주요 문제는 파일 등의 리소스 핸들을 사용 하는 것입니다. 잘못 된 삭제로 인해 잘못 된 핸들이 사용 될 수 있으며,이로 인해 보안 취약성이 발생 하기도 합니다.  
  
## <a name="race-conditions-in-constructors"></a>생성자의 경합 상태  
 일부 응용 프로그램에서는 클래스 생성자가 완전히 실행 되기 전에 다른 스레드가 클래스 멤버에 액세스할 수 있습니다. 모든 클래스 생성자를 검토 하 여이 문제가 발생 하는 경우 보안 문제가 없는지 확인 하거나 필요한 경우 스레드를 동기화 해야 합니다.  
  
## <a name="race-conditions-with-cached-objects"></a>캐시 된 개체를 사용 하는 경합 상태  
 보안 정보를 캐시 하거나 코드 액세스 보안 [어설션](../../../docs/framework/misc/using-the-assert-method.md) 작업을 사용 하는 코드는 다음 예제와 같이 클래스의 다른 부분이 적절 하 게 동기화 되지 않은 경우 경합 상태에 취약할 수 있습니다.  
  
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
  
 같은 개체를 사용 하 여 다른 스레드에서 호출할 수 있는 `DoOtherWork`에 대 한 다른 경로가 있는 경우 신뢰할 수 없는 호출자가 요청을 지난 후에 지연 될 수 있습니다.  
  
 코드가 보안 정보를 캐시 하는 경우이 취약점을 검토 해야 합니다.  
  
## <a name="race-conditions-in-finalizers"></a>종료자의 경합 상태  
 경합 상태는 해당 종료자에서 해제할 정적 또는 관리 되지 않는 리소스를 참조 하는 개체 에서도 발생할 수 있습니다. 여러 개체가 클래스의 종료자에서 조작 되는 리소스를 공유 하는 경우 개체는 해당 리소스에 대 한 모든 액세스를 동기화 해야 합니다.  
  
## <a name="see-also"></a>참조

- [보안 코딩 지침](../../../docs/standard/security/secure-coding-guidelines.md)
